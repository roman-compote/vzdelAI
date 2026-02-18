---
title: Research Questionnaire Design
req-id: REQ-FUNC-S04
status: draft
priority: could
category: functional
subcategory: student
source-section: "8.2"
source-type: extracted
activity:
  - 1
partners:
  - aricoma
milestone: M5
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
---

# REQ-FUNC-S04: Research Questionnaire Design

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall assist students in formulating clear, neutral, and targeted research questions for their seminar papers and research projects. It shall help design questionnaire items that avoid bias and align with research methodology best practices.

## Key Capabilities

- Help formulate research questions aligned with the student's topic
- Suggest questionnaire items with proper phrasing (neutral, unambiguous)
- Identify potential bias in draft questions
- Recommend appropriate question types (Likert, open-ended, multiple choice)
- Provide basic guidance on research methodology alignment

## Acceptance Criteria

- [ ] System generates questionnaire suggestions given a research topic description
- [ ] Generated questions are neutral and free of leading language
- [ ] System explains why certain formulations are preferred over others
- [ ] Output exportable in a structured format for use in survey tools

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM for question generation and bias detection

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant) |
| **Partner** | Aricoma |
| **Milestone** | M5 (deployment methodology ready) |

> [!question] Open Questions
> - Should this feature integrate with specific survey tools (e.g., MS Forms)?
> - What research methodology standards should guide the recommendations?
> - Is ethical review guidance (IRB-equivalent) in scope?
