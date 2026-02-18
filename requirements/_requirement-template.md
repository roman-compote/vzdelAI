---
title: "<% tp.file.cursor(1) %>"
req-id: "<% tp.file.cursor(2) %>"
status: draft
priority: must
category: "<% tp.file.cursor(3) %>"
subcategory: "<% tp.file.cursor(4) %>"
source-section: "<% tp.file.cursor(5) %>"
source-type: extracted
activity:
  - <% tp.file.cursor(6) %>
partners: []
milestone: <% tp.file.cursor(7) %>
created: <% tp.date.now("YYYY-MM-DD") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - type/requirement
---

# <% tp.frontmatter["req-id"] %>: <% tp.frontmatter.title %>

> [!info] Source
> [[VzdelAI_Project_Description]] — Section <% tp.frontmatter["source-section"] %>

## Description

<% tp.file.cursor(8) %>

## Key Capabilities

-

## Acceptance Criteria

- [ ]

## Dependencies

-

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §<% tp.frontmatter["source-section"] %> |
| **Activity** | |
| **Partner** | |
| **Milestone** | |

> [!question] Open Questions
> -
