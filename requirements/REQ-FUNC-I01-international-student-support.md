---
title: International Student Support
req-id: REQ-FUNC-I01
status: draft
priority: should
category: functional
subcategory: international
source-section: "8.3"
source-type: extracted
activity:
  - 1
  - 2
partners:
  - aricoma
  - comtec
milestone: M5
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - topic/ux
---

# REQ-FUNC-I01: International Student Support

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.3

## Description

The system shall support international students through translation and summarization of study materials into their native language, guidance on academic system navigation (course registration, exam enrollment, administrative communication), and social integration support. Multilingual operation shall be demonstrated in English, German, Spanish, and Russian.

## Key Capabilities

- Translate and summarize study materials into student's native language
- Guide students through academic processes (registration, enrollment, administration)
- Provide social integration information (student activities, cultural events, campus orientation)
- Operate in at least 4 languages: English, German, Spanish, Russian (plus Slovak)
- Adapt communication style for non-native Slovak speakers

## Acceptance Criteria

- [ ] System operates in at least 4 languages beyond Slovak (EN, DE, ES, RU)
- [ ] Study material translation maintains academic accuracy and terminology
- [ ] Navigation guidance covers core academic processes at UNIZA
- [ ] International student adaptation measured via structured interviews and questionnaires (§9 target)
- [ ] Social integration information is current and regularly updated

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: Multilingual LLM capabilities
- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams bot for interaction delivery
- [[REQ-FUNC-S01-personalized-exam-preparation|REQ-FUNC-S01]]: Core student features as baseline

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.3 |
| **Activity** | 1 (AI Assistant), 2 (Teams Integration) |
| **Partner** | Aricoma, COMTEC |
| **Milestone** | M5 (deployment methodology ready) |

> [!question] Open Questions
> - What is the acceptable translation quality threshold for academic materials?
> - How will social integration content be sourced and maintained?
> - Should the system support additional languages beyond the initial four?
