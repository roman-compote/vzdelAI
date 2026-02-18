---
title: Study Planning and Scheduling
req-id: REQ-FUNC-S03
status: draft
priority: should
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
  - topic/ux
---

# REQ-FUNC-S03: Study Planning and Scheduling

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall help students organize their study time based on upcoming exams, assignment deadlines, and personal schedules. It shall generate optimized study schedules and provide automatic reminders for key dates.

## Key Capabilities

- Import exam and assignment deadlines from Moodle and Teams calendar
- Generate optimized study schedules considering workload distribution
- Send automatic reminders for upcoming deadlines and planned study sessions
- Allow students to adjust schedules based on personal preferences
- Suggest study session durations based on topic complexity and student performance

## Acceptance Criteria

- [ ] System generates a study schedule based on imported deadlines
- [ ] Automatic reminders delivered via Teams at configurable intervals
- [ ] Students can manually adjust and customize generated schedules
- [ ] Schedule accounts for multiple subjects and prioritizes based on urgency

## Dependencies

- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams integration for reminders and calendar access
- [[REQ-INT-02-moodle-integration|REQ-INT-02]]: Moodle integration for deadline import

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant) |
| **Partner** | Aricoma |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - Should study schedules integrate with personal calendar apps beyond Teams?
> - How should the system handle schedule conflicts?
> - What is the minimum lead time for exam preparation recommendations?
