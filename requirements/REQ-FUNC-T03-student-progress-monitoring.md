---
title: Student Progress Monitoring and Analysis
req-id: REQ-FUNC-T03
status: draft
priority: must
category: functional
subcategory: teacher
source-section: "8.1"
source-type: extracted
activity:
  - 4
partners:
  - esmo
milestone: M5
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/analytics
  - platform/power-bi
---

# REQ-FUNC-T03: Student Progress Monitoring and Analysis

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The system shall provide teachers with an overview of individual and cohort student progress, identifying students struggling with specific topics and generating personalized recommendations for individual work. Analytics shall be presented via interactive dashboards.

## Key Capabilities

- Track student interactions, assessment results, and engagement metrics
- Identify students struggling with specific topics via knowledge gap analysis
- Generate personalized recommendations for individual student work
- Provide cohort-level trend analysis and performance distribution views
- Interactive Power BI dashboards with role-based access for teachers
- Proactive alerts when students fall below defined performance thresholds

## Acceptance Criteria

- [ ] Teacher dashboard shows per-student and per-topic performance breakdown
- [ ] System identifies knowledge gaps and generates actionable recommendations
- [ ] At least 250 students tracked across the pilot (§9 target)
- [ ] Statistical comparison between engaged vs. non-engaged student results (§9 target)
- [ ] Dashboards accessible via web and embedded in MS Teams

## Dependencies

- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams integration for interaction data collection
- [[REQ-INT-02-moodle-integration|REQ-INT-02]]: Moodle integration for grade and activity data
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Student data must be pseudonymized in analytics

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1, §6-Act4 |
| **Activity** | 4 (Predictive Analytics) |
| **Partner** | ESMO |
| **Milestone** | M5 (predictive analytics operational) |

> [!question] Open Questions
> - What specific metrics define "struggling" with a topic?
> - How granular should the topic breakdown be (course, chapter, concept)?
> - What pseudonymization approach satisfies GDPR while preserving analytical utility?
