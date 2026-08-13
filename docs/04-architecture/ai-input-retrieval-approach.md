# AI Input & Retrieval Approach

## Project

**AI Project Health Assistant**

---

## Architecture Goal

The prototype must allow a Project Manager to ask natural-language questions about project health while receiving conclusions grounded in project evidence.

The system should correlate information across multiple project sources rather than relying on one document or simply summarizing files independently.

---

## MVP Architecture Decision

The MVP will use a single retrieval-and-reasoning pipeline.

The architecture will not use multiple specialized AI agents.

The objective of the first prototype is to validate whether AI can reliably retrieve, correlate and reason over fragmented project information.

---

## High-Level Flow

Project Data Sources

→ Document Ingestion

→ Logical Chunking

→ Metadata Enrichment

→ Searchable Project Knowledge Store

→ User Question

→ Evidence Retrieval

→ Project-Health Reasoning

→ Structured Health Assessment

→ Dashboard, Explanation and Supporting Evidence

---

## Project Data Input

Scenario 01 currently contains eight synthetic project sources:

1. Jira Feature Snapshot
2. Weekly Delivery Team Update
3. Risk & Issue Register
4. Project Status Meeting Notes
5. Defect Tracker
6. Milestone & Release Plan
7. Action & Dependency Tracker
8. Executive Status Update

Only project input data will be made available to the AI.

Evaluation ground-truth files must remain outside the AI retrieval path.

---

## Document Processing

Documents will be divided into logical sections rather than treated only as complete files.

Example sections may include:

- Feature updates
- Risks
- Issues
- Defects
- Dependencies
- Actions
- Milestones
- Stakeholder concerns
- Executive status information

---

## Metadata

Each project-information chunk should retain metadata that helps the system understand its context.

Example metadata:

- Scenario ID
- Source name
- Source type
- Source date
- Feature
- Project
- Information category

Metadata can later help with retrieval, filtering, recency reasoning and evidence attribution.

---

## Retrieval

When the Project Manager asks a question, the system should retrieve relevant evidence from the project knowledge store.

Example:

"What are the main risks to Fund Transfer?"

Relevant information may be retrieved from:

- Jira
- Weekly Delivery Team Update
- Risk Register
- Meeting Notes
- Defect Tracker
- Milestone Plan
- Dependency Tracker

The system should not assume that the answer exists in only one source.

---

## Project-Health Reasoning

Retrieved evidence will be passed to the AI together with project-health reasoning instructions.

The AI should consider:

- Severity
- Delivery impact
- Urgency
- Recoverability
- Milestone proximity
- Dependencies
- Source recency
- Supporting evidence

The AI should distinguish:

- Confirmed facts
- Emerging concerns
- Potential impacts
- Unsupported conclusions

---

## Recency Handling

Newer project evidence should generally be given greater weight when it supersedes older status information.

For example:

August 7:
Executive Status = Green

August 12:
Vendor dependency remains unresolved.

The AI should recognize that an older executive status may no longer represent current project health.

---

## Evidence Requirement

Important conclusions should reference the project evidence supporting them.

The response should make it possible for the Project Manager to understand:

- What the AI concluded
- Why it reached that conclusion
- Which project information supports it
- Where uncertainty remains

---

## Human-in-the-Loop

The AI provides project-health analysis and recommendations.

The Project Manager retains responsibility for final:

- RAG status
- Escalation decisions
- Schedule changes
- Scope decisions
- Stakeholder communication
- Corrective actions

---

## MVP Design Principle

Keep the architecture simple enough to test the core hypothesis:

Can AI reliably turn fragmented project information into a useful, evidence-backed project-health view?

More complex capabilities such as multi-agent workflows and live enterprise integrations can be evaluated after the core concept is validated.
