---
title: Assessment and Correction Support
req-id: REQ-FUNC-T02
status: draft
priority: must
category: functional
subcategory: teacher
source-section: "8.1"
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

# REQ-FUNC-T02: Assessment and Correction Support

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The system shall analyze student submissions (test answers, seminar papers) to provide preliminary assessment feedback. It shall highlight frequent errors, evaluate logical structure and argumentation, and detect potential AI-generated content that students may attempt to pass as their own work.

## Key Capabilities

- Analyze student test answers against rubric/answer key and highlight frequent errors
- Provide preliminary feedback on seminar papers (structure, argumentation, language precision)
- Detect AI-generated content in student submissions
- Aggregate error patterns across a class to identify common misconceptions
- Present results in a teacher-facing dashboard with actionable insights

## Acceptance Criteria

- [ ] System provides preliminary feedback on student submissions within a reasonable timeframe
- [ ] Frequent error patterns are identified and highlighted across a student cohort
- [ ] AI-generated content detection is available with configurable sensitivity
- [ ] Teacher can review and override all AI-generated assessments before release to students
- [ ] Minimum 70 teachers engaged with the assessment tooling (§9 target)

## Dependencies

- [[REQ-FUNC-T01-automated-material-generation|REQ-FUNC-T01]]: Test generation provides the assessment items to be evaluated
- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline needed for reference material retrieval during assessment
- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM foundation for text analysis and feedback generation

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M4 (integrated agent layer) |

> [!question] Open Questions
> - What level of assessment granularity is expected (per-question vs. holistic)?
> - How should AI-generated content detection results be communicated to teachers?
> - What rubric format should be supported for automated evaluation?
