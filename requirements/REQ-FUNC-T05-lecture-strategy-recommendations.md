---
title: Lecture Strategy Recommendations
req-id: REQ-FUNC-T05
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

# REQ-FUNC-T05: Lecture Strategy Recommendations

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The system shall recommend lecture structures and teaching strategies that promote critical thinking, including comparative analysis approaches, practical exercises, role-play simulations, and discussion prompts tailored to course content and student level.

## Key Capabilities

- Analyze course content and learning objectives to suggest lecture structures
- Recommend pedagogical strategies: critical thinking exercises, comparative analysis, role-play, discussion prompts
- Adapt recommendations based on student engagement data and feedback
- Provide templates for interactive lecture segments

## Acceptance Criteria

- [ ] System generates at least 3 distinct strategy recommendations per lecture topic
- [ ] Recommendations include concrete activity descriptions, not just abstract strategies
- [ ] Strategies are aligned with course learning objectives
- [ ] Teacher can provide feedback to improve future recommendations

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM for generating pedagogical recommendations
- [[REQ-FUNC-T03-student-progress-monitoring|REQ-FUNC-T03]]: Student analytics data informs strategy adaptation

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1 |
| **Activity** | 1 (AI Assistant) |
| **Partner** | Aricoma |
| **Milestone** | M4 (integrated agent layer) |

> [!question] Open Questions
> - What pedagogical frameworks should guide the recommendation engine?
> - Should recommendations be validated by pedagogy experts before serving?
> - How should the system handle discipline-specific teaching conventions?
