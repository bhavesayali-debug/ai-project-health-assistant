# RAG Project Health Rules

## Purpose

This document defines the initial Green / Amber / Red project-health logic for Prototype 1 of the AI Project Health Assistant.

The goal is to provide consistent guidance for how project health should be assessed based on available project evidence.

---

## GREEN — On Track

A project should be considered **Green** when:

- Key milestones are on schedule
- Current progress supports committed delivery dates
- No significant unresolved blockers exist
- Identified risks are low, controlled, or adequately mitigated
- No major delivery concerns have been reported
- Minor issues can be handled through normal team activities
- No material impact to schedule, scope, or quality is currently expected

### Green Summary

> **The project is progressing as planned, with no material threat to committed delivery.**

---

## AMBER — Attention Required

A project should be considered **Amber** when:

- A key activity or milestone is delayed or at risk
- Important blockers or dependencies remain unresolved
- Risks could affect delivery if not addressed
- PM follow-up, escalation, or corrective action is required
- A realistic recovery path still exists
- The team can reasonably return the project to plan without major re-planning
- Potential schedule, scope, or quality impact exists but has not yet become unavoidable

### Amber Summary

> **The project has delivery concerns requiring attention, but timely corrective action can still bring it back on track.**

---

## RED — Immediate Intervention Required

A project should be considered **Red** when:

- A critical milestone or committed deadline has been missed or is highly likely to be missed
- A critical blocker remains unresolved
- A major risk has become an active issue
- Significant delivery impact is occurring or unavoidable
- Existing recovery actions are insufficient
- Major re-planning, leadership intervention, or a significant project decision is required
- No credible short-term recovery path exists through normal team-level corrective action

### Red Summary

> **The project has a material delivery problem requiring immediate intervention or significant corrective action.**

---

## Project Health Assessment Factors

The assistant should not determine project health from one isolated project update.

The assessment should consider the combination of:

### Severity

How serious is the concern?

### Delivery Impact

Could the concern materially affect schedule, scope, quality, or an important milestone?

### Urgency

How soon could the concern affect delivery?

### Recoverability

Can the project team reasonably resolve the concern and return the project to plan?

### Supporting Evidence

Is there sufficient project information supporting the health assessment?

---

## Example — Green

### Project Information

- Development milestone is on schedule
- No critical defects are open
- Current sprint is progressing as planned
- Existing risks have mitigation plans
- UAT remains scheduled as planned

### Assessment

**GREEN**

### Reason

The project is progressing according to plan with no material threat to committed delivery.

---

## Example — Amber

### Project Information

- API integration is two days behind schedule
- Vendor access remains unresolved
- UAT begins in three days
- The team has identified a recovery plan if access is received within the next two days

### Assessment

**AMBER**

### Reason

The unresolved dependency could affect UAT, but a realistic recovery path still exists.

---

## Example — Red

### Project Information

- API integration is incomplete
- UAT cannot begin
- The committed release date is expected to slip
- The critical dependency has no confirmed resolution date
- No approved recovery plan exists

### Assessment

**RED**

### Reason

A critical delivery milestone is impacted and the project currently has no credible recovery path.

---

## Important MVP Rule

> **One delayed task does not automatically make a project Amber or Red.**

The assistant must evaluate context, severity, urgency, delivery impact, recoverability, and supporting evidence before assigning overall project health.

---

## Human-in-the-Loop Principle

The AI Project Health Assistant provides an evidence-based assessment to support the Project Manager.

The final project-health judgment and any resulting escalation or delivery decision remain the responsibility of the Project Manager.
