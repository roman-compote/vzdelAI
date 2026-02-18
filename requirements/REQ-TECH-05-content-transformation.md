---
title: Content Transformation and Output Generation
req-id: REQ-TECH-05
status: draft
priority: must
category: technical
source-section: "5.6"
source-type: extracted
activity:
  - 3
partners:
  - compote
milestone: M3
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/rag
  - topic/ai-assistant
---

# REQ-TECH-05: Content Transformation and Output Generation

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 5.6

## Description

The system shall provide a content transformation API that converts AI-generated content into various output formats based on DSL specifications. The API shall support output type definition (test, presentation, summary, diagram), target audience parameters, and generation in multiple formats including PPTX, PDF, SCORM, LTI, interactive quizzes, and visualizations.

## Key Capabilities

- Accept DSL specifications (JSON, XML, YML, Markdown) defining output requirements
- Support output types: tests, presentations, summaries, diagrams, videos, interactive materials
- Configure target audience, level, scope, and language style per output
- Generate outputs in: PPTX, PDF, SCORM, LTI-compatible packages, HTML
- Generate interactive quizzes and visualizations
- Integrate with Moodle, SharePoint, OneDrive, and Microsoft 365 ecosystem

## Acceptance Criteria

- [ ] API accepts DSL specifications and generates requested output formats
- [ ] At least 5 output formats supported (PPTX, PDF, SCORM, HTML, Moodle-compatible)
- [ ] Generated outputs meet quality standards for educational use
- [ ] Content transformation completes within acceptable time limits
- [ ] Minimum 1,500 materials generated across the pilot (§9 target)
- [ ] Digital platform achieves TRL 5 — functional prototype verified in real conditions (§2.2)

## Dependencies

- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline provides source content for transformation
- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: LLM for content generation
- [[REQ-INT-02-moodle-integration|REQ-INT-02]]: Moodle integration for LMS-compatible output

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.6, §2.2, §2.3 |
| **Activity** | 3 (RAG Pipeline & Content Generation) |
| **Partner** | COMPOTE |
| **Milestone** | M3 (infrastructure available) |

> [!question] Open Questions
> - What DSL schema will be standardized for output specifications?
> - Which SCORM version (1.2 or 2004) is required for Moodle compatibility?
> - How will video generation be implemented (Azure Media Services, third-party)?
> - What quality assurance process will validate generated educational outputs?
