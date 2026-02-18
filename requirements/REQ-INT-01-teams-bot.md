---
title: Microsoft Teams Bot Integration
req-id: REQ-INT-01
status: draft
priority: must
category: integration
source-section: "5.7, 6-Act2"
source-type: extracted
activity:
  - 2
partners:
  - comtec
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/integration
  - platform/teams
---

# REQ-INT-01: Microsoft Teams Bot Integration

> [!info] Source
> [[VzdelAI_Project_Description]] — Sections 5.7, 6 (Activity 2)

## Description

The system shall be implemented and integrated into Microsoft Teams as the primary user-facing interaction channel. This includes a chatbot interface in Teams channels and direct messages, subject-specific AI avatars/assistants in dedicated channels, collaboration and sharing features, and authentication via Microsoft Entra ID.

## Key Capabilities

- Azure Bot Services integration with MS Teams Bot Framework
- Chatbot interface in Teams channels (per-subject) and direct messages
- Subject-specific AI avatars/assistants deployed in dedicated Teams channels
- Rich message support (cards, adaptive cards, inline images, file attachments)
- Collaboration features: sharing AI responses, co-authoring with AI assistance
- Entra ID authentication and single sign-on (SSO) for seamless access
- Teams app manifest and admin-managed deployment

## Acceptance Criteria

- [ ] AI assistant accessible as a bot in MS Teams (channels and DMs)
- [ ] Subject-specific AI assistants deployed in at least 3 Teams channels
- [ ] Authentication via Entra ID with SSO — no separate login required
- [ ] Bot supports rich messages (adaptive cards, file attachments)
- [ ] Bot available on desktop, web, and mobile Teams clients
- [ ] User satisfaction measured via Likert scale questionnaires (§9 target)

## Dependencies

- [[REQ-TECH-02-agent-architecture|REQ-TECH-02]]: Agent layer provides the intelligence behind the bot
- [[REQ-NFR-04-scalability-security|REQ-NFR-04]]: Azure infrastructure for bot hosting
- [[REQ-INT-03-m365-ecosystem|REQ-INT-03]]: M365 services for SSO and data access

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.7, §6-Activity 2 |
| **Activity** | 2 (MS Teams Integration) |
| **Partner** | COMTEC |
| **Milestone** | M4 (integrated agent deployed in Teams) |

> [!question] Open Questions
> - What Teams admin policies are required for bot deployment at UNIZA?
> - How should the bot handle rate limiting and concurrent user sessions?
> - What is the fallback behavior when the bot service is unavailable?
