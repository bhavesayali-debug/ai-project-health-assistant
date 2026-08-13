# Project Health Output Schema

## Project

**AI Project Health Assistant**

---

## Purpose

The AI Project Health Assistant should return project-health results in a consistent structured format.

The structured output will allow the application to:

- Display an overall RAG status
- Build a quick-glance dashboard
- Show prioritized concerns
- Highlight feature and milestone health
- Present PM attention items
- Display supporting evidence
- Communicate uncertainty clearly

The AI may later generate a human-readable explanation from the same structured result.

---

## Output Structure

The project-health assessment should contain the following sections:

1. Overall Project Health
2. Executive Summary
3. Key Concerns
4. Feature / Milestone Health
5. PM Attention Required
6. Supporting Evidence
7. Uncertainty
8. Assessment Metadata

---

## Proposed JSON Structure

```json
{
  "overall_health": {
    "rag": "GREEN | AMBER | RED",
    "label": "On Track | At Risk but Recoverable | Material Delivery Impact",
    "confidence": "HIGH | MEDIUM | LOW"
  },

  "executive_summary": "Short explanation of the current project-health position.",

  "primary_driver": {
    "title": "Main reason driving the overall health assessment",
    "impact": "Short explanation of why this matters",
    "affected_features": []
  },

  "key_concerns": [
    {
      "priority": 1,
      "title": "Concern title",
      "severity": "LOW | MEDIUM | HIGH | CRITICAL",
      "delivery_impact": "LOW | MEDIUM | HIGH",
      "urgency": "LOW | MEDIUM | HIGH",
      "recoverability": "HIGH | MEDIUM | LOW",
      "status": "MONITOR | AT_RISK | MATERIAL_IMPACT",
      "explanation": "Why this concern matters"
    }
  ],

  "feature_health": [
    {
      "feature": "Feature name",
      "current_stage": "Development | SIT | UAT | Production | Blocked | Not Started",
      "health": "ON_TRACK | MONITOR | AT_RISK | MATERIAL_IMPACT",
      "milestone": "Relevant milestone",
      "milestone_date": "YYYY-MM-DD",
      "reason": "Short explanation"
    }
  ],

  "pm_attention_required": [
    {
      "priority": 1,
      "action": "Recommended PM follow-up",
      "reason": "Why the action is required"
    }
  ],

  "supporting_evidence": [
    {
      "source": "Source name",
      "source_date": "YYYY-MM-DD",
      "related_feature": "Feature name or null",
      "evidence": "Relevant project fact",
      "supports": "Conclusion supported by this evidence"
    }
  ],

  "uncertainty": [
    {
      "topic": "Area where information is incomplete",
      "known": "What is confirmed",
      "unknown": "What is not yet known",
      "impact": "How the uncertainty affects the assessment"
    }
  ],

  "assessment_metadata": {
    "assessment_date": "YYYY-MM-DD",
    "sources_considered": [],
    "stale_sources_detected": [],
    "conflicting_information_detected": true
  }
}
