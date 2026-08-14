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

---

# Decision 3 — LLM / Reasoning Model

## Selected Technology

**OpenAI Responses API**

**Initial Model:** GPT-5.6

---

## Why OpenAI Responses API

The Responses API will be used as the main interface between the application and the language model.

For the MVP, the model needs to:

- Analyze retrieved project evidence
- Correlate information across multiple sources
- Consider stale and conflicting information
- Apply project-health reasoning rules
- Distinguish facts from potential impacts
- Identify uncertainty
- Produce evidence-backed conclusions
- Return a structured result for the dashboard

---

## Initial Model Choice

The first implementation will use:

**GPT-5.6**

The initial priority is reasoning quality and reliability rather than minimizing model cost.

Scenario 01 and future controlled evaluation scenarios will be used to determine whether the selected model produces acceptable project-health assessments.

---

## Reasoning Configuration

The MVP should begin with a balanced reasoning configuration.

The model should be given:

- Retrieved project evidence
- Project-health RAG rules
- Assessment date
- Source dates and metadata
- Required output schema
- Clear instructions not to invent unsupported project information

Reasoning effort may later be adjusted based on evaluation results.

---

## Structured Output

The model response should use the structured project-health schema defined in:

`project-health-output-schema.md`

Structured output will be used so that the application can reliably extract:

- Overall RAG
- Executive summary
- Primary driver
- Key concerns
- Feature health
- PM actions
- Supporting evidence
- Uncertainty
- Assessment metadata

The dashboard should consume this structured result rather than attempting to interpret a free-form AI response.

---

## Model Evaluation Strategy

GPT-5.6 is the starting model, not an assumption that it is automatically the best long-term choice.

Once the evaluation framework is working, the project may compare:

- Reasoning quality
- Ground-truth accuracy
- Unsupported claims
- Latency
- Token usage
- Cost

across different model configurations.

A lower-cost model may later be used if it meets the required quality threshold.

---

## MVP Design Principle

Model selection should be evidence-driven.

The project should first establish a reliable quality baseline and then optimize cost and latency without materially reducing project-health assessment quality.
