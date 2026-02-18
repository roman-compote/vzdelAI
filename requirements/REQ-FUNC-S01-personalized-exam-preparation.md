---
title: Personalized Exam Preparation
req-id: REQ-FUNC-S01
status: draft
priority: must
category: functional
subcategory: student
source-section: "8.2"
source-type: extracted
activity:
  - 1
  - 3
partners:
  - aricoma
  - compote
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - topic/pedagogy
---

# REQ-FUNC-S01: Personalized Exam Preparation

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall generate personalized exam preparation materials for students, including custom study plans, practice questions, summaries, and recommended supplementary resources, adapted to individual knowledge gaps and learning progress.

## Key Capabilities

- Generate custom study plans based on upcoming exams and individual progress data
- Create practice questions aligned with exam topics and format
- Produce concise summaries of key concepts per topic
- Recommend supplementary resources (textbooks, articles, open-access materials)
- Adapt difficulty and focus areas based on identified knowledge gaps

## Acceptance Criteria

- [ ] Student receives a personalized study plan for each upcoming exam
- [ ] Practice questions cover all relevant exam topics with varying difficulty
- [ ] Summaries are accurate and aligned with course materials
- [ ] Minimum 250 students engaged with exam preparation features (§9 target)
- [ ] User satisfaction measured via Likert scale questionnaires (§9 target)

## Dependencies

- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline for retrieving course-specific materials
- [[REQ-FUNC-T01-automated-material-generation|REQ-FUNC-T01]]: Material generation capabilities
- [[REQ-FUNC-T03-student-progress-monitoring|REQ-FUNC-T03]]: Student progress data for personalization

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - How far in advance should study plans be generated before exams?
> - Should practice questions be generated from the same pool as actual exam questions?
> - How should difficulty adaptation be calibrated per student?
