---
title: Practical Exercise Design Support
req-id: REQ-FUNC-T06
status: draft
priority: should
category: functional
subcategory: teacher
source-section: "8.1"
source-type: extracted
activity:
  - 1
partners:
  - aricoma
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - topic/pedagogy
---

# REQ-FUNC-T06: Practical Exercise Design Support

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The system shall generate structured practical exercise recommendations for teachers, including introductory theory segments, interactive discussion prompts, simulation scenarios, and reflection activities, tailored to the course topic and target student level.

## Key Capabilities

- Generate structured exercise plans with distinct phases (theory, discussion, simulation, reflection)
- Tailor exercises to specific course topics and student proficiency levels
- Provide ready-to-use exercise templates in editable formats
- Suggest time allocations for each exercise phase

## Acceptance Criteria

- [ ] System generates complete exercise structures with at least 4 phases
- [ ] Exercises are customizable by topic, duration, and student level
- [ ] Output available in editable document formats (DOCX, Markdown)
- [ ] Teacher can modify and save customized exercises back to the knowledge base

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM for generating exercise content
- [[REQ-TECH-05-content-transformation|REQ-TECH-05]]: Content transformation for output formatting

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1 |
| **Activity** | 1 (AI Assistant) |
| **Partner** | Aricoma |
| **Milestone** | M4 (integrated agent layer) |

> [!question] Open Questions
> - What exercise formats are most commonly used at Faculty PEDaS?
> - Should exercises include assessment rubrics?
> - How should simulation scenarios be validated for educational appropriateness?
