---
title: Automated Educational Material Generation
req-id: REQ-FUNC-T01
status: draft
priority: must
category: functional
subcategory: teacher
source-section: "8.1"
source-type: extracted
activity:
  - 1
  - 3
partners:
  - aricoma
  - compote
milestone: M3
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - topic/rag
---

# REQ-FUNC-T01: Automated Educational Material Generation

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.1

## Description

The system shall automatically generate educational materials (presentations, test questions, key point summaries) from teacher-uploaded lecture notes and source documents stored in SharePoint. Generated materials shall be adaptable to different student knowledge levels.

## Key Capabilities

- Accept teacher-uploaded documents from SharePoint/OneDrive as source material
- Generate PPTX presentations from lecture notes with configurable detail level
- Generate test questions (multiple choice, open-ended, true/false) aligned with lecture content
- Generate key point summaries at configurable granularity
- Adapt output complexity to target student level (introductory, intermediate, advanced)
- Output in multiple formats: PPTX, PDF, SCORM, Moodle-compatible packages

## Acceptance Criteria

- [ ] Teacher can upload lecture notes via SharePoint and trigger material generation
- [ ] System generates at least 3 output types (presentation, test, summary) from a single source
- [ ] Generated materials are adaptable to at least 2 distinct student levels
- [ ] Minimum 1,500 materials generated across the pilot (§9 target)
- [ ] Minimum 900 source materials analyzed across the pilot (§9 target)
- [ ] Generated content passes quality review by subject matter experts
- [ ] Output formats include PPTX, PDF, and at least one LMS-compatible format

## Dependencies

- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline must be operational to retrieve and process source documents
- [[REQ-TECH-05-content-transformation|REQ-TECH-05]]: Content transformation API needed for output format generation
- [[REQ-INT-03-m365-ecosystem|REQ-INT-03]]: SharePoint/OneDrive integration for document upload

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.1, §5.6 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M3 (fine-tuned models + vector DB available) |

> [!question] Open Questions
> - What quality thresholds define "acceptable" generated material?
> - Should generated materials require teacher approval before student access?
> - What metadata schema should be applied to generated materials for discoverability?
