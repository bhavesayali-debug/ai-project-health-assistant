# Evaluation & Testing Strategy

## Project

**AI Project Health Assistant**

---

## Purpose

This document defines how the AI Project Health Assistant will be tested and evaluated.

The objective is not simply to verify that the application produces a response.

The evaluation must determine whether the AI:

- Assesses project health correctly
- Identifies the right delivery concerns
- Prioritizes concerns appropriately
- Uses supporting project evidence
- Handles stale and conflicting information
- Avoids unsupported conclusions
- Communicates uncertainty appropriately
- Provides useful Project Manager attention items

---

# Evaluation Principle

The prototype will use controlled synthetic project scenarios with predefined expected outcomes.

Each scenario will contain:

1. Project input data available to the AI
2. A hidden ground-truth assessment
3. Expected important concerns
4. Expected evidence
5. Expected uncertainty
6. Conclusions the AI should avoid

The AI will receive only the project input data.

The hidden ground truth will be used only during evaluation.

---

# Ground Truth Separation

Ground-truth files are stored separately from project input data.

Example:

```text
data/
└── scenario-01/
    ├── 01-jira-feature-snapshot.md
    ├── 02-weekly-delivery-team-update.md
    ├── 03-risk-issue-register.md
    ├── 04-project-status-meeting-notes.md
    ├── 05-defect-tracker.md
    ├── 06-milestone-release-plan.md
    ├── 07-action-dependency-tracker.md
    └── 08-executive-status-update.md

evaluation/
└── ground-truth/
    └── scenario-01-ground-truth.md
```

Files under `evaluation/ground-truth/` must never be uploaded to or indexed in the project knowledge store used by the AI.

This prevents the model from seeing the expected answer before producing its assessment.

---

# Evaluation Flow

The evaluation process will follow this general flow:

```text
Synthetic Project Scenario
          ↓
AI Project Health Assistant
          ↓
Structured AI Assessment
          ↓
Evaluation Comparison
          ↑
Hidden Ground Truth
          ↓
Evaluation Results
```

---

# Scenario 01

## Project

**Online Banking Upgrade Project**

## Assessment Date

**August 12, 2026**

## Expected Overall Health

**AMBER — At Risk but Recoverable**

## Primary Expected Concern

The unresolved beneficiary-validation API dependency is affecting Fund Transfer testing and increasing delivery risk against the planned testing and production milestones.

The AI should recognize the risk without claiming that the September 4 production date will definitely be missed.

---

# Evaluation Dimensions

The AI assessment will be evaluated across the following dimensions.

---

## 1. Overall RAG Accuracy

Determine whether the AI selects the expected overall project-health status.

Possible results:

- Correct
- Incorrect

For Scenario 01:

```text
Expected: AMBER
```

Examples:

```text
AI Result: AMBER
Evaluation: PASS
```

```text
AI Result: GREEN
Evaluation: FAIL
```

```text
AI Result: RED
Evaluation: FAIL
```

RAG accuracy is one of the most important evaluation dimensions.

---

## 2. Primary Concern Identification

Determine whether the AI identifies the most important delivery concern.

For Scenario 01, the expected primary concern is:

**Beneficiary-validation API dependency affecting Fund Transfer testing.**

The AI does not need to use exactly the same wording.

The meaning must be equivalent.

---

## 3. Cross-Source Correlation

Determine whether the AI connects related evidence across project sources.

For Scenario 01, successful reasoning should connect information such as:

- Beneficiary Management is Blocked.
- Fund Transfer depends on beneficiary validation.
- Some Fund Transfer SIT scenarios cannot be completed.
- Vendor access was expected by August 10.
- Access remains unavailable.
- The vendor recovery date is not confirmed.
- Fund Transfer SIT is planned to complete August 21.
- Fund Transfer production is planned for September 4.
- Stakeholder confidence has been questioned.

The AI should recognize these as one connected delivery concern rather than unrelated project facts.

---

## 4. Recency Reasoning

Determine whether the AI appropriately handles older and newer information.

Scenario 01 intentionally contains:

```text
August 7:
Executive Status = GREEN

August 10:
Beneficiary API expected

August 11:
API still unavailable

August 12:
No confirmed recovery date
```

The AI should not blindly reuse the August 7 Green status.

Expected behavior:

The AI should recognize that newer project evidence has changed the current health position.

---

## 5. Concern Prioritization

Determine whether the AI distinguishes material concerns from ordinary delivery noise.

For Scenario 01:

### High-Priority Concern

- Beneficiary-validation dependency / Fund Transfer risk

### Watch Items

- Transaction Alerts event-service delays
- Transaction History Medium UAT defects
- Bill Payment requirement clarification

### Low Material Impact

- Account Dashboard cosmetic production defect
- Future Secure Messaging security review
- Features correctly scheduled as Not Started

A successful assessment should not give all issues equal importance.

---

## 6. Evidence Quality

Important AI conclusions should be supported by project evidence.

For each major conclusion, evaluate whether:

- The evidence comes from actual project input data.
- The evidence is relevant to the conclusion.
- The source can be identified.
- The source date is retained where useful.
- Multiple sources are connected where appropriate.

Example:

```text
Conclusion:
Fund Transfer is at risk.

Evidence:
Weekly Delivery Team Update — August 12
Project Status Meeting Notes — August 11
Milestone & Release Plan — August 7
Action & Dependency Tracker — August 12
```

---

## 7. Unsupported Claims / Hallucinations

The evaluation should identify statements that are not supported by available project evidence.

For Scenario 01, the AI should NOT claim that:

- September 4 will definitely be missed.
- Transaction History will miss its August 21 production date.
- Transaction Alerts will miss its October 2 date.
- Critical production defects exist.
- The entire project is failing.
- Major project re-planning has already been approved.
- The vendor has provided a confirmed recovery date.

Each unsupported material claim should be recorded as an evaluation failure.

---

## 8. Uncertainty Handling

Determine whether the AI clearly distinguishes between:

- What is known
- What is not known
- What may happen

For Scenario 01:

### Known

- Beneficiary API is unavailable.
- Fund Transfer testing is partially blocked.
- Vendor recovery date is not confirmed.
- SIT completion is planned for August 21.
- Production is planned for September 4.

### Unknown

- Exact vendor recovery date.
- Final Fund Transfer schedule impact.
- Whether September 4 will ultimately be missed.

Expected AI behavior:

The AI should describe September 4 as **at risk**, not as **definitely missed**.

---

## 9. PM Attention Quality

Determine whether recommendations are useful and supported by evidence.

For Scenario 01, appropriate PM attention items include:

- Obtain a confirmed vendor recovery date.
- Complete the Fund Transfer schedule-impact assessment.
- Determine remaining SIT and UAT contingency.
- Escalate the vendor dependency if recovery information remains unavailable.
- Continue monitoring the Transaction Alerts technical issue.

Recommendations should help the PM reduce uncertainty or manage delivery risk.

---

## 10. Human-in-the-Loop Compliance

The AI should support PM judgment rather than make management decisions independently.

The AI may recommend:

- Follow-up
- Investigation
- Escalation consideration
- Impact assessment
- Monitoring

The AI should not independently:

- Change delivery dates
- Approve scope changes
- Approve releases
- Escalate stakeholders
- Commit to a recovery plan
- Make the final project-health decision on behalf of the PM

---

# Initial Evaluation Scorecard

Each scenario will use the following scorecard.

| Evaluation Area | Result |
|---|---|
| Overall RAG Correct | PASS / FAIL |
| Primary Concern Identified | PASS / FAIL |
| Cross-Source Correlation | PASS / PARTIAL / FAIL |
| Recency Reasoning | PASS / FAIL |
| Concern Prioritization | PASS / PARTIAL / FAIL |
| Supporting Evidence | PASS / PARTIAL / FAIL |
| Unsupported Claims | PASS / FAIL |
| Uncertainty Handling | PASS / PARTIAL / FAIL |
| PM Attention Recommendations | PASS / PARTIAL / FAIL |
| Human-in-the-Loop Compliance | PASS / FAIL |

---

# Critical Failure Conditions

Some failures should be treated as more serious than others.

A scenario should not be considered successful if the AI:

- Produces the wrong overall RAG assessment
- Misses the primary material delivery concern
- Makes a major unsupported claim
- Ignores clearly newer evidence
- Claims certainty where the project information is uncertain
- Uses information from the hidden ground truth

These failures indicate that the core project-health reasoning is not yet reliable.

---

# Evaluation Phases

## Phase 1 — Manual Evaluation

During early development, AI results will be manually compared with the hidden ground truth.

This allows rapid identification of:

- Retrieval problems
- Prompt problems
- Reasoning problems
- Evidence gaps
- Output-structure problems

---

## Phase 2 — Automated Checks

Once the structured output is stable, Python-based automated checks can verify deterministic elements such as:

- Overall RAG
- Required output fields
- Expected primary feature or concern
- Presence of evidence
- Presence of uncertainty
- Source references
- Schema validity

Example:

```text
Expected overall_health.rag = AMBER

Actual overall_health.rag = AMBER

Result = PASS
```

---

## Phase 3 — Qualitative Review

Some dimensions cannot be evaluated reliably using exact string comparison.

Examples:

- Quality of executive summary
- Concern prioritization
- Evidence relevance
- PM action usefulness
- Quality of uncertainty explanation

These will initially be reviewed using a defined scoring rubric.

Automated qualitative evaluation may be explored later after the baseline evaluation approach is proven.

---

# Why Exact Text Matching Is Not Enough

The AI does not need to produce exactly the same wording as the ground-truth file.

For example:

Ground truth:

```text
The beneficiary-validation API dependency is creating delivery risk for Fund Transfer.
```

AI:

```text
Fund Transfer is at risk because required beneficiary-validation testing remains blocked by the unavailable external API.
```

These conclusions are semantically equivalent.

Evaluation should therefore focus on whether the AI reaches the correct project-health meaning rather than whether it reproduces specific sentences.

---

# Future Evaluation Scenarios

Scenario 01 validates an Amber project with stale information and an unresolved external dependency.

Additional scenarios should later test other situations.

Potential scenarios include:

```text
Scenario 01 — AMBER: Recoverable external dependency
Scenario 02 — GREEN: Normal delivery noise but no material impact
Scenario 03 — RED: Confirmed milestone impact with no recovery path
Scenario 04 — Conflicting project sources
Scenario 05 — Stale executive status
Scenario 06 — Hidden dependency
Scenario 07 — Insufficient project information
Scenario 08 — High-severity defect with limited delivery impact
Scenario 09 — Minor delay with no material milestone impact
Scenario 10 — Multiple moderate signals creating cumulative risk
```

The exact scenarios will be created incrementally rather than all at once.

---

# Evaluation Success Criteria

The MVP should demonstrate that the AI can reliably:

1. Identify overall project health.
2. Surface the most important delivery concern.
3. Connect related evidence across multiple sources.
4. Handle stale information correctly.
5. Prioritize material concerns.
6. Support conclusions with project evidence.
7. Avoid unsupported claims.
8. Communicate uncertainty.
9. Recommend useful PM attention items.
10. Maintain the human-in-the-loop model.

---

# Evaluation Design Principle

A convincing AI prototype should demonstrate not only what the system can generate, but also how its reliability is measured.

The evaluation framework is therefore a core part of the AI Project Health Assistant rather than an activity performed only after development is complete.
