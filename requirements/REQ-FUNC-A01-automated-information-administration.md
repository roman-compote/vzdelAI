---
title: Automated Information and Administration
req-id: REQ-FUNC-A01
status: draft
priority: could
category: functional
subcategory: admin
source-section: "8.4"
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
  - topic/integration
---

# REQ-FUNC-A01: Automated Information and Administration

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.4

## Description

The system shall automate routine administrative tasks including information publishing from university portals, schedule organization, course registration support, exam enrollment processing, and intelligent handling of student requests across faculties, departments, and research institutes.

## Key Capabilities

- Publish information automatically from university portals across organizational units
- Support automated schedule organization and course registration workflows
- Process student administrative requests intelligently (FAQ-style responses, routing)
- Manage publication database entries, grant call notifications, and research project tracking
- Suggest potential research collaborations based on expertise matching

## Acceptance Criteria

- [ ] System automates information publishing from at least 2 university portal sources
- [ ] Common student administrative requests handled without human intervention
- [ ] Schedule and registration information is accurate and up-to-date
- [ ] Administrative staff workload reduction demonstrated in pilot evaluation

## Dependencies

- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams bot as primary interaction channel
- [[REQ-INT-03-m365-ecosystem|REQ-INT-03]]: M365 integration for data access
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Personal data handling for student requests

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.4 |
| **Activity** | 1 (AI Assistant), 2 (Teams Integration) |
| **Partner** | Aricoma, COMTEC |
| **Milestone** | M5 (deployment methodology ready) |

> [!question] Open Questions
> - Which university portal systems need integration (AIS, web portals)?
> - What administrative processes are highest priority for automation?
> - How should escalation to human administrators work?
