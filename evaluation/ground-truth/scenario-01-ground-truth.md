
# Ground Truth — Scenario 01

## Scenario Information

**Project:** Online Banking Upgrade Project  
**Assessment Date:** August 12, 2026  
**Expected Overall Health:** AMBER  
**Scenario Type:** Delivery risk with recoverable external dependency  

> This file is an evaluation artifact for the AI Project Health Assistant.
> It must not be included in the project information provided to the AI during assessment.

---

## Expected Overall Assessment

### AMBER — At Risk but Recoverable

The project should no longer be assessed as Green because the unresolved beneficiary-validation API dependency is creating a meaningful risk to the Fund Transfer delivery timeline.

However, the project should not currently be assessed as Red because no committed production milestone has yet been missed and a realistic recovery path still exists.

---

## Primary Health Driver

### Fund Transfer / Beneficiary-Validation Dependency

The most significant current concern is the unavailable external beneficiary-validation API.

Expected reasoning should connect the following evidence:

- Beneficiary Management is currently Blocked.
- The beneficiary-validation API was expected to be available by August 10.
- The August 10 expected availability date has passed.
- The API remains unavailable as of August 12.
- No confirmed recovery date has been provided.
- Fund Transfer depends on beneficiary validation for new-beneficiary testing.
- Some Fund Transfer SIT scenarios therefore cannot currently be completed.
- Fund Transfer SIT is planned to complete by August 21.
- Fund Transfer production is targeted for September 4.
- A Fund Transfer schedule-impact assessment is still pending.
- The Product Owner has questioned confidence in the September 4 production target.

### Expected Interpretation

Fund Transfer is at risk, but there is currently insufficient evidence to conclude that the September 4 production target will definitely be missed.

---

## Why the Project Is Not GREEN

The project should not remain Green because:

1. An important external dependency has missed its expected availability date.
2. The dependency is blocking required testing.
3. The same dependency affects a feature with a relatively near-term milestone.
4. There is no confirmed recovery date.
5. A schedule-impact assessment remains outstanding.
6. Stakeholder confidence in the Fund Transfer production date has been questioned.

These signals together represent a meaningful delivery risk requiring active PM attention.

---

## Why the Project Is Not RED

The project should not currently be Red because:

- No committed production milestone has been missed.
- Fund Transfer still has time before the September 4 production date.
- Some SIT activities continue independently of the blocked service.
- No evidence currently proves that UAT or production will definitely slip.
- No Critical or High-severity defects are recorded.
- A potential recovery path still exists if the external service becomes available soon.

---

## Secondary Concerns

### Transaction Alerts & Notifications

**Expected assessment:** Watch / emerging concern.

Evidence:

- Intermittent transaction-event delays are occurring in the test environment.
- Investigation is ongoing.
- No confirmed milestone impact has been identified.

This should not currently be a primary driver of overall project health.

---

### Transaction History & Search

**Expected assessment:** On track with issues being monitored.

Evidence:

- Two Medium-severity UAT defects remain.
- Fixes and retesting are planned.
- Product Owner does not currently consider the defects release blockers.
- No impact to the August 21 production target is expected.

The AI should not mark this feature Amber solely because defects exist.

---

### Bill Payment Upgrade

**Expected assessment:** Minor watch item / currently on track.

Evidence:

- Development is progressing.
- Requirement clarification for recurring payments is pending.
- Clarification is expected shortly.
- No schedule impact has currently been identified.

---

## Items That Should NOT Materially Drive Overall Health

The AI should avoid overreacting to:

- The Low-severity Account Dashboard production defect.
- Secure Messaging security review that is scheduled for a later phase.
- Features that are legitimately Not Started because their planned delivery dates are later.
- Medium-severity defects that have credible resolution plans and no current milestone impact.
- The fact that only 2 of 10 features are currently in Production.

Feature count alone should not determine project health.

---

## Expected PM Attention

The AI should recommend PM attention to approximately the following:

1. Obtain a confirmed recovery date from the external vendor.
2. Complete the Fund Transfer schedule-impact assessment.
3. Determine remaining SIT and UAT contingency if the API delay continues.
4. Escalate the vendor dependency if a recovery date cannot be confirmed promptly.
5. Continue monitoring the Transaction Alerts event-service investigation.
6. Continue tracking Transaction History UAT defect resolution without unnecessarily escalating it.

---

## Expected Quick-Glance Summary

**Overall Project Health:** AMBER

**Primary Driver:**  
Unresolved beneficiary-validation API dependency is threatening the Fund Transfer testing timeline.

**Immediate Attention:**
- Vendor recovery date is overdue.
- Fund Transfer impact assessment is pending.
- Planned SIT completion: August 21.
- Planned production: September 4.

**Other Watch Items:**
- Transaction Alerts event-service delays.
- Two Medium-severity Transaction History UAT defects.

**Production Status:**
- 2 features are live and stable.

---

## Expected Evidence Behavior

A successful AI response should:

- Prefer newer August 11–12 information over the August 7 Executive Status Update.
- Recognize that the August 5 Risk Register information regarding expected August 10 resolution is stale.
- Correlate the beneficiary dependency across multiple sources.
- Explain why the project has moved from the previously reported Green position to Amber.
- Cite supporting project evidence.
- Clearly distinguish confirmed facts from potential future impacts.

---

## Unsupported Conclusions the AI Should Avoid

The AI should NOT claim:

- The September 4 Fund Transfer production date will definitely be missed.
- The entire project is failing.
- Transaction History will miss its August 21 release.
- Transaction Alerts will miss its October 2 release.
- Critical production problems exist.
- A major project re-plan is already required.

There is insufficient evidence for these conclusions.

---

## What Would Make the Scenario RED

A future assessment could reasonably become Red if evidence showed that:

- The beneficiary-validation API remains unavailable.
- Fund Transfer SIT cannot be completed.
- UAT cannot start or complete as planned.
- September 4 is forecast to be missed.
- No credible short-term recovery option exists.
- Major re-planning or leadership intervention is required.

---

## Evaluation Criteria

The AI response should later be scored against:

1. Correct overall RAG assessment.
2. Identification of the primary delivery concern.
3. Appropriate treatment of secondary concerns.
4. Use of supporting evidence.
5. Recognition of stale or conflicting information.
6. Absence of unsupported claims.
7. Appropriate handling of uncertainty.
8. Quality of PM attention recommendations.
