# Risk & Issue Register — Scenario 01

## Project Information

**Project:** Online Banking Upgrade Project  
**Project Manager:** Sayali Bhave  
**Snapshot Date:** August 12, 2026  

> This is synthetic project data created for the AI Project Health Assistant prototype. It does not represent any real organization or production system.

---

## Risks and Issues

| ID | Type | Description | Probability | Impact | Owner | Status | Last Updated | Mitigation / Action |
|---|---|---|---|---|---|---|---|---|
| ISS-01 | Issue | Beneficiary-validation API is unavailable in the test environment, preventing dependent development and testing. | — | High | Backend Lead | Open | August 5, 2026 | Vendor working on environment access. Expected resolution by August 10. |
| RSK-01 | Risk | Delay in beneficiary-validation API availability may affect Fund Transfer testing and the September 4 production target. | Medium | High | Sayali Bhave | Open | August 5, 2026 | Continue independent SIT scenarios. Reassess schedule if API remains unavailable. |
| ISS-02 | Issue | Two medium-severity defects remain open in Transaction History UAT. | — | Medium | QA Lead | Open | August 11, 2026 | Fixes are being tested. Retest expected by August 17. |
| RSK-02 | Risk | Bill Payment delivery may be delayed if recurring-payment requirements are not clarified promptly. | Low | Medium | Business Analyst | Open | August 11, 2026 | Requirement clarification requested from Product Owner. |

---

## Register Notes

- The beneficiary-validation dependency entries were last updated on August 5, 2026.
- At that time, external service availability was expected by August 10, 2026.
- This register should be interpreted together with more recent project updates.
