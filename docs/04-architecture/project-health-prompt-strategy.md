# Project Health Prompt Strategy

## Project

**AI Project Health Assistant**

---

## Purpose

This document defines the instructions that will guide the AI when analyzing retrieved project evidence.

The retrieval layer finds relevant project information.

The reasoning prompt tells the AI how to interpret that information and produce a reliable project-health assessment.

The objective is not simply to summarize retrieved documents.

The AI must:

- Correlate evidence across sources
- Consider source recency
- Assess delivery impact
- Apply project-health rules
- Identify uncertainty
- Avoid unsupported conclusions
- Produce evidence-backed recommendations

---

# Prompt Architecture

The AI request will contain four main inputs:

1. System / role instructions
2. Project-health reasoning rules
3. Retrieved project evidence
4. Project Manager question

Conceptually:

```text
Project Health Instructions
          +
RAG / Reasoning Rules
          +
Retrieved Evidence
          +
PM Question
          ↓
      AI Model
          ↓
Structured Project Health Assessment
