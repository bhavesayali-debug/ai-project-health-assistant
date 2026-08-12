# Action & Dependency Tracker — Scenario 01

## Project Information

**Project:** Online Banking Upgrade Project  
**Project Manager:** Sayali Bhave  
**Snapshot Date:** August 12, 2026  

> This is synthetic project data created for the AI Project Health Assistant prototype. It does not represent any real organization or production system.

---

## Actions and Dependencies

| ID | Type | Description | Related Feature | Owner | Target / Due Date | Status | Escalation |
|---|---|---|---|---|---|---|---|
| ACT-01 | Action | Obtain confirmed availability date for beneficiary-validation API | Beneficiary Management / Fund Transfer Upgrade | Sayali Bhave | August 10, 2026 | Overdue | Vendor follow-up required |
| DEP-01 | External Dependency | Beneficiary-validation API must be available in the test environment | Beneficiary Management / Fund Transfer Upgrade | External Vendor | August 10, 2026 | Not Available | Escalation pending |
| ACT-02 | Action | Assess Fund Transfer schedule impact if API remains unavailable | Fund Transfer Upgrade | Backend Lead | August 14, 2026 | Open | None |
| ACT-03 | Action | Retest two Transaction History UAT defects | Transaction History & Search | QA Lead | August 17, 2026 | Open | None |
| ACT-04 | Action | Confirm recurring-payment requirements | Bill Payment Upgrade | Product Owner | August 13, 2026 | Open | None |
| ACT-05 | Action | Investigate intermittent transaction-event delays | Transaction Alerts & Notifications | Backend Lead | August 14, 2026 | Open | None |
| DEP-02 | Technical Dependency | Stable transaction-event service required for alert processing | Transaction Alerts & Notifications | Backend / API Team | August 21, 2026 | Under Investigation | None |
| DEP-03 | Security Dependency | Security review required before production | Secure Messaging | Security Team | October 30, 2026 | Not Started | None |

---

## Current Dependency Notes

### Beneficiary-Validation API

- The external beneficiary-validation API is currently unavailable in the test environment.
- The dependency affects Beneficiary Management directly.
- Fund Transfer also depends on beneficiary validation for new-beneficiary testing.
- The original expected availability date of August 10 has passed.
- A confirmed recovery date has not yet been provided.

### Transaction Event Service

- Transaction Alerts & Notifications depends on the transaction-event service.
- Intermittent event delays have been observed in the test environment.
- Investigation is ongoing.
- No confirmed milestone impact has been identified yet.

### Secure Messaging Security Review

- Secure Messaging requires security review before production.
- The dependency has not started because the feature is scheduled for later in the delivery plan.
- No current schedule impact has been identified.

---

## Tracker Notes

- An overdue action or unresolved dependency should not automatically determine overall project health.
- Health assessment should consider proximity to milestones, delivery impact, severity, recoverability, and supporting evidence from other project sources.
