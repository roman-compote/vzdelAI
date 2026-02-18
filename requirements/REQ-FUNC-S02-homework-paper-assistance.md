---
title: Homework and Paper Assistance
req-id: REQ-FUNC-S02
status: draft
priority: must
category: functional
subcategory: student
source-section: "8.2"
source-type: extracted
activity:
  - 1
  - 3
partners:
  - aricoma
  - compote
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - topic/rag
---

# REQ-FUNC-S02: Homework and Paper Assistance

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall provide instant feedback to students on their homework and seminar papers, evaluating logical structure, argumentation quality, and language precision. It shall suggest supplementary materials to strengthen weak areas while ensuring academic integrity boundaries are maintained.

## Key Capabilities

- Analyze submitted text for logical structure and coherence
- Evaluate argumentation quality and identify logical gaps
- Check language precision and academic writing conventions
- Suggest supplementary materials and references to strengthen arguments
- Provide constructive, actionable feedback in natural language
- Maintain clear boundaries to prevent over-reliance (guidance, not ghost-writing)

## Acceptance Criteria

- [ ] Student receives structured feedback on submitted text within minutes
- [ ] Feedback covers structure, argumentation, and language dimensions
- [ ] Supplementary material suggestions are relevant and accessible
- [ ] System clearly delineates guidance from doing the work for the student
- [ ] Feedback quality validated by teacher review of sample interactions

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM for text analysis and feedback generation
- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline for supplementary material retrieval
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Student submissions must be handled per GDPR

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - What are the academic integrity boundaries for AI assistance on graded work?
> - Should feedback be visible to teachers or only to students?
> - How to handle submissions in Slovak vs. English?
