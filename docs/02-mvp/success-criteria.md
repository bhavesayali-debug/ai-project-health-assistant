# MVP Success Criteria

## Purpose

This document defines how Prototype 1 of the AI Project Health Assistant will be evaluated.

The goal is not simply to demonstrate that the AI can generate a project-status response.

The prototype must demonstrate that the response is useful, evidence-based, and sufficiently reliable to support a Project Manager.

---

## Overall MVP Success Statement

> **Prototype 1 will be considered successful if it can convert fragmented synthetic project information into a reliable, evidence-backed project-health view that allows a Project Manager to quickly understand overall project status and identify areas requiring attention.**

---

## Success Criterion 1 — Correct Project Health Assessment

The assistant should correctly classify project health as:

- Green
- Amber
- Red

based on the agreed RAG project-health rules and the available project evidence.

The assessment should consider:

- Severity
- Delivery impact
- Urgency
- Recoverability
- Supporting evidence

---

## Success Criterion 2 — Important Concerns Are Identified

The assistant should surface significant project-health signals such as:

- Major risks
- Active issues
- Critical blockers
- Important dependencies
- Milestone threats
- Overdue critical actions
- Significant delivery concerns

A meaningful project-health signal contained within the project information should not be missed simply because it appears in a less formal source such as meeting notes or stakeholder comments.

---

## Success Criterion 3 — Conclusions Are Evidence-Backed

Important conclusions should be supported by project information.

For example:

### Conclusion

> UAT is at risk.

### Supporting Evidence

- API integration is delayed.
- Vendor access remains unresolved.
- UAT begins next week.

The PM should be able to understand why the assistant reached its conclusion.

---

## Success Criterion 4 — No Unsupported Information

The assistant should not invent:

- Risks
- Issues
- Dates
- Milestones
- Dependencies
- Actions
- Project statuses
- Stakeholder concerns

that are not supported by the available project information.

If sufficient evidence is not available, the assistant should indicate uncertainty rather than fabricate an answer.

---

## Success Criterion 5 — Quick-Glance Usefulness

A Project Manager should be able to quickly understand:

- Overall project health
- What is at risk
- What requires attention
- Which milestones are affected
- Why the assistant reached its conclusion

without first reading a lengthy project-status report.

---

## Success Criterion 6 — Useful Follow-Up Responses

The assistant should provide useful answers to follow-up questions such as:

> Why is the project Amber?

> What are the top risks?

> Which milestones are at risk?

> Are there any overdue actions?

> What requires my attention this week?

The responses should remain grounded in the available synthetic project data.

---

## Evaluation Approach

Prototype 1 will be evaluated using controlled project-health scenarios with known expected outcomes.

Potential scenarios will include:

### Scenario 1 — Healthy Project

Expected result: **Green**

### Scenario 2 — Recoverable Delivery Concern

Expected result: **Amber**

### Scenario 3 — Significant Delivery Impact

Expected result: **Red**

### Scenario 4 — Conflicting Project Information

Different sources report inconsistent statuses.

### Scenario 5 — Stale Project Information

A formal tracker contains an older status while a newer project update indicates a change.

### Scenario 6 — Hidden Dependency

Information from multiple sources must be correlated to identify the delivery impact.

### Scenario 7 — Weak Risk Signal

An emerging concern appears in meeting notes before being formally recorded as a risk.

### Scenario 8 — Minor Delay With No Material Impact

The assistant should avoid unnecessarily changing overall project health.

### Scenario 9 — Missing Information

The assistant should communicate uncertainty where evidence is insufficient.

### Scenario 10 — Unsupported Question

The assistant should avoid inventing information that does not exist in the project dataset.

Additional scenarios may be added during testing.

---

## Expected vs. Actual Evaluation

For each test scenario, the evaluation will compare:

**Expected Project Health**

vs.

**AI Project Health Assessment**

and review:

- Correct health classification
- Concerns identified
- Concerns missed
- Supporting evidence used
- Unsupported claims
- Quality of PM attention recommendations

---

## Human Evaluation

The final usefulness of the output will also be reviewed from a Project Manager perspective.

The key question will be:

> **Would this output help a Project Manager understand the project situation faster and know where to focus attention?**

---

## MVP Evaluation Principle

> **A convincing AI response is not enough. The response must be supported by the project data and useful for Project Manager decision-making.**
