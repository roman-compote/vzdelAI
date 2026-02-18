---
title: AI Agent Architecture
req-id: REQ-TECH-02
status: draft
priority: must
category: technical
source-section: "5.3"
source-type: extracted
activity:
  - 1
partners:
  - aricoma
milestone: M3
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ai-assistant
  - platform/azure
---

# REQ-TECH-02: AI Agent Architecture

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 5.3

## Description

The system shall implement an AI Agent architecture where fine-tuned models serve as the foundation for specialized agents, each with a defined mission, inputs, and outputs. The architecture shall support dozens of prompt-processing procedures for different query types, implementing the project's 4-layer prompting system.

## Key Capabilities

- Define and deploy specialized AI agents for distinct workflow types
- Each agent has a defined mission, input schema, and output schema
- Support the 4-layer prompting system: global context → instructional logic (Socratic method) → adaptive variables (student model) → post-interaction (reflection)
- Implement dozens of prompt-processing procedures for different query types
- Agent orchestration and routing based on query classification
- Agent state management for multi-turn conversations

## Acceptance Criteria

- [ ] At least 5 distinct agent types deployed covering core use cases (material generation, assessment, consultation, analytics, administration)
- [ ] 4-layer prompting system implemented and configurable per agent
- [ ] Query routing correctly classifies and dispatches to appropriate agent >90% of the time
- [ ] Multi-turn conversation state maintained across agent interactions
- [ ] Agent configurations are version-controlled and auditable

## Dependencies

- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: Fine-tuned LLM as agent foundation
- [[REQ-TECH-03-input-processing|REQ-TECH-03]]: Input pipeline feeds into agent layer

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.3 |
| **Activity** | 1 (AI Assistant Design & Development) |
| **Partner** | Aricoma |
| **Milestone** | M3 (fine-tuned models and infrastructure available) |

> [!question] Open Questions
> - What agent framework will be used (Azure AI Agent Service, Semantic Kernel, custom)?
> - How should agent failures and fallbacks be handled?
> - What observability is required for agent decision-making (logging, tracing)?
