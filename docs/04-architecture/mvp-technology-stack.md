# MVP Technology Stack

## Project

**AI Project Health Assistant**

---

## Technology Selection Principle

Technology choices for the MVP should prioritize:

- Simplicity
- Fast prototype development
- Explainability
- Ease of testing
- Low operating cost
- Portfolio/demo usability
- Ability to evolve toward a more enterprise-ready architecture later

The MVP should avoid unnecessary infrastructure until the core AI project-health hypothesis has been validated.

---

# Decision 1 — Application Language

## Selected Technology

**Python**

## Why Python

Python will be used for the core application because it provides a simple development environment for:

- AI / LLM integration
- Document ingestion
- Text processing
- Retrieval
- Structured data handling
- Evaluation
- Backend orchestration

Using one language across these components keeps the MVP architecture simple and easier to maintain.

---

# Decision 2 — User Interface

## Selected Technology

**Streamlit**

## Why Streamlit

Streamlit will be used to build the initial Project Manager dashboard and conversational interface.

It supports rapid development of interactive Python applications and provides capabilities useful for the MVP, including:

- Dashboard components
- Charts and metrics
- Chat input and message components
- Session state
- Expandable evidence sections
- Multipage application support

Using Streamlit allows the prototype to focus engineering effort on project-health reasoning, retrieval and evaluation rather than building a separate frontend application.

---

## MVP UI Responsibilities

The Streamlit application will eventually display:

- Overall project RAG status
- Executive summary
- Quick project metrics
- Key concerns
- Feature / milestone health
- PM attention required
- Supporting evidence
- Follow-up question interface

---

## Architecture Note

For the MVP, Streamlit may act as both the presentation layer and lightweight application layer.

The internal Python logic should still be separated into modules for:

- Ingestion
- Retrieval
- AI reasoning
- Output validation
- Evaluation

This keeps the prototype simple without tightly coupling all business logic to the user interface.
