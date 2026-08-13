# Scenario 01 — Consistency Review

## Project

**AI Project Health Assistant**

## Scenario

**Scenario 01 — Online Banking Upgrade Project**

**Review Date:** August 13, 2026

---

## Purpose

This review verifies that the synthetic project sources tell one coherent project story.

The dataset intentionally contains some stale, incomplete, and conflicting information because the AI Project Health Assistant is expected to reason across multiple sources rather than blindly trust a single document.

Accidental inconsistencies should be corrected.

Intentional inconsistencies should remain as part of the evaluation scenario.

---

## Core Scenario Truth

As of August 12, 2026:

- 2 features are in Production.
- 1 feature is in UAT.
- 1 feature is in SIT.
- 2 features are in Development.
- 1 feature is Blocked.
- 3 features are Not Started.
- Beneficiary Management is blocked by the unavailable external beneficiary-validation API.
- Fund Transfer is also affected because some SIT scenarios require beneficiary validation.
- Fund Transfer SIT is planned to complete on August 21.
- Fund Transfer production is planned for September 4.
- No production milestone has yet been missed.
- Recovery is still possible.
- Expected current overall health is AMBER.

---

## Intentional Differences Across Sources

### 1. Executive Status: Green vs Current Expected Health: Amber

**Executive Status Update:** August 7 — Green  
**Current assessment date:** August 12 — Expected Amber

**Decision:** KEEP

**Reason:**  
The project situation changed after the executive report was issued. The AI should recognize that newer evidence can change the current health assessment.

---

### 2. Vendor API Expected August 10 vs Still Unavailable August 12

**Risk & Issue Register:** API expected by August 10  
**Meeting Notes:** API unavailable on August 11  
**Weekly Delivery Update:** API still unavailable on August 12

**Decision:** KEEP

**Reason:**  
This deliberately tests whether the AI detects stale information and gives appropriate weight to newer evidence.

---

### 3. Transaction Alerts Concern Missing From Risk Register

The Weekly Delivery Team Update and meeting notes mention intermittent transaction-event delays.

The formal Risk & Issue Register does not yet contain this concern.

**Decision:** KEEP

**Reason:**  
This represents an emerging delivery signal that has not yet been formally converted into a project risk.

The AI should identify it as a watch item without exaggerating its impact.

---

### 4. Account Dashboard Production Defect

The Account Dashboard is in Production and considered stable, while the Defect Tracker contains one Low-severity cosmetic defect.

**Decision:** KEEP

**Reason:**  
This tests whether the AI understands that the existence of a defect does not automatically make a feature or project unhealthy.

---

### 5. Beneficiary Management Blocked but Later Production Date

Beneficiary Management is blocked, but its production target is October 16.

Fund Transfer is affected by the same dependency but has an earlier September 4 production target.

**Decision:** KEEP

**Reason:**  
This tests whether the AI considers milestone proximity, urgency, delivery impact, and recoverability instead of treating the same dependency equally across all features.

---

## Accidental Inconsistencies Corrected

### Vendor Follow-Up Action

The Weekly Delivery Team Update originally showed the vendor follow-up action due August 13.

It was corrected to:

**August 10 — Overdue**

This aligns with the Meeting Notes and Action & Dependency Tracker.

---

### Bill Payment Requirement Clarification

The Weekly Delivery Team Update originally assigned requirement clarification to the Business Analyst.

It was corrected to:

**Owner: Product Owner**

The Business Analyst is waiting for clarification from the Product Owner.

---

## Final Consistency Assessment

Scenario 01 is internally coherent.

Remaining differences between sources are intentional and are designed to test:

- Recency reasoning
- Cross-source correlation
- Severity assessment
- Milestone impact
- Dependency reasoning
- Handling of stale information
- Appropriate uncertainty
- Avoidance of unsupported conclusions

Scenario 01 is therefore suitable for use as the first evaluation dataset for the AI Project Health Assistant.
