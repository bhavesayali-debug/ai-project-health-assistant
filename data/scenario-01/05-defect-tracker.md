# Defect Tracker — Scenario 01

## Project Information

**Project:** Online Banking Upgrade Project  
**Project Manager:** Sayali Bhave  
**Snapshot Date:** August 12, 2026  

> This is synthetic project data created for the AI Project Health Assistant prototype. It does not represent any real organization or production system.

---

## Defects

| Defect ID | Feature | Environment | Severity | Status | Description | Owner | Target Resolution |
|---|---|---|---|---|---|---|---|
| DEF-201 | Transaction History & Search | UAT | Medium | Open | Date-range search occasionally excludes transactions from the final selected day. | Backend Team | August 14, 2026 |
| DEF-202 | Transaction History & Search | UAT | Medium | Fix Ready / Awaiting Retest | Transaction description is truncated for some merchant transactions. | Frontend Team | August 17, 2026 |
| DEF-203 | Fund Transfer Upgrade | SIT | Medium | Open | Transfer confirmation page occasionally displays an outdated available balance after submission. | Backend Team | August 14, 2026 |
| DEF-204 | Account Dashboard | Production | Low | Open | Account-card alignment is inconsistent on some smaller-screen resolutions. | Frontend Team | August 21, 2026 |

---

## Defect Summary

| Severity | Open / Active Count |
|---|---:|
| Critical | 0 |
| High | 0 |
| Medium | 3 |
| Low | 1 |

---

## Notes

- No Critical or High-severity defects are currently recorded.
- The two Transaction History defects are not currently considered release blockers.
- Fund Transfer has one open SIT defect in addition to incomplete testing caused by the beneficiary-validation dependency.
- The Account Dashboard production defect is cosmetic and has no known material delivery or customer impact.
