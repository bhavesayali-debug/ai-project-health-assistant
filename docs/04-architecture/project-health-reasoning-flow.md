# Project Health Reasoning Flow

## Project

**AI Project Health Assistant**

---

## Purpose

This document defines how the AI should reason when the Project Manager asks:

**"What is the current status of this project?"**

The AI should not simply summarize documents.

It should retrieve relevant evidence, correlate information across sources, evaluate delivery impact, and produce an evidence-backed project-health assessment.

---

## Reasoning Flow

### Step 1 — Understand the Question

Identify that the user is asking for an overall project-health assessment.

Expected output should include:

- Overall RAG status
- Main health drivers
- Milestone / feature concerns
- Risks, issues and blockers
- PM attention required
- Supporting evidence
- Uncertainty where appropriate

---

### Step 2 — Retrieve Current Project Evidence

Retrieve relevant information across project sources, including:

- Current feature status
- Recent delivery updates
- Risks and issues
- Defects
- Dependencies
- Overdue actions
- Milestones
- Stakeholder concerns
- Previous executive status

The system should avoid relying on only one source.

---

### Step 3 — Determine Source Recency

For related or conflicting information:

1. Identify the source date.
2. Determine whether newer information supersedes older information.
3. Retain older information when it provides useful historical context.
4. Avoid treating outdated status as the current project position.

Example:

- August 7 Executive Status = Green
- August 12 delivery evidence = unresolved external dependency

The August 7 Green status should be treated as historical rather than automatically reused.

---

### Step 4 — Identify Material Signals

Review retrieved evidence for:

- Blockers
- Delivery delays
- High-impact dependencies
- Milestone threats
- Defects
- Overdue actions
- Emerging technical concerns
- Stakeholder concerns
- Missing or conflicting information

Not every signal should affect overall project health.

---

### Step 5 — Assess Each Signal

Evaluate important signals using:

**Severity**
- How serious is the problem?

**Delivery Impact**
- Does it threaten scope, schedule, quality or a committed milestone?

**Urgency**
- How soon could the impact occur?

**Recoverability**
- Is there a credible recovery path?

**Milestone Proximity**
- How close is the affected feature to its planned milestone?

**Supporting Evidence**
- Is the concern supported by one or multiple reliable project sources?

---

### Step 6 — Correlate Related Evidence

The AI should combine related information rather than assess each item independently.

Example:

External beneficiary API unavailable

+

Fund Transfer depends on beneficiary validation

+

Some SIT scenarios cannot be completed

+

SIT completion target is August 21

+

Vendor recovery date is overdue

+

Stakeholder confidence has been questioned

=

Meaningful Fund Transfer delivery risk

---

### Step 7 — Determine Feature-Level Health

For each material feature, determine whether it is:

- On Track
- At Risk
- Materially Impacted

Feature health should be based on evidence and delivery impact rather than task status alone.

Examples:

**Transaction History**
Medium defects exist, but fixes are planned and no current milestone impact is expected.

Expected interpretation:
**On Track / Monitor**

**Fund Transfer**
Testing is partially blocked by an unresolved dependency close to its SIT milestone.

Expected interpretation:
**At Risk**

---

### Step 8 — Determine Overall Project RAG

Apply the agreed project-health rules.

## GREEN — On Track

Use Green when:

- Key milestones remain achievable.
- No material unresolved blockers threaten delivery.
- Risks are controlled.
- Current progress supports committed dates.

---

## AMBER — At Risk but Recoverable

Use Amber when:

- A meaningful delivery risk, blocker or dependency exists.
- PM follow-up or corrective action is required.
- A milestone may be affected.
- A realistic recovery path still exists.

---

## RED — Material Delivery Impact

Use Red when:

- A critical milestone has been missed or is highly likely to be missed.
- A critical blocker remains unresolved.
- Significant delivery impact is confirmed.
- No credible short-term recovery path exists.
- Major re-planning or leadership intervention is required.

---

## Important Rule

A single delayed task, open defect, blocked item or overdue action does not automatically determine overall project health.

Overall RAG should reflect material delivery impact.

---

### Step 9 — Identify PM Attention Required

The system should recommend the areas requiring PM action.

Examples:

- Confirm vendor recovery date.
- Complete schedule-impact assessment.
- Escalate unresolved dependency.
- Monitor emerging technical issue.
- Confirm whether contingency remains.

Recommendations should be grounded in the project evidence.

---

### Step 10 — Build the Response

The final response should follow this structure:

## Overall Project Health

GREEN / AMBER / RED

## Why

Short executive explanation of the main drivers.

## Key Concerns

Prioritized concerns based on delivery impact.

## Milestone / Feature Health

Important features and whether they are on track or at risk.

## PM Attention Required

Specific follow-up actions.

## Supporting Evidence

Source-backed evidence supporting important conclusions.

## Uncertainty

Clearly identify where evidence is incomplete or where future impact cannot yet be confirmed.

---

## Expected Scenario 01 Result

For Scenario 01, the expected overall assessment is:

**AMBER — At Risk but Recoverable**

The primary driver is the unresolved beneficiary-validation dependency affecting Fund Transfer testing.

The AI should not claim that the September 4 production date will definitely be missed because there is not yet sufficient evidence for that conclusion.

---

## Design Principle

The purpose of the reasoning flow is not to make the AI act as the Project Manager.

The AI should organize evidence, highlight material delivery signals and explain its reasoning so that the Project Manager can make an informed decision.
