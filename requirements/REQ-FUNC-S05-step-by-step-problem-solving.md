---
title: Step-by-Step Problem Solving
req-id: REQ-FUNC-S05
status: draft
priority: must
category: functional
subcategory: student
source-section: "8.2"
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

# REQ-FUNC-S05: Step-by-Step Problem Solving

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall guide students through calculations and problem-solving exercises step by step, showing intermediate results and explanations at each stage. This supports the Socratic method approach, helping students understand the reasoning process rather than just providing final answers.

## Key Capabilities

- Break down complex problems into sequential, understandable steps
- Show intermediate calculations with explanations for each step
- Adapt explanation depth based on student's demonstrated understanding
- Support Economics and Finance domain problems (financial calculations, statistical methods)
- Allow students to attempt each step before revealing the solution
- Provide hints when students are stuck rather than immediate answers

## Acceptance Criteria

- [ ] System decomposes problems into clearly explained sequential steps
- [ ] Intermediate results are shown and explained at each stage
- [ ] Student can attempt each step independently before requesting the solution
- [ ] Supports domain-specific problem types for Economics and Finance courses
- [ ] Explanation depth adapts to student interaction patterns

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM fine-tuned for mathematical and financial reasoning
- [[REQ-TECH-02-agent-architecture|REQ-TECH-02]]: Agent architecture for multi-turn guided interactions

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant) |
| **Partner** | Aricoma |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - What problem types should be prioritized for Economics and Finance courses?
> - How should the system handle incorrect student attempts (corrective feedback)?
> - Should step-by-step solutions be saveable for later review?
