---
title: Interactive Student Consultations
req-id: REQ-FUNC-T04
status: draft
priority: must
category: functional
subcategory: teacher
source-section: "8.1"
source-type: extracted
activity:
  - 1
  - 2
partners:
  - aricoma
  - comtec
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - platform/teams
---

# REQ-FUNC-T04: Interactive Student Consultations

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The AI assistant shall handle frequently asked student questions autonomously within MS Teams, reducing repetitive consultation load on teachers. When the assistant's confidence is below a defined threshold, it shall escalate the query to the teacher with full context.

## Key Capabilities

- Answer common student questions using course-specific knowledge base
- Operate as a chatbot within MS Teams channels and direct messages
- Detect low-confidence responses and escalate to the teacher with full conversation context
- Log all interactions for analytics and quality improvement
- Support subject-specific AI avatars/assistants in dedicated Teams channels

## Acceptance Criteria

- [ ] AI assistant answers FAQs with verified accuracy above a defined threshold
- [ ] Escalation to teacher occurs when confidence is below threshold, with full context attached
- [ ] Students can interact via Teams chat (channel and direct message)
- [ ] User satisfaction measured via Likert scale and questionnaires (§9 target)
- [ ] Interaction logs available for teacher review

## Dependencies

- [[REQ-INT-01-teams-bot|REQ-INT-01]]: MS Teams bot framework for chat interface
- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM foundation for response generation
- [[REQ-TECH-02-agent-architecture|REQ-TECH-02]]: Agent architecture for workflow management

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1, §6-Act2 |
| **Activity** | 1 (AI Assistant), 2 (Teams Integration) |
| **Partner** | Aricoma, COMTEC |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - What confidence threshold triggers escalation to the teacher?
> - Should teachers be able to "train" the bot with approved answers to new questions?
> - How are subject-specific avatars configured and managed?
