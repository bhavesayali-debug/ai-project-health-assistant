# MVP Definition

## Project

**AI Project Health Assistant**

## Purpose

The purpose of Prototype 1 is to validate whether AI can analyze fragmented project information and provide a Project Manager with a reliable, evidence-backed view of overall project health.

The MVP deliberately focuses on one core Project Manager responsibility:

> **Understanding overall project health and identifying delivery concerns that may require attention or escalation.**

---

## MVP Objective

The MVP will explore the following question:

> **Can AI analyze information from multiple project sources and provide a Project Manager with a reliable, quick-glance view of project health while explaining the evidence behind its conclusions?**

---

## A. Project Data

Prototype 1 will use **one preloaded synthetic software project**.

The synthetic project will contain realistic information representing data that could exist across enterprise project-management tools.

The dataset may include:

- Jira-style updates
- Sprint updates
- Meeting notes
- Risk information
- Issue information
- Project milestones
- Defects
- Dependencies
- Action items
- Stakeholder comments
- Project schedule information

No confidential or proprietary organizational data will be used.

In a future enterprise implementation, similar information could come from platforms such as Jira, Confluence, SharePoint, ServiceNow, Microsoft Teams, Outlook, project plans, and other organizational systems.

---

## B. Primary User Interaction

The Project Manager opens the AI Project Health Assistant with the synthetic project already available.

The primary MVP question is:

> **What is the current status of this project?**

The PM should not need to manually consolidate project information before asking this question.

---

## C. Main Project Health Output

The response will be divided into two layers.

### Layer 1 — Quick-Glance Graphical Project Health Summary

The PM should first see a concise visual summary containing:

- Overall Project Health — Green / Amber / Red
- Milestone Health
- Number of Risks
- Number of Issues
- Number of Blockers
- Number of Overdue Actions
- Top Project Concerns
- PM Attention Required

The purpose of this section is to allow the PM to quickly understand the overall situation without reading a lengthy report.

### Layer 2 — Detailed Project Health Explanation

Below the graphical summary, the assistant will provide:

- Executive Summary
- Key Risks and Issues
- Blockers and Dependencies
- Milestone Concerns
- PM Attention Required
- Supporting Evidence

The detailed section allows the PM to understand why the project received its health assessment.

---

## D. Follow-Up Questions

After viewing the overall project-health summary, the PM can ask follow-up questions such as:

> Why is the project Amber?

> What are the top project risks?

> Which milestones are at risk?

> Are there any overdue actions?

> What requires my attention this week?

> What evidence supports this concern?

The assistant should answer these questions using information available within the synthetic project dataset.

---

## Supporting Evidence Principle

An important project-health conclusion should not be presented without supporting information.

For example:

**Conclusion**

> UAT is at risk.

**Supporting Evidence**

- API integration is delayed.
- Vendor API access remains unresolved.
- UAT is scheduled to begin next week.

The assistant should make the relationship between project evidence and its conclusion understandable to the PM.

---

## Human-in-the-Loop Principle

The AI Project Health Assistant supports Project Manager judgment.

It does not replace it.

The assistant may:

- Identify potential concerns
- Correlate information
- Highlight delivery signals
- Summarize project health
- Suggest areas requiring review

The Project Manager remains responsible for:

- Final project-health assessment
- Escalation decisions
- Delivery decisions
- Scope decisions
- Schedule decisions
- Stakeholder communication

---

## MVP Experience

The Prototype 1 experience can be summarized as:

**Synthetic Project Information**

↓

**AI analyzes and correlates project signals**

↓

**PM asks: "What is the current status of this project?"**

↓

**Graphical Project Health Summary**

↓

**Detailed Explanation + Supporting Evidence**

↓

**PM asks follow-up questions**

↓

**PM reviews the information and decides appropriate actions**

---

## MVP Value Proposition

Prototype 1 aims to demonstrate that fragmented project information can be converted into a concise, actionable, and evidence-backed project-health view that helps a Project Manager quickly understand:

> **What is happening, what requires attention, and why.**
