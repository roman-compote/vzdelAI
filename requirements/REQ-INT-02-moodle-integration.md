---
title: Moodle LMS Integration
req-id: REQ-INT-02
status: draft
priority: must
category: integration
source-section: "5.7"
source-type: extracted
activity:
  - 2
  - 3
partners:
  - comtec
  - compote
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/integration
  - platform/moodle
---

# REQ-INT-02: Moodle LMS Integration

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 5.7

## Description

The system shall integrate with Moodle LMS via LTI 1.3 for content delivery and activity launching, and xAPI for learning analytics data collection. This enables the AI assistant to access course structure, deliver generated materials as Moodle activities, and collect interaction data for analytics.

## Key Capabilities

- LTI 1.3 integration for launching AI assistant activities within Moodle
- Deliver AI-generated content as Moodle-compatible resources (SCORM, quiz imports)
- xAPI event streaming for learning analytics (interactions, completions, scores)
- Access Moodle course structure and gradebook data (read-only, with authorization)
- Synchronize assignment deadlines and exam schedules to the AI assistant

## Acceptance Criteria

- [ ] LTI 1.3 tool successfully launches AI assistant from within Moodle courses
- [ ] AI-generated materials deployable as Moodle activities/resources
- [ ] xAPI events captured for key interactions (content access, quiz attempts, completions)
- [ ] Course deadlines and grades accessible for personalization features
- [ ] Integration tested with UNIZA's Moodle instance

## Dependencies

- [[REQ-TECH-05-content-transformation|REQ-TECH-05]]: Content transformation for Moodle-compatible output formats
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Student data from Moodle handled per GDPR
- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams bot as complementary access channel

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.7 |
| **Activity** | 2 (Teams Integration), 3 (RAG Pipeline) |
| **Partner** | COMTEC, COMPOTE |
| **Milestone** | M4 (integrated system) |

> [!question] Open Questions
> - What Moodle version is running at UNIZA?
> - Are there existing LTI integrations at UNIZA that can serve as reference?
> - What xAPI Learning Record Store (LRS) will be used?
> - How will Moodle admin permissions for the integration be managed?
