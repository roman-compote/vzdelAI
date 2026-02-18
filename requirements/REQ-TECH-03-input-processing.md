---
title: Input Processing Pipeline
req-id: REQ-TECH-03
status: draft
priority: must
category: technical
source-section: "5.4"
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

# REQ-TECH-03: Input Processing Pipeline

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 5.4

## Description

The system shall implement a multi-stage input processing pipeline that handles non-text conversion (OCR, Speech-to-Text), text normalization, supplementary information retrieval from connected data sources (SharePoint, OneDrive, structured databases), and passes enriched input to the AI agent layer for response generation.

## Key Capabilities

- Non-text conversion: OCR for images and scanned documents, Speech-to-Text for audio inputs
- Text normalization: format detection, language identification, special requirement extraction
- Supplementary information retrieval from teacher knowledge bases (SharePoint, OneDrive, structured DB)
- Retrieval from official and verified educational material portals
- Context enrichment: ongoing topic, required explanation level, student profile
- Pipeline orchestration with configurable processing stages

## Acceptance Criteria

- [ ] OCR successfully processes scanned documents and handwritten notes with >90% accuracy
- [ ] Speech-to-Text supports Slovak and English audio input
- [ ] Text normalization correctly identifies input language and format
- [ ] Supplementary information retrieved from at least 3 connected data sources
- [ ] Pipeline latency acceptable for interactive use (<5 seconds for text, <15 seconds for OCR/audio)
- [ ] Processing errors handled gracefully with user-friendly feedback

## Dependencies

- [[REQ-INT-03-m365-ecosystem|REQ-INT-03]]: SharePoint/OneDrive access for knowledge base retrieval
- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline for educational material retrieval

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.4 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M3 (fine-tuned models and infrastructure available) |

> [!question] Open Questions
> - What OCR service will be used (Azure AI Document Intelligence)?
> - What Speech-to-Text service (Azure Speech Services)?
> - How should the pipeline handle mixed-language input (Slovak/English)?
