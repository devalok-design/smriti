---
title: The Break Framework — Complete Reference
version: 1.0.0
lastUpdated: 2026-03-24
---

# The Break Framework — Complete Reference

Devalok's leave and attendance system. Replaces the conventional weekday/weekend model with a fluid, trust-based break pool. No fixed weekends, no weekdays — Lokwasis work and rest on their own rhythm within a defined annual break budget.

For the overview, see the Complete Context doc, Section 18. This document covers every rule, edge case, and operational detail.

---

## 1. The Break Pool

**122 break days per year**, split into two halves:

| Half | Period | Days |
|------|--------|------|
| H1 | January 1 – June 30 | 61 days |
| H2 | July 1 – December 31 | 61 days |

**Origin of 122:** 52 weeks × 2 weekend days + 15 PTOs + 3 National Holidays = 122 breaks. Since there are no fixed weekends, Lokwasis choose when to use these days.

Every calendar day counts equally — a 7-day break uses 7 days, regardless of which days of the week they fall on.

---

## 2. Balance Computation

A Lokwasi's remaining break balance is:

```
remaining = baseAllocation
           + approved carry-forward days
           + approved manual adjustments
           - approved break days used
           - uncorrected absence days
```

**Critical rule: Absences reduce break balance.** If a Lokwasi misses marking attendance and doesn't get it corrected, that missed day counts against their break pool — just like a break day. This is the single most misunderstood aspect of the framework.

### What counts as "used"
- Approved break days within the half
- For cross-boundary breaks, only the days falling within the specific half count
- Uncorrected absences (Attendance records with status ABSENT and corrected: false)

### What does NOT count against balance
- Cancelled break days (automatically returned to pool)
- Corrected absences (admin approved the correction)
- Cashout/forfeit adjustments (accounting entries, not spendable)
- National holidays (Jan 26, Aug 15, Oct 2 — these are free)

---

## 3. Entitlement by Role

| Role | H1 | H2 | Notes |
|------|----|----|-------|
| Regular staff | 61 | 61 | Full allocation |
| Mid-year joiner | Pro-rated | Pro-rated or 61 | See Section 4 |
| Apprentice | 0 | 0 | Case-by-case admin approval; no fixed pool |
| Attendance-exempt | N/A | N/A | Outside the framework entirely |

### Attendance-Exempt ("Beyond BREAK")
Founders and leadership marked as `isAttendanceExempt`. They:
- Cannot mark attendance
- Cannot request breaks
- Always count as present in team views
- Break balance is always zero
- Are excluded from all break-related calculations and reports

---

## 4. Pro-Rating for Mid-Year Joiners

Formula: `ceil(61 × remainingDaysInHalf / totalDaysInHalf)`

Uses ceiling (always rounds up — favors the Lokwasi).

**H1 joiner example:** Joins March 15.
- H1 remaining: Mar 15 – Jun 30 = 108 days out of 181 total
- H1 allocation: ceil(61 × 108/181) = ceil(36.4) = 37 days
- H2 allocation: full 61 days

**H2 joiner:** Gets 0 H1 days + pro-rated H2.

Allocations are created lazily — when a Lokwasi first requests a break, the system checks if their half-year allocations exist and creates them if not.

---

## 5. Requesting a Break

### Prerequisites (hard gates — submission blocked if not met)
1. **Not attendance-exempt** — exempt users cannot request breaks
2. **Google Calendar connected** — the system creates Out-of-Office events; calendar auth is mandatory before any break request
3. **Start date not in the past** — cannot request retroactive breaks
4. **No overlap with existing breaks** — checks against all PENDING and APPROVED requests. Adjacent (back-to-back) requests are also flagged as overlaps to prevent gaming
5. **Sufficient balance** — checked per half for cross-boundary requests (skipped for Apprentices since they have no fixed allocation)

### Protocol Violations (advisory — never blocks submission)
| Break Length | Required Notice |
|-------------|----------------|
| < 3 days | At least 1 day before start |
| ≥ 3 days | At least 5 days before start |

Violating the protocol flags the request (`protocolViolation: true`) with a human-readable reason. The admin sees the warning when reviewing. The request still goes through.

### Cross-Boundary Breaks

**Cross-half (Jun 30 → Jul 1):** Automatically split into two linked requests — one for H1 days, one for H2 days. Each is validated against its own half's balance. Both requests store each other's ID (`linkedRequestId`) for tracking.

**Cross-year (Dec 31 → Jan 1):** Same split logic, but across years. Each request validated against its year's allocation.

The split is transparent to the Lokwasi — they request one date range, the system handles the rest.

### Side Effects on Successful Creation
- Google Calendar Out-of-Office event created (best-effort — failure doesn't block)
- SSE event published for real-time UI updates
- Admin notification sent
- Audit log entry created

---

## 6. Approval Flow

Admin with break management permission reviews pending requests.

On approval:
- Break status set to APPROVED
- One Attendance record per break day created (status: BREAK)
- Google Calendar OOO event created if not already
- Lokwasi notified
- If the request has a linked sibling (from a split), both are handled

**Self-approval is blocked.** An admin cannot approve their own break request — another admin must do it.

**Date editing at approval:** Admin can modify the break dates during approval. The system recalculates the day count from the new range.

---

## 7. Rejection Flow

On rejection:
- If rejecting an already-approved break:
  - Past break days (before today) revert from BREAK to ABSENT in attendance
  - Future break days are deleted from attendance
- Linked sibling is cascade-rejected (if not already rejected/cancelled)
- Calendar events deleted for both requests

---

## 8. Cancellation

Lokwasis can cancel their own breaks **without admin permission**. Admins are notified.

### Cancellation Gates (enforced — not advisory)
1. **Cannot cancel an ended break** — if `endDate` is before today, the break is over
2. **Same-day gate:** After **11:00 AM IST**, cannot cancel today's break day
   - Exception: can still cancel future days within a multi-day break even if today is locked
3. No prior admin approval needed for cancellation

### Full Cancellation
- Status set to CANCELLED
- All Attendance records for the break deleted
- Linked sibling cancelled if present
- Calendar events deleted
- Balance automatically restored (cancelled days stop counting as "used")

### Partial Cancellation (removing one day from a multi-day break)

Three cases depending on which day is removed:

| Cancelled Day | What Happens |
|--------------|-------------|
| Start day | Break start moves to the next day, numberOfDays decremented |
| End day | Break end moves to the previous day, numberOfDays decremented |
| Middle day | Break splits into two new requests — the pre-gap portion and the post-gap portion |

In all cases:
- Attendance record for the cancelled day is deleted
- Old Calendar event deleted, new one(s) created for remaining days
- If a middle-day cancel splits the break, the original request is modified and a new request is created for the earlier portion

---

## 9. Annual Lifecycle

| Date | Event | Details |
|------|-------|---------|
| **Jan 1** | Allocation seeding | H1 (61 days) + H2 (61 days) created for all active, non-exempt, non-Apprentice users. Pro-rated for mid-year joiners. Idempotent. |
| **Jul 1** | H1→H2 carry-forward | Unused H1 days (max 7) added to H2 as a CARRY_FORWARD adjustment. Excess H1 days are lost. Record created even if carry amount is 0 (for idempotency). |
| **Dec 15** | Year-end preview | Dry-run: computes cashout/forfeit amounts per user for admin review. No writes. |
| **Dec 31** | Year-end execution | Cashout (max 15 days) + forfeit (anything above 15) + new year allocations created. All in one transaction per user. |

### Carryover Details (Jul 1)
- `carryAmount = min(max(h1Remaining, 0), 7)`
- If H1 remaining is negative (due to absences), carry is 0
- The carry-forward is a separate adjustment record — it does NOT modify the H2 base allocation
- H1 days above 7 are silently forfeited (no FORFEIT record created for H1 — only at year-end)

### Year-End Details (Dec 31)
- `cashoutAmount = min(max(h2Remaining, 0), 15)`
- `forfeitAmount = max(h2Remaining - 15, 0)`
- Both CASHOUT and FORFEIT adjustments created (even if 0, for idempotency)
- New year's H1 + H2 allocations created in the same transaction

---

## 10. Attendance Interaction

### Marking Attendance on Break Days
Cannot mark attendance on an approved break day. The system blocks it — the Lokwasi must cancel the break first.

### Missed Attendance
- If not marked by 11:00 AM the next day, automatically marked as ABSENT
- ABSENT records with `corrected: false` drain break balance
- Correction request (RAC) within 7-day lookback, up to 15/year

### Attendance Corrections (RAC)
- **Quota:** 15 per year (admin can grant more via `extraAttendanceCorrections` on User)
- **Lookback:** 7 days
- **Rejected corrections** don't count against the quota
- **Threshold notifications:**
  - 50% remaining: in-app alert
  - 25% remaining: in-app alert
  - 10% remaining: in-app + email
  - 3% remaining: in-app + email

---

## 11. Cashout Requests

Separate from the year-end cron. Individual Lokwasis can submit cashout requests via the `CashoutRequest` model:
- `days` — number of days to cash out
- `calculatedAmount` — payment amount (set by admin during processing)
- Status: PENDING → APPROVED or REJECTED

The year-end cron creates system-level CASHOUT adjustments. The CashoutRequest is the staff-facing request flow.

---

## 12. Anomaly Detection

A daily cron at 6 PM IST checks for break balance anomalies:
- **Negative balance** — remaining days < 0 (likely due to uncorrected absences)
- **High usage** — used days > 80% of allocation (early warning)

These anomalies are logged and available to the AI agent but do not generate individual notifications.

---

## 13. Edge Cases — Quick Reference

| Scenario | Behavior |
|----------|----------|
| Break spans Jun 30 – Jul 1 | Auto-split into two linked requests |
| Break spans Dec 31 – Jan 1 | Auto-split across years |
| Request overlaps existing break | Blocked — includes adjacent (back-to-back) detection |
| Balance insufficient in one half of a split | Request blocked with per-half breakdown |
| Apprentice requests break | No balance check — goes straight to admin for case-by-case |
| Exempt user tries to request | Blocked — outside the framework |
| Cancel at 10:59 AM IST | Allowed (before 11 AM gate) |
| Cancel at 11:01 AM IST | Today's day blocked; future days in same break still cancellable |
| Cancel middle day of Mon-Fri break | Break splits: Mon-Tue + Thu-Fri (two requests) |
| Admin approves own break | Blocked — another admin must approve |
| 3 missed attendances in a month | 3 break days consumed from balance |
| Correction approved for missed day | Day no longer drains break balance |
| H1 remaining: -2 days | Carry-forward to H2: 0 days (no negative carry) |
| Year-end remaining: 20 days | Cashout: 15, forfeit: 5 |
| Year-end remaining: 8 days | Cashout: 8, forfeit: 0 |
