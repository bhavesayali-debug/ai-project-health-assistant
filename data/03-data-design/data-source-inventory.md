# Data Source Inventory

## Project

**AI Project Health Assistant**

## Scenario

**Scenario 01 — Online Banking Upgrade Project**

The purpose of Scenario 01 is to test whether the AI can combine fragmented project information from multiple sources and produce a reliable, evidence-based project health assessment.

The project information is intentionally distributed across different sources. Some information is current, some is stale, and some signals only become meaningful when correlated with other sources.

---

## Data Sources

| # | Data Source | What It Represents | Primary Information |
|---|---|---|---|
| 1 | Jira Feature Snapshot | Structured delivery tracking | Feature status, owner team, delivery stage, planned production date, blockers |
| 2 | Weekly Delivery Team Update | Cross-functional team context | Current progress, emerging concerns, assumptions and recovery expectations |
| 3 | Risk & Issue Register | Formal governance tracking | Known risks, issues, impact, ownership, mitigation and last-update date |
| 4 | Project Status Meeting Notes | Human project discussion | Stakeholder concerns, decisions, verbal risks and actions |
| 5 | Defect Tracker | Quality information | SIT/UAT/production defects, severity, status and affected feature |
| 6 | Milestone & Release Plan | Approved delivery baseline | Sprint dates, milestone dates and production commitments |
| 7 | Action & Dependency Tracker | Delivery dependencies and actions | External/technical dependencies, overdue actions, ownership and escalation |
| 8 | Executive Status Update | Previously communicated management status | Historical RAG status and executive-level project view |

---

## Why Multiple Sources Are Required

No individual source provides the complete project-health picture.

For example, Jira may show that Fund Transfer is in SIT, but it may not fully explain:

- why some testing cannot continue,
- whether an external dependency is overdue,
- how close the feature is to its milestone,
- whether stakeholders have raised concerns,
- or whether the formal risk register is stale.

The AI therefore needs to correlate information across sources rather than simply summarize each document independently.

---

## Expected Cross-Source Reasoning

### Beneficiary-Validation Dependency Example

The AI should connect:

**Jira Feature Snapshot**
- Beneficiary Management is Blocked.
- Fund Transfer is in SIT.

**Weekly Delivery Team Update**
- Some Fund Transfer scenarios cannot be completed.
- Vendor availability date is not confirmed.

**Risk & Issue Register**
- Vendor access was expected by August 10.
- Related entries were last updated August 5.

**Project Status Meeting Notes**
- August 10 has passed without access.
- Stakeholder confidence in the September 4 Fund Transfer release has been questioned.

**Milestone & Release Plan**
- Fund Transfer SIT completion is planned for August 21.
- Production is planned for September 4.

**Action & Dependency Tracker**
- The vendor recovery-date action is overdue.
- The external dependency remains unresolved.

The AI should recognize this combination as a meaningful delivery risk without claiming that the September 4 release will definitely be missed.

---

## Recency Reasoning

When information differs between sources, the AI should consider the date and context of each source.

For example:

- August 7 Executive Status Update → Overall Green
- August 5 Risk Register → API expected August 10
- August 11 Meeting Notes → API still unavailable
- August 12 Weekly Delivery Update → still no confirmed availability date

The newer evidence should influence the current project-health assessment more strongly than the older project status.

---

## Severity and Delivery Impact

The AI should not treat every project problem equally.

Examples:

- A Low-severity cosmetic production defect should not materially affect overall project health.
- Medium UAT defects with credible fixes should be monitored but should not automatically change overall project health.
- An unresolved external dependency affecting a near-term testing milestone may materially affect delivery health.

Assessment should consider:

- Severity
- Delivery impact
- Urgency
- Recoverability
- Milestone proximity
- Supporting evidence

---

## Human-in-the-Loop Principle

The AI Project Health Assistant provides analysis, evidence and recommendations.

The Project Manager remains responsible for:

- Final project-health decisions
- Escalation
- Schedule changes
- Scope decisions
- Stakeholder communication
- Corrective actions

The AI supports Project Manager judgment rather than replacing it.
