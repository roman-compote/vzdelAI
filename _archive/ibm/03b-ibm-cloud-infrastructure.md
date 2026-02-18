---
title: "IBM Cloud Infrastructure, Analytics, Security & DevOps"
status: draft
author: research-team
created: 2026-02-18
updated: 2026-02-18
activity:
  - 1
  - 2
  - 3
  - 4
partners:
  - aricoma
  - compote
  - esmo
  - comtec
  - uniza
tags:
  - type/research
  - topic/infrastructure
  - topic/analytics
  - topic/security
---

# 03b — IBM Cloud Infrastructure, Analytics, Security & DevOps

> Comparative research on IBM Cloud capabilities for building an enterprise educational AI platform. Covers compute, databases, messaging, storage, IAM, BI/analytics, data lakehouse, DevOps, and IaC. Intended as a reference alongside [[research/03-technical-architecture]] (Microsoft-native stack) for informed platform evaluation.

> [!note] Research Context (February 2026)
> - **IBM completed HashiCorp acquisition** for $6.4B on 27 Feb 2025 — Terraform, Vault, Consul now part of IBM
> - **IBM Cloud Functions deprecated** — Code Engine is the successor for all serverless workloads
> - **Code Engine GPU Fleets** — serverless GPU support announced Oct 2025 for AI/ML workloads
> - **Cloud Pak for Data 5.3** — latest release; integrates watsonx.ai, watsonx.governance, and data fabric
> - **watsonx.data** — lakehouse with Presto C++ and Spark 3.5.4 engines; available as SaaS and software
> - **IBM acquired Confluent** — announced for real-time event streaming, strengthening Kafka portfolio

---

## 1. IBM Cloud Compute

### 1.1 Code Engine (Serverless) — Recommended for Web Apps & APIs

IBM Cloud Code Engine is a fully managed, serverless platform for running container images, batch jobs, source code, and functions. It is based on Kubernetes and Knative, auto-scales workloads from zero to thousands, and charges only for consumed resources.

| Feature | Details |
|---------|---------|
| **Workload types** | Applications (HTTP), Jobs (batch), Functions (FaaS) |
| **Scale-to-zero** | Yes — no charges when idle |
| **GPU support** | Serverless Fleets with GPUs (announced Oct 2025) for AI/ML workloads |
| **Container runtime** | OCI-compliant container images |
| **Source-to-URL** | Build from Git repo or local source; no Dockerfile required |
| **Networking** | Custom domains, TLS termination, private endpoints |
| **Pricing** | $0.00002213/vCPU-second, $0.00000229/GB-second |
| **Free tier** | Limited free tier available |
| **Promotion** | 50% savings for 6 months on non-GPU workloads (as of early 2026) |

> [!tip] Recommendation for VzdelAI
> Code Engine is the recommended option for hosting web APIs and lightweight web applications. Its scale-to-zero capability makes it cost-effective for educational workloads with variable traffic patterns (peak during semesters, idle during breaks).

### 1.2 IBM Cloud Kubernetes Service (IKS)

Fully managed Kubernetes with IBM-managed control plane. Worker nodes are single-tenant and dedicated.

| Feature | Details |
|---------|---------|
| **Kubernetes version** | Tracks upstream releases |
| **Control plane** | IBM-managed (patching, upgrades, HA) |
| **Worker nodes** | Client-owned, single-tenant, VPC-based |
| **Scaling** | Horizontal pod autoscaler, cluster autoscaler |
| **Multi-zone** | Spread workers across availability zones |
| **Integrations** | IBM Cloud Object Storage, Cloud Databases, Watson services, Istio service mesh |
| **Use case** | Complex microservices architectures requiring fine-grained control |

### 1.3 IBM Cloud Functions — DEPRECATED

> [!warning] Deprecated
> IBM Cloud Functions (based on Apache OpenWhisk) is deprecated. IBM actively guides users to migrate to Code Engine, which now supports Functions-as-a-Service (FaaS). Migration guides are available in IBM documentation.

### 1.4 Virtual Servers for VPC

Traditional VMs deployed into a Virtual Private Cloud (VPC).

| Feature | Details |
|---------|---------|
| **Profile families** | Balanced, Compute, Memory, Very High Memory, Ultra High Memory, Storage, GPU/AI, Flex |
| **Flex profiles** | Lowest price per vCPU, simplest provisioning |
| **Spot instances** | Up to 75% lower cost for interruptible workloads |
| **Billing** | Hourly, tiered storage, sustained use discounts |
| **Promotion** | Up to 60% off new VPC profiles with code BUYVPC (early 2026) |

### 1.5 Compute Recommendation Summary

| Workload | Recommended Service | Why |
|----------|-------------------|-----|
| Web APIs / microservices | **Code Engine** | Scale-to-zero, no cluster management, pay-per-use |
| Complex orchestration | **IKS** | Fine-grained Kubernetes control, multi-zone HA |
| GPU inference (prod) | **Code Engine GPU Fleets** | Serverless GPU, pay only when used |
| Legacy / stateful workloads | **Virtual Servers for VPC** | Traditional VM flexibility |
| Batch processing | **Code Engine Jobs** | Event-driven, scale-to-zero |

---

## 2. IBM Cloud Databases

IBM Cloud provides a comprehensive suite of managed database services under the "IBM Cloud Databases" umbrella. All managed databases include high availability, automated backups, encryption at rest and in transit, and point-in-time recovery.

### 2.1 Service Overview

| Database | Type | Key Features | Use Case for VzdelAI |
|----------|------|-------------|---------------------|
| **Databases for PostgreSQL** | Relational | Read replicas, automated HA, backups, PITR, extensions | Primary application database, user profiles, course metadata |
| **Db2 on Cloud** | Relational | Independent compute/storage scaling, IBM SRE-managed | Enterprise reporting, legacy data integration |
| **Cloudant** | NoSQL (JSON/CouchDB) | Serverless scaling, Transaction Engine architecture, native encryption | Chat histories, conversation logs, flexible document storage |
| **Databases for Redis** | In-memory | Cache, message broker, session store | Session caching, rate limiting, real-time leaderboards |
| **Databases for MongoDB** | NoSQL (Document) | Managed MongoDB, encryption, automated ops | Alternative to Cloudant for document workloads |
| **Databases for Elasticsearch** | Search/Analytics | Full-text search, log analytics | Application search, log aggregation |
| **Databases for MySQL** | Relational | Managed MySQL, automated HA | Alternative relational option |
| **Databases for EnterpriseDB** | Relational (Postgres) | Oracle-compatible PostgreSQL | Oracle migration scenarios |
| **Databases for etcd** | Key-value | Distributed configuration store | Service discovery, configuration management |

### 2.2 Common Managed Features

All IBM Cloud Databases share:

- **Encryption** — at rest (IBM Key Protect / Hyper Protect Crypto Services) and in transit (TLS)
- **High availability** — multi-zone deployment options
- **Automated backups** — daily, with configurable retention
- **Point-in-time recovery (PITR)** — restore to any point within retention window
- **Scaling** — independent compute and storage scaling via API or console
- **IAM integration** — IBM Cloud IAM for access control
- **Private endpoints** — VPC-native private connectivity
- **Monitoring** — IBM Cloud Monitoring (Sysdig) and Activity Tracker integration

> [!tip] Recommendation for VzdelAI
> PostgreSQL as the primary relational database (user data, course metadata, analytics), Redis for caching and session management, and Cloudant for flexible document storage (conversation logs, LLM interaction history). This mirrors the general pattern from the Microsoft stack where Azure SQL + Azure Cache for Redis + Cosmos DB serve equivalent roles.

---

## 3. IBM Event Streams (Managed Apache Kafka)

IBM Event Streams is a fully managed Apache Kafka service for event-driven architectures and real-time data streaming.

### 3.1 Plans and Capabilities

| Feature | Standard Plan | Enterprise Plan |
|---------|--------------|----------------|
| **Cluster type** | Shared multi-tenant | Dedicated single-tenant |
| **Auto-scaling** | Partition-based autoscaling | Custom throughput/storage scaling |
| **Encryption** | At rest + in transit | At rest + in transit + Key Protect / HPCS |
| **Compliance** | HIPAA, PCI-DSS, SOC 2 Type 2, ISO 27001/27017, GDPR | Same + ISMAP, C5 |
| **Geo-replication** | No | Yes |
| **Disaster recovery** | Multi-zone HA | Multi-zone HA + geo-replication |
| **Pricing model** | Pay-per-partition | Base Capacity Unit-Hour (~$1.37/hr base) |
| **Kafka API** | Full Kafka protocol | Full Kafka protocol |

> [!note] IBM's Confluent Acquisition
> IBM announced plans to acquire Confluent, the company founded by the creators of Apache Kafka. This could significantly strengthen IBM's event streaming capabilities, potentially bringing Confluent Cloud features (ksqlDB, Schema Registry, Kafka Connect) into the IBM ecosystem.

### 3.2 Comparison: IBM Event Streams vs. Azure Event Hubs

| Aspect | IBM Event Streams | Azure Event Hubs |
|--------|-------------------|-----------------|
| **Kafka compatibility** | Native Apache Kafka (full protocol) | Kafka protocol endpoint (subset, version lag) |
| **Management** | Managed brokers, user handles tuning | Fully managed, zero-infrastructure |
| **Multi-cloud** | Multi-cloud friendly via Kafka protocol | Azure-native, tighter Azure integration |
| **Geo-replication** | Enterprise plan | Premium/Dedicated tiers |
| **Pricing entry** | ~$1.37/hr (Enterprise base unit) | ~$0.015/throughput unit/hr (Standard) |
| **Schema Registry** | Via Confluent acquisition (expected) | Built-in schema registry |
| **Stream processing** | Kafka Streams / Flink | Stream Analytics / Azure Functions |
| **Best for** | Kafka-native workloads, multi-cloud | Azure-first environments, cost-sensitive |

> [!tip] For VzdelAI
> Azure Event Hubs is more cost-effective for Azure-native deployments and has a significantly lower entry price. IBM Event Streams offers full Kafka fidelity, which matters for organizations already using Kafka tooling. For a Microsoft-native stack, Event Hubs remains the natural choice.

---

## 4. IBM Cloud Object Storage

IBM Cloud Object Storage (COS) is an S3-compatible, highly scalable object storage service with built-in encryption, multi-region support, and integration with the IBM Cloud ecosystem.

### 4.1 Key Features

| Feature | Details |
|---------|---------|
| **S3 compatibility** | Full S3 API support; SDKs in Java, Python, Node.js, Go (forks of AWS SDKs with IBM extensions) |
| **Storage classes** | Standard, Vault (30-day min), Cold Vault (90-day min), Flex, One Rate |
| **Resiliency** | Cross-region, Regional, Single data center |
| **Encryption** | SSE (IBM-managed keys), SSE-C (customer-managed), Key Protect, Hyper Protect Crypto Services |
| **Immutable storage** | S3 Object Lock (WORM model), retention policies for regulatory compliance |
| **Lifecycle policies** | Automatic archival and expiration rules |
| **Event notifications** | Triggers to Code Engine, Cloud Functions, or Event Streams |
| **IAM integration** | IBM Cloud IAM for bucket and object-level access control |
| **Transfer** | Aspera high-speed transfer for large datasets |

### 4.2 Pricing

| Tier | Price | Notes |
|------|-------|-------|
| **One Rate Plan** | As low as $10/TB/month | All-inclusive (storage + egress); promo rate locked by 31 Mar 2026 |
| **Standard** | ~$0.022/GB/month (storage) + egress fees | Separate charges for storage, retrieval, egress |
| **Vault** | ~$0.011/GB/month | 30-day minimum retention |
| **Cold Vault** | ~$0.004/GB/month | 90-day minimum retention |

> [!tip] For Document Storage in VzdelAI
> COS is well-suited for storing course materials, lecture recordings, PDF documents for RAG ingestion, and xAPI learning records. The S3 compatibility means most tools and libraries work out of the box. The One Rate Plan simplifies cost prediction for educational institutions.

---

## 5. IBM Security Verify — Enterprise IAM

IBM Security Verify (formerly IBM Security Access Manager / ISAM) is an enterprise Identity and Access Management (IAM) platform. It is available as SaaS, on-premises, and hybrid deployments.

### 5.1 Core Capabilities

| Capability | Details |
|-----------|---------|
| **SSO** | SAML 2.0, OIDC/OAuth 2.0, hundreds of pre-built connectors |
| **MFA** | OTP (SMS, email, voice, TOTP), push notifications, FIDO2/WebAuthn passwordless |
| **Adaptive access** | AI-powered risk engine considering location, device, behavior |
| **IGA** | Identity Governance and Administration (lifecycle management, access reviews) |
| **PAM** | Privileged Access Management |
| **CIAM** | Customer IAM for external-facing applications |
| **Zero Trust** | Continuous verification, least-privilege enforcement |
| **Deployment** | SaaS, on-premises, hybrid-cloud |
| **Directory integration** | LDAP, Active Directory, cloud directories |

### 5.2 OIDC/OAuth 2.0 Support

- Acts as an OpenID Connect Identity Provider
- Supports Authorization Code, Implicit, Client Credentials, Resource Owner Password grants
- JWT token issuance and validation
- Custom claims and scopes
- Integration with IBM Application Gateway (IAG) for reverse-proxy authentication

### 5.3 Comparison: IBM Security Verify vs. Microsoft Entra ID

| Aspect | IBM Security Verify | Microsoft Entra ID |
|--------|--------------------|--------------------|
| **Target audience** | Large enterprise, regulated industries | Mid-market to enterprise |
| **SSO** | SAML 2.0, OIDC, 100s of connectors | SAML 2.0, OIDC, 1000s of connectors |
| **MFA** | OTP, push, FIDO2, passwordless | Authenticator app, FIDO2, passwordless, number matching |
| **Adaptive access** | AI-powered contextual risk engine | Risk-based Conditional Access policies |
| **IGA** | Built-in identity governance | Entra ID Governance (separate license) |
| **PAM** | Built-in PAM | Privileged Identity Management (PIM) |
| **M365 integration** | Limited — requires federation | Native — seamless with Teams, SharePoint, Outlook |
| **Teams bot auth** | Requires custom OIDC federation | Native Bot Framework SSO |
| **Ecosystem** | IBM Cloud, multi-cloud | Azure, M365, Windows, 3rd-party SaaS (broadest marketplace) |
| **Pricing** | Enterprise-negotiated | Free (basic), P1 ($6/user/mo), P2 ($9/user/mo) |
| **RBAC granularity** | High, customizable | High, Azure RBAC + app roles |
| **Third-party integration** | Reported difficulties with some apps | Broadest app catalog (10,000+) |

> [!warning] Implication for VzdelAI
> Microsoft Entra ID is the clear choice for VzdelAI given the project's commitment to MS Teams as the primary interface. Entra ID provides native SSO with Teams bots, seamless M365 integration, and direct integration with Azure services. IBM Security Verify would require additional federation configuration and lacks native Teams bot authentication support.

---

## 6. IBM Cognos Analytics — BI & Dashboards

IBM Cognos Analytics is an enterprise BI platform recognized with the 2025 TrustRadius Buyer's Choice Award. It has been enhanced with AI capabilities and is available on IBM Cloud, AWS, and on-premises.

### 6.1 Current Capabilities (as of early 2026)

| Capability | Details |
|-----------|---------|
| **AI Assistant** | Natural language Q&A, auto-generated visualizations and dashboards |
| **Reporting** | Pixel-perfect reports, interactive brushing, master-detail charts |
| **Dashboards** | Responsive dashboards, customizable themes, drag-and-drop |
| **Data connectivity** | On-premises and cloud databases, SAP BW/4HANA, Microsoft Fabric connector |
| **Governance** | Centralized audit trails, fine-grained access controls |
| **Deployment** | IBM Cloud, AWS (certified containers), on-premises, hybrid |
| **Reporting Agents** | Preview feature — automated report generation and distribution |
| **Mobile** | Unified mobile app |

### 6.2 Embedding Options

| Method | Details |
|--------|---------|
| **Cognos Dashboard Embedded** | Cloud service in IBM Cloud Catalog; JavaScript SDK for embedding |
| **JavaScript API** | `ca-dashboard-js-api` library for creating/managing dashboards programmatically |
| **REST API** | Full REST API for automation and integration |
| **iframe embedding** | Traditional iframe-based embedding with parameter passing |
| **Node-RED backend** | Sample apps using Node-RED for server-side Cognos integration |

### 6.3 Comparison: IBM Cognos Analytics vs. Power BI

| Aspect | IBM Cognos Analytics | Microsoft Power BI |
|--------|---------------------|-------------------|
| **Strengths** | Pixel-perfect reporting, enterprise governance, complex data models | Broad visualization library, ease of use, interactive dashboards |
| **AI features** | AI Assistant for NL queries | Copilot, Quick Insights, Smart Narratives |
| **Data connectivity** | Broad (on-prem + cloud, SAP, Fabric) | Broadest (400+ connectors, Dataverse, Fabric native) |
| **Embedding** | Dashboard Embedded (JS SDK), REST API, iframe | Power BI Embedded (JS SDK), REST API, iframe, Teams tabs |
| **Teams integration** | Manual (iframe/link) | Native Power BI app in Teams |
| **Pricing** | Enterprise-negotiated (typically $10-15/user/mo) | Pro: $10/user/mo, Premium: $20/user/mo, capacity-based options |
| **Ecosystem** | IBM Cloud, multi-vendor | Azure, M365, Fabric native |
| **Rating (Gartner PI)** | 4.3/5 (469 reviews) | 4.4/5 (3,223 reviews) |
| **Best for** | Regulated industries needing pixel-perfect reports | Organizations in Microsoft ecosystem, self-service BI |

> [!tip] For VzdelAI
> Power BI is the natural fit given the project's Microsoft-native commitment. Its native Teams tab integration, Copilot AI features, and Fabric connectivity align directly with the architecture. Cognos Analytics would be the choice only if the project pivoted to an IBM-centric stack.

---

## 7. watsonx.data — Data Lakehouse

IBM watsonx.data is an open data lakehouse architecture built on Apache Iceberg, supporting multiple query engines for AI and analytics workloads.

### 7.1 Architecture and Engines

| Component | Details |
|-----------|---------|
| **Table format** | Apache Iceberg (open format, vendor-neutral) |
| **Query engines** | Presto, Presto C++ (with Velox), Apache Spark 3.5.4, Gluten-accelerated Spark |
| **Storage** | IBM Cloud Object Storage, S3-compatible, on-premises |
| **Metadata catalog** | Integrated metastore, Hive-compatible |
| **Data lineage** | IBM Manta Data Lineage integration |
| **Governance** | watsonx.data Intelligence for access controls and cataloging |
| **Federation** | Query data in place across multiple sources |

### 7.2 Editions

| Edition | Deployment | Includes |
|---------|-----------|----------|
| **SaaS** | IBM Cloud (fully managed) | Consumption-based pricing |
| **Standard Software** | Self-managed (OpenShift) | Spark, Storage Fusion, Storage Ceph, Cloud Pak for Data platform, OpenShift |
| **Premium Software** | Self-managed (OpenShift) | Standard + watsonx.ai entitlements, watsonx.data Intelligence, watsonx.data Integration |
| **Developer Edition** | Local/dev | Free for development and testing |

### 7.3 Comparison: watsonx.data vs. Microsoft Fabric

| Aspect | IBM watsonx.data | Microsoft Fabric |
|--------|-----------------|-----------------|
| **Architecture** | Open lakehouse (Iceberg) | Unified analytics platform (OneLake, Delta) |
| **Table format** | Apache Iceberg (open) | Delta Lake (open, but Microsoft-aligned) |
| **Query engines** | Presto, Presto C++, Spark | Spark, T-SQL (Synapse), KQL, DAX |
| **AI integration** | watsonx.ai (bundled in Premium) | Azure OpenAI, Copilot, ML models |
| **Governance** | watsonx.data Intelligence, Cloud Pak for Data | Purview, OneLake security, sensitivity labels |
| **Data integration** | watsonx.data Integration, DataStage | Data Factory, Dataflows Gen2, Pipelines |
| **BI** | Cognos Analytics (separate) | Power BI (native, included) |
| **Real-time analytics** | Event Streams + Spark Streaming | Real-Time Intelligence (Eventhouse, KQL) |
| **Multi-cloud** | IBM Cloud, AWS, on-premises (OpenShift) | Azure-native (OneLake mirrors to other clouds) |
| **Pricing** | Consumption-based (SaaS), license-based (software) | Capacity Units (F2-F2048), pay-as-you-go |
| **M365 integration** | Limited | Native (OneDrive, SharePoint, Teams) |
| **Best for** | Multi-cloud, Iceberg-committed, IBM ecosystem | Microsoft-native organizations, unified analytics |

> [!note] Key Difference
> watsonx.data is committed to Apache Iceberg as an open table format, enabling true multi-engine and multi-vendor interoperability. Microsoft Fabric uses Delta Lake, which is also open-source but more tightly coupled to the Microsoft/Databricks ecosystem. For VzdelAI's Microsoft-native commitment, Fabric is the natural choice.

---

## 8. IBM DevOps — Continuous Delivery & Container Registry

### 8.1 IBM Cloud Continuous Delivery

IBM Cloud Continuous Delivery provides managed CI/CD pipelines based on the open-source Tekton framework.

| Feature | Details |
|---------|---------|
| **Pipeline engine** | Tekton (Kubernetes-native, CNCF project) |
| **Pipeline as code** | Tekton YAML resources stored in Git |
| **Toolchains** | Pre-built integrations (Git, Slack, PagerDuty, SonarQube, etc.) |
| **Delivery insights** | DevOps metrics, deployment frequency, lead time |
| **Compliance** | Shift-left compliance with IBM Cloud Security & Compliance Center |
| **Multi-target** | Deploy to IKS, OpenShift, Code Engine, Cloud Foundry (deprecated) |

### 8.2 IBM Cloud Container Registry

| Feature | Details |
|---------|---------|
| **Type** | Private, multi-tenant OCI-compliant registry |
| **Vulnerability Advisor** | Automatic scanning on image push; CVE detection, configuration issues |
| **Trusted content** | Content trust and image signing |
| **Security enforcement** | Container Image Security Enforcement (block vulnerable images at deploy) |
| **IAM integration** | IBM Cloud IAM for namespace/image access control |
| **Regional** | Available in all IBM Cloud regions |

### 8.3 Comparison: IBM Cloud DevOps vs. Azure DevOps

| Aspect | IBM Cloud Continuous Delivery | Azure DevOps |
|--------|------------------------------|-------------|
| **CI/CD engine** | Tekton (open-source, Kubernetes-native) | Azure Pipelines (proprietary + YAML) |
| **Source control** | External Git (GitHub, GitLab, Bitbucket) | Azure Repos (built-in) + external Git |
| **Work tracking** | External (Jira, GitHub Issues) | Azure Boards (built-in) |
| **Artifacts** | IBM Container Registry, external registries | Azure Artifacts (NuGet, npm, Maven, pip, Cargo) |
| **Test management** | External (SonarQube, etc.) | Azure Test Plans (built-in) |
| **Container registry** | IBM Cloud Container Registry (VA scanning) | Azure Container Registry (Defender scanning) |
| **Compliance** | IBM Cloud Security & Compliance Center | Microsoft Defender for DevOps, GHAS |
| **Ecosystem** | Open-source tools (Tekton, Ansible, Terraform) | Microsoft-integrated (GitHub, VS Code, Visual Studio) |
| **Pricing** | Included in IBM Cloud; pay for compute | Free tier (5 users), Basic ($6/user/mo), Basic+Test ($52/user/mo) |
| **Best for** | Kubernetes-native CI/CD, multi-cloud, open-source preference | Microsoft-centric organizations, integrated ALM |

> [!tip] For VzdelAI
> Azure DevOps provides a more integrated ALM experience with built-in boards, repos, pipelines, test plans, and artifacts in a single platform. IBM's Tekton-based approach is more open and Kubernetes-native but requires assembling separate tools for work tracking, source control, and testing. Given VzdelAI's Microsoft-native commitment, Azure DevOps is the natural choice. However, Tekton expertise is valuable for multi-cloud portability.

---

## 9. IBM Cloud Pak for Data — Relevance in 2026

### 9.1 Current Status

IBM Cloud Pak for Data remains relevant as the **data fabric and governance platform** that complements watsonx's AI-specific services. The latest version is **Cloud Pak for Data 5.3** (early 2026).

### 9.2 Relationship with watsonx

| Aspect | Cloud Pak for Data | watsonx |
|--------|-------------------|---------|
| **Focus** | Data integration, governance, observability, master data management | AI models (watsonx.ai), data lakehouse (watsonx.data), AI governance (watsonx.governance) |
| **Relationship** | Platform layer; watsonx.data license includes Cloud Pak for Data entitlements | AI and data services that run on Cloud Pak for Data |
| **Immersive Experience** | Toggle between Cloud Pak for Data and watsonx UIs in a single deployment (since v5.0) |
| **Unique capabilities** | Data Product Hub, Watson Knowledge Catalog, DataStage, Master Data Management, Data Lineage | Foundation models, prompt engineering, model fine-tuning, lakehouse query engines |
| **Remote Data Planes** | Single control plane supporting multiple lightweight data planes across clouds/regions | N/A (requires Cloud Pak for Data for multi-region) |

### 9.3 When to Use Cloud Pak for Data

- **Data governance at scale** — Watson Knowledge Catalog, data lineage, data quality
- **Data integration** — DataStage for ETL/ELT across heterogeneous sources
- **Master data management** — MDM for consistent entity resolution
- **Multi-cloud data fabric** — Remote Data Planes across regions and cloud providers
- **Combined AI + governance** — Immersive Experience toggling between watsonx and Cloud Pak for Data

> [!note] For VzdelAI
> Cloud Pak for Data is enterprise-grade tooling that exceeds the needs of a medium-scale educational AI platform. The standalone watsonx services (watsonx.ai, watsonx.data) or equivalent Azure services (Microsoft Fabric, Azure AI services) are more appropriate for the project's scope. Cloud Pak for Data would be relevant if the university needed enterprise-wide data governance beyond this project.

---

## 10. IBM Cloud Regions in Europe

### 10.1 European Multizone Regions (MZRs)

IBM Cloud operates two Multizone Regions in Europe, each with 3 availability zones (minimum 1 mile apart):

| Region | Code | Location | Availability Zones |
|--------|------|----------|-------------------|
| **Frankfurt** | `eu-de` | Frankfurt, Germany | 3 AZs |
| **London** | `eu-gb` | London, United Kingdom | 3 AZs |

### 10.2 Additional European Data Centers

| Location | Type | Notes |
|----------|------|-------|
| **Warsaw, Poland** | Data center (2 sites) | Central/Eastern Europe presence; designed for in-country data hosting |
| **Paris, France** | Data center | Single-zone presence |
| **Milan, Italy** | Data center | Single-zone presence |
| **Amsterdam, Netherlands** | Data center | Single-zone presence |

### 10.3 GDPR and Data Residency

| Feature | Details |
|---------|---------|
| **EU data residency** | Supported via Frankfurt and London MZRs |
| **EU Cloud Code of Conduct** | IBM Cloud adheres to EU Cloud CoC |
| **Data processing agreements** | Standard DPA available |
| **Key management** | Keep Your Own Key (KYOK) via Hyper Protect Crypto Services |
| **CEE coverage** | Warsaw data centers serve Central/Eastern Europe |

### 10.4 Comparison with Azure EU Regions

| Aspect | IBM Cloud (Europe) | Azure (Europe) |
|--------|-------------------|---------------|
| **MZRs in EU** | 2 (Frankfurt, London) | 10+ (West Europe, North Europe, France, Germany, Switzerland, Sweden, Italy, Poland, Spain, Norway) |
| **CEE presence** | Warsaw (data center, not full MZR) | Poland Central (MZR), plus nearby regions |
| **Slovakia proximity** | Warsaw (~500km from Bratislava) or Frankfurt (~600km) | Poland Central (~400km), Austria East (~60km from Bratislava) |
| **Service availability** | Most services in Frankfurt; some limited in London | Full service availability in all EU MZRs |
| **Sovereign cloud** | No EU-specific sovereign offering | EU Data Boundary, Azure Confidential Computing |

> [!warning] CEE Gap for VzdelAI
> IBM Cloud has no data center in Slovakia or immediate neighboring countries. The nearest options are Warsaw (Poland) or Frankfurt (Germany). Azure's Poland Central and upcoming/existing regions in Austria provide significantly closer data residency for a Slovak university. Azure also offers more EU regions with full service availability.

---

## 11. IBM Cloud Pricing Model

### 11.1 Pricing Structure

| Aspect | Details |
|--------|---------|
| **Model** | Pay-as-you-go (default), monthly subscriptions, enterprise agreements |
| **Free tier** | IBM Cloud Lite (limited services, no credit card) |
| **Discounts** | ~10% for monthly commitment vs. on-demand; 30%+ for enterprise agreements |
| **Reserved pricing** | Limited compared to Azure (no 1-year/3-year reserved instances for most services) |
| **Cost transparency** | Reported as less transparent; bills may arrive delayed |
| **Cost calculator** | IBM Cloud cost estimator available |

### 11.2 Comparison: IBM Cloud vs. Azure Pricing for Educational AI Platform

| Cost Factor | IBM Cloud | Azure |
|-------------|-----------|-------|
| **Compute (serverless)** | Code Engine: $0.00002213/vCPU-sec | Azure Container Apps: $0.000024/vCPU-sec |
| **Compute (VMs)** | Flex profiles; up to 60% promo | B-series burstable; up to 72% reserved |
| **Object storage** | $10/TB/mo (One Rate promo) | ~$18/TB/mo (Hot tier) |
| **Managed PostgreSQL** | Enterprise-negotiated | ~$0.034/vCore/hr (Flexible Server) |
| **Event streaming** | ~$1.37/hr (Enterprise base) | ~$0.015/throughput unit/hr (Event Hubs Standard) |
| **AI model inference** | watsonx.ai consumption-based | Azure OpenAI per-token pricing |
| **Identity (IAM)** | Security Verify (enterprise-negotiated) | Entra ID: Free (basic) to $9/user/mo (P2) |
| **BI** | Cognos Analytics (enterprise license) | Power BI Pro: $10/user/mo |
| **Discount depth** | ~10-30% negotiated | Up to 72% reserved instances |
| **Academic pricing** | Limited public academic programs | Azure for Education, $100 credits, GitHub Student Pack |

### 11.3 TCO Considerations

| Factor | IBM Cloud | Azure |
|--------|-----------|-------|
| **Entry cost** | Higher — enterprise-oriented pricing, less self-service | Lower — generous free tiers, pay-as-you-go |
| **Scale economics** | Better for enterprise agreements (30%+ discount) | Better at medium scale with reserved instances |
| **Academic discounts** | Limited | Extensive (Azure for Education, Microsoft Imagine Academy) |
| **Hybrid advantage** | Red Hat OpenShift included in many bundles | Azure Hybrid Benefit (Windows + SQL Server licenses) |
| **Total platform cost** | Higher for equivalent capabilities | Lower for Microsoft-native workloads due to bundling |

> [!tip] For a Medium-Scale Educational AI Platform
> Azure is likely more cost-effective for VzdelAI due to: (1) academic pricing programs, (2) deeper discounts via reserved instances, (3) bundled services in M365 E5 that the university may already have, (4) lower entry price for most individual services. IBM Cloud's strength is in enterprise-negotiated deals for large organizations, which may not align with a university research project budget.

---

## 12. Infrastructure as Code

### 12.1 IBM Cloud Schematics

IBM Cloud Schematics is a fully managed IaC service that leverages Terraform, Ansible, and Git.

| Feature | Details |
|---------|---------|
| **Terraform support** | Native — Terraform workspaces, state management, plan/apply |
| **Ansible support** | Configuration management and application deployment |
| **IBM Terraform provider** | Full IBM Cloud resource coverage (`ibm` provider on Terraform Registry) |
| **State management** | Managed state storage (no external backend needed) |
| **Drift detection** | Detect configuration drift from desired state |
| **RBAC** | IBM Cloud IAM for workspace access control |
| **Compliance** | Integration with IBM Cloud Security & Compliance Center for shift-left compliance |
| **VS Code extension** | IBM Cloud Schematics extension for local development |
| **CRAIG** | Cloud Resource and Infrastructure-as-Code Generator — GUI for generating Terraform |
| **Speed** | Reported 80% faster provisioning vs. manual configuration |

### 12.2 HashiCorp Acquisition Impact

IBM completed the $6.4B acquisition of HashiCorp on 27 February 2025. This brings Terraform, Vault, Consul, Waypoint, Nomad, Packer, Boundary, and Vagrant directly into the IBM portfolio.

| Product | IBM Integration Potential |
|---------|-------------------------|
| **Terraform** | Strengthened Schematics, unified with Ansible for end-to-end automation |
| **Vault** | Secrets management integrated with OpenShift, Ansible, Guardium |
| **Consul** | Service mesh and service discovery for hybrid cloud |
| **Boundary** | Secure remote access to infrastructure |
| **Packer** | Image building for IBM Cloud VPC virtual servers |

> [!note] Project infragraph (HashiConf 2025)
> HashiCorp (now IBM) unveiled Project infragraph — a real-time infrastructure graph connecting infrastructure, applications, services, and ownership across hybrid cloud environments. This represents IBM's vision for agentic infrastructure automation.

### 12.3 Comparison: IBM IaC vs. Azure IaC

| Aspect | IBM Cloud Schematics | Azure IaC |
|--------|---------------------|-----------|
| **Primary tool** | Terraform (native, now owned by IBM) | Bicep (native), ARM templates, Terraform (supported) |
| **Configuration mgmt** | Ansible (integrated in Schematics) | Azure Automation (PowerShell DSC), Ansible (via Azure CLI) |
| **State management** | Managed by Schematics | Azure Storage backend (manual), Terraform Cloud |
| **Secrets** | Vault (HashiCorp, now IBM), Key Protect | Azure Key Vault |
| **GUI generator** | CRAIG (open-source) | Azure Portal export, Bicep VS Code extension |
| **Compliance as code** | IBM Cloud Security & Compliance Center | Azure Policy, Defender for Cloud |
| **Drift detection** | Built-in | Azure Policy compliance scanning, Terraform plan |

> [!tip] For VzdelAI
> Both platforms have strong IaC support. IBM's ownership of HashiCorp/Terraform is strategically significant for the IaC ecosystem, but for Azure-native infrastructure, Bicep or Terraform with the AzureRM provider is the practical choice. IBM Cloud Schematics is relevant only if deploying IBM Cloud resources.

---

## 13. Summary Assessment for VzdelAI

### 13.1 IBM Cloud Strengths

| Strength | Details |
|----------|---------|
| **Open standards** | Iceberg (lakehouse), Kafka (event streaming), Kubernetes (compute), Terraform (IaC) |
| **Multi-cloud flexibility** | watsonx.data on IBM Cloud + AWS; OpenShift portability |
| **Enterprise governance** | Cloud Pak for Data provides deep data governance and lineage |
| **HashiCorp portfolio** | Terraform, Vault, Consul now IBM-owned — strongest IaC story |
| **Security depth** | Security Verify, Hyper Protect Crypto Services, Confidential Computing |

### 13.2 IBM Cloud Weaknesses for VzdelAI

| Weakness | Impact |
|----------|--------|
| **No native Teams integration** | Project requires MS Teams as primary interface |
| **Limited EU/CEE regions** | Only 2 EU MZRs vs. Azure's 10+; no Slovakia-adjacent MZR |
| **Higher entry cost** | Enterprise-oriented pricing; less academic program support |
| **Smaller ecosystem** | Fewer marketplace integrations, smaller community |
| **No Moodle LTI connectors** | No equivalent to Azure-based Moodle integration paths |
| **BI/analytics gap** | Cognos lacks native Teams embedding; Power BI is superior for M365 |

### 13.3 Recommendation

> [!warning] Platform Recommendation
> **Azure remains the recommended platform for VzdelAI**, as stated in the project description. IBM Cloud is a capable enterprise platform with notable strengths in open standards, governance, and (post-HashiCorp acquisition) infrastructure automation. However, VzdelAI's core requirements — MS Teams bot, Moodle LMS integration, M365 ecosystem, EU data residency near Slovakia, and academic pricing — all favor Azure.
>
> **Where IBM could complement Azure:**
> - **Terraform/Vault** (HashiCorp tools) for multi-cloud IaC and secrets management — these tools work on any cloud
> - **watsonx.ai models** as alternative LLMs via API (if Azure OpenAI models prove insufficient for Slovak language)
> - **Cloud Pak for Data** if the university requires institution-wide data governance beyond VzdelAI

---

## Sources

- [IBM Cloud Code Engine](https://www.ibm.com/products/code-engine)
- [IBM Cloud Code Engine Serverless Fleets with GPUs — InfoQ](https://www.infoq.com/news/2025/10/ibm-cloud-code-engine-serverless/)
- [Code Engine Pricing](https://cloud.ibm.com/docs/codeengine?topic=codeengine-pricing)
- [IBM Cloud Database Services](https://www.ibm.com/products/cloud-databases)
- [IBM Cloud Database Offerings: A 2025 Overview](https://bigdataclouds.org/ibm-cloud-database-offerings-a-2025-comprehensive-overview/)
- [IBM Event Streams](https://www.ibm.com/products/event-streams)
- [Event Streams Overview](https://cloud.ibm.com/docs/EventStreams?topic=EventStreams-about)
- [IBM Cloud Object Storage](https://www.ibm.com/products/cloud-object-storage)
- [IBM Cloud Object Storage One-Rate Extended](https://www.ibm.com/new/announcements/predictable-storage-more-time-ibm-cloud-object-storage-one-rate-extended)
- [IBM Verify — IAM Platform](https://www.ibm.com/products/verify)
- [IBM Security Verify Review 2025](https://www.infisign.ai/reviews/ibm-security-verify)
- [Entra ID vs IBM Security Verify](https://www.selecthub.com/identity-access-management-software/entra-id-vs-ibm-security-verify/)
- [Microsoft Entra ID vs IBM Security Verify — LoginRadius](https://www.loginradius.com/compare/iam/entraid-vs-ibmsecurityverify)
- [IBM Cognos Analytics](https://www.ibm.com/products/cognos-analytics)
- [Cognos vs Power BI — IBM](https://www.ibm.com/products/cognos-analytics/cognos-vs-power-bi)
- [Cognos Dashboard Embedded JS API — GitHub](https://github.com/IBM/ca-dashboard-js-api)
- [IBM watsonx.data](https://www.ibm.com/products/watsonx-data)
- [watsonx.data Pricing](https://www.ibm.com/products/watsonx-data/pricing)
- [IBM Cloud Pak for Data 5.0 Announcement](https://www.ibm.com/new/announcements/ibm-unveils-ibm-cloud-pak-for-data-5-0-revolutionizing-ai-implementations-with-data-fabric-architecture)
- [Cloud Pak for Data 5.3 Announcement](https://www.ibm.com/new/announcements/cloud-pak-for-data-v5-3-smarter-faster-and-built-for-scale)
- [Comparison of watsonx and Cloud Pak for Data](https://dataplatform.cloud.ibm.com/docs/content/wsj/getting-started/compare-platforms.html?context=wx)
- [IBM Cloud Continuous Delivery](https://www.ibm.com/products/continuous-delivery)
- [Tekton on IBM Cloud](https://www.ibm.com/products/tekton)
- [IBM Cloud Container Registry](https://www.ibm.com/products/container-registry)
- [IBM Cloud Global Data Centers](https://www.ibm.com/cloud/data-centers)
- [IBM Cloud Locations](https://cloud.ibm.com/docs/overview?topic=overview-locations)
- [IBM Cloud Schematics](https://www.ibm.com/products/schematics)
- [IBM Completes HashiCorp Acquisition](https://newsroom.ibm.com/2025-02-27-ibm-completes-acquisition-of-hashicorp,-creates-comprehensive,-end-to-end-hybrid-cloud-platform)
- [IBM Cloud Pricing](https://www.ibm.com/products/cloud/pricing)
- [Cloud Pricing Comparison 2026 — CloudZero](https://www.cloudzero.com/blog/cloud-pricing-comparison/)
- [Comparing Cloud Instance Pricing — Flexera](https://www.flexera.com/blog/finops/comparing-cloud-instance-pricing-aws-vs-azure-vs-google-vs-ibm/)
- [IBM Cloud Functions Deprecation Overview](https://cloud.ibm.com/docs/openwhisk?topic=openwhisk-dep-overview)
- [Migrating Cloud Functions to Code Engine](https://cloud.ibm.com/docs/codeengine?topic=codeengine-fun-migrate)
- [IBM Kubernetes Service](https://www.ibm.com/products/kubernetes-service)
- [IBM Virtual Servers for VPC](https://www.ibm.com/products/virtual-servers)
