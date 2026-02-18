---
title: Resource Discovery and Recommendations
req-id: REQ-FUNC-S06
status: draft
priority: should
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
  - topic/rag
---

# REQ-FUNC-S06: Resource Discovery and Recommendations

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 8.2

## Description

The system shall recommend relevant books, scientific articles, and open-access materials to students based on their current study topics and needs. Recommendations shall include direct links (where available) and concise summaries to help students evaluate relevance before accessing full materials.

## Key Capabilities

- Recommend relevant academic resources (books, journal articles, open-access papers)
- Provide concise summaries of recommended materials
- Include direct links to accessible resources where available
- Filter recommendations by relevance to current study topic
- Distinguish between university-licensed and open-access resources
- Leverage the RAG knowledge base and external academic databases

## Acceptance Criteria

- [ ] System provides at least 3 relevant resource recommendations per query
- [ ] Each recommendation includes a summary and access link where available
- [ ] Recommendations are relevant to the student's current course and topic
- [ ] Open-access vs. licensed resources are clearly distinguished
- [ ] Recommendations draw from both internal knowledge base and external sources

## Dependencies

- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]]: RAG pipeline for internal knowledge base search
- [[REQ-TECH-05-content-transformation|REQ-TECH-05]]: Content transformation for summary generation

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §8.2 |
| **Activity** | 1 (AI Assistant), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMPOTE |
| **Milestone** | M4 (integrated agent in Teams) |

> [!question] Open Questions
> - Which external academic databases should be integrated (Scopus, WoS, Google Scholar)?
> - How should university-licensed resources be handled (access verification)?
> - Should the system track which recommendations students find useful for future improvement?
