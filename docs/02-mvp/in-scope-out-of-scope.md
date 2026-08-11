# MVP Scope

## Purpose

This document defines the scope boundaries for Prototype 1 of the AI Project Health Assistant.

The MVP is deliberately limited to validating the core project-health use case before introducing enterprise integrations or additional automation.

---

## In Scope — Prototype 1

### One Synthetic Software Project

The prototype will initially support one preloaded synthetic software project.

### Synthetic Project Information

The project dataset may include:

- Jira-style updates
- Sprint updates
- Meeting notes
- Risks
- Issues
- Blockers
- Dependencies
- Milestones
- Defects
- Action items
- Stakeholder comments

### Project Health Assessment

The assistant will provide an overall project-health assessment using:

- Green
- Amber
- Red

### Graphical Project Health Summary

The prototype will provide a quick-glance project-health view showing information such as:

- Overall health
- Milestone health
- Risks
- Issues
- Blockers
- Overdue actions
- Top concerns
- PM attention required

### Detailed Project Health Explanation

The assistant will provide supporting detail explaining the project-health assessment.

### Evidence-Based Conclusions

Important conclusions should be linked to supporting project information.

### Project Health Follow-Up Questions

The PM can ask questions about:

- Risks
- Issues
- Milestones
- Dependencies
- Overdue actions
- Project-health rating
- Areas requiring attention

### Human-in-the-Loop

The AI provides analysis and decision support.

The Project Manager retains final decision-making responsibility.

---

## Out of Scope — Prototype 1

The following capabilities will deliberately not be included in the first prototype.

### Live Enterprise Integrations

No direct integrations with:

- Jira
- Confluence
- SharePoint
- ServiceNow
- Microsoft Teams
- Outlook
- Other enterprise platforms

### Multiple Project Management

Prototype 1 will focus on one synthetic project.

### Automatic Project Decisions

The AI will not independently:

- Change project status
- Approve scope changes
- Re-plan milestones
- Change delivery dates
- Assign resources
- Make escalation decisions

### Automated Escalations

The assistant will not automatically send:

- Emails
- Teams messages
- Management alerts
- Escalations

### Modification of Source Systems

Prototype 1 will be read-only from a project-data perspective.

### Enterprise Authentication and Authorization

Capabilities such as:

- Single Sign-On
- Role-based access
- Enterprise identity management

will remain outside Prototype 1.

### Detailed Financial Management

Detailed project-budget and financial-health analysis will not be included in the initial prototype.

### Multiple Autonomous AI Agents

Prototype 1 will not use a complex multi-agent architecture unless later technical evaluation demonstrates that it is necessary.

### Automated Project Schedule Changes

The assistant will not automatically modify project schedules or milestone dates.

---

## Scope Principle

> **Prototype 1 will validate the usefulness and reliability of AI-assisted project-health analysis before investing in enterprise integrations and broader automation.**

---

## Why the Scope Is Intentionally Small

The objective of Prototype 1 is not to build a complete enterprise Project Management platform.

The first question to validate is:

> **Can AI reliably convert fragmented project information into an evidence-backed view of project health that is useful to a Project Manager?**

If that core capability proves valuable, additional functionality can be considered in later versions.
