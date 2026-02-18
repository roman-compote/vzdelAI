# 07 — Regulatory Compliance: EU AI Act, GDPR & Slovakia National Context

> Comprehensive analysis of the regulatory landscape for educational AI in the EU, with specific focus on compliance requirements for VzdelAI.

---

## 1. EU AI Act — Overview

### 1.1 Legislative Context

The **EU AI Act** (Regulation (EU) 2024/1689) is the world's first comprehensive AI regulation. It entered into force on 1 August 2024 and applies in phases.

**Full text:** [EUR-Lex — Regulation (EU) 2024/1689](https://eur-lex.europa.eu/eli/reg/2024/1689)

### 1.2 Risk-Based Classification

The AI Act classifies AI systems into four risk tiers:

| Risk Level | Description | Examples | Requirements |
|------------|-------------|----------|-------------|
| **Unacceptable** | Banned practices | Social scoring, manipulative AI, real-time biometric ID (exceptions) | Prohibited |
| **High-Risk** | Significant impact on fundamental rights | **Education AI**, employment AI, critical infrastructure | Strict compliance obligations |
| **Limited Risk** | Transparency concerns | Chatbots, deepfakes | Transparency obligations |
| **Minimal Risk** | Low impact | Spam filters, AI in video games | No requirements (voluntary codes) |

### 1.3 Education AI as HIGH-RISK

**Article 6(2) and Annex III, Section 3** of the EU AI Act explicitly classify the following educational AI systems as **high-risk**:

| High-Risk Educational AI | Article Reference |
|--------------------------|-------------------|
| AI systems intended to determine **access to or admission** to educational institutions | Annex III, 3(a) |
| AI systems for **assigning persons to educational institutions** or programmes | Annex III, 3(a) |
| AI systems for **evaluating learning outcomes** (including AI-assisted grading) | Annex III, 3(b) |
| AI systems for **assessing the appropriate level of education** for a person | Annex III, 3(b) |
| AI systems for **monitoring and detecting prohibited behaviour** during exams/tests | Annex III, 3(c) |

**Critical implication for VzdelAI:** If VzdelAI performs any assessment, grading, or personalized learning path determination, it falls under **high-risk classification**. The university (University of Žilina) would be classified as a **provider** of a high-risk AI system.

### 1.4 Implementation Timeline

| Date | Milestone | Relevance to VzdelAI |
|------|-----------|----------------------|
| **1 Aug 2024** | AI Act enters into force | Awareness required |
| **2 Feb 2025** | Prohibited practices apply | Ensure no banned features |
| **2 Aug 2025** | GPAI model rules apply | LLM provider obligations |
| **2 Aug 2025** | Governance structure established | National authorities appointed |
| **2 Aug 2026** | **General application — all remaining provisions**, including high-risk systems in **Annex III** (education, employment, biometrics, etc.) under Art. 6(2) | **Full compliance required for VzdelAI** |
| **2 Aug 2027** | Art. 6(1) obligations — high-risk AI as safety components of products under **Annex I** Union harmonisation legislation | Product-embedded AI only |

**Key date:** VzdelAI must be fully compliant with high-risk obligations by **2 August 2026** (the general application date). The later 2027 deadline applies only to AI systems embedded in regulated products (Annex I / Art. 6(1)), not standalone educational AI systems classified under Annex III / Art. 6(2).

---

## 2. High-Risk AI Compliance Obligations

### 2.1 Requirements Overview

Universities deploying educational AI are classified as **providers** under Article 3(3) and must fulfill the following obligations:

| Obligation | Article | Description |
|------------|---------|-------------|
| **Risk Management System** | Art. 9 | Continuous risk identification, assessment, and mitigation throughout the AI system lifecycle |
| **Data Governance** | Art. 10 | Quality criteria for training, validation, and testing data; bias detection and mitigation |
| **Technical Documentation** | Art. 11 | Comprehensive documentation of system design, capabilities, limitations, and performance |
| **Record-Keeping / Logging** | Art. 12 | Automatic logging of system events for traceability and auditability |
| **Transparency & User Instructions** | Art. 13 | Clear instructions for deployers; information about capabilities and limitations |
| **Human Oversight** | Art. 14 | System must allow effective human oversight; humans must be able to override AI decisions |
| **Accuracy, Robustness, Cybersecurity** | Art. 15 | Appropriate levels of accuracy, robustness, and security throughout lifecycle |
| **Quality Management System** | Art. 17 | Documented quality processes, procedures, and controls |
| **Conformity Assessment** | Art. 43 | Self-assessment for most education AI (not via notified body) |
| **EU Declaration of Conformity** | Art. 47 | Written declaration that the system meets requirements |
| **CE Marking** | Art. 48 | Conformity marking (for products placed on market) |
| **Post-Market Monitoring** | Art. 72 | Ongoing monitoring of system performance and compliance |

### 2.2 Detailed Compliance Requirements for VzdelAI

#### Risk Management System (Art. 9)

VzdelAI must implement:

| Component | Implementation |
|-----------|---------------|
| Risk identification | Document all risks: hallucination, bias, privacy, academic integrity |
| Risk assessment | Probability × impact analysis for each risk |
| Risk mitigation | Technical measures (RAG, guardrails, filtering) + organizational measures (human review policies) |
| Residual risk | Document accepted risks and justify why they are acceptable |
| Testing | Regular testing to evaluate risk mitigation effectiveness |
| Lifecycle management | Update risk assessment when system changes (new models, knowledge bases, features) |

#### Data Governance (Art. 10)

| Requirement | VzdelAI Implementation |
|-------------|----------------------|
| Data quality | Curated course knowledge bases with expert review |
| Bias detection | Test for demographic, linguistic, and subject-matter biases |
| Data relevance | Ensure RAG knowledge bases are current and relevant to courses |
| Data representativeness | Include diverse perspectives in knowledge bases |
| Error correction | Process for updating/correcting incorrect content |
| Privacy | GDPR-compliant data handling (see Section 3) |

#### Technical Documentation (Art. 11)

VzdelAI must maintain documentation covering:

1. General system description (purpose, functionality, target users)
2. Detailed technical description (architecture, algorithms, data flows)
3. Development process (design choices, trade-offs, testing)
4. Monitoring and control mechanisms
5. Risk management documentation
6. Changes and updates log
7. Performance metrics and benchmarks
8. Cybersecurity measures

#### Logging Requirements (Art. 12)

| Event to Log | Data Points |
|--------------|-------------|
| User queries | Timestamp, user role (anonymized), query text |
| AI responses | Response text, confidence score, RAG sources used |
| Model decisions | Learning path suggestions, content difficulty adjustments |
| Assessment actions | Grading decisions, feedback generated |
| System events | Model version changes, knowledge base updates |
| Error events | Failures, fallbacks, escalations to human |

**Implementation:** xAPI-based event logging satisfies both learning analytics needs and AI Act logging requirements.

#### Human Oversight (Art. 14)

| Mechanism | Implementation |
|-----------|---------------|
| Teacher review | All AI-generated assessments reviewed by teacher before use |
| Override capability | Teachers can modify AI learning path recommendations |
| Escalation | Complex questions flagged for human response |
| Transparency | Students informed when interacting with AI |
| Opt-out | Students can choose not to use AI features |

#### Conformity Assessment (Art. 43)

For education AI systems (Annex III, Section 3), the conformity assessment is **self-assessment** based on internal control procedures (Annex VI), NOT requiring a third-party notified body.

Steps:
1. Establish quality management system (Art. 17)
2. Prepare technical documentation (Art. 11)
3. Conduct internal conformity assessment
4. Draw up EU Declaration of Conformity (Art. 47)
5. Register in EU database (Art. 49)

---

## 3. GDPR Requirements for Educational AI

### 3.1 Lawful Processing Basis

Under GDPR (Regulation (EU) 2016/679), VzdelAI must establish a lawful basis for processing student personal data:

| Lawful Basis | Applicability to VzdelAI |
|-------------|--------------------------|
| **Legitimate interest** (Art. 6(1)(f)) | Most likely basis — educational support is a legitimate institutional interest; requires balancing test |
| **Consent** (Art. 6(1)(a)) | Possible but problematic — power imbalance between university and student weakens consent validity |
| **Contract** (Art. 6(1)(b)) | If AI tutoring is part of the educational service contract |
| **Public task** (Art. 6(1)(e)) | If the university's public mission includes AI-enhanced education |

**Recommendation:** Combination of **legitimate interest** (for core functionality) and **consent** (for optional enhanced features like learning analytics profiling).

### 3.2 Core GDPR Principles Applied to VzdelAI

| Principle | Article | VzdelAI Implementation |
|-----------|---------|----------------------|
| **Purpose limitation** | Art. 5(1)(b) | Data collected only for educational support; not used for other purposes |
| **Data minimization** | Art. 5(1)(c) | Collect only necessary data (queries, responses); no excessive profiling |
| **Storage limitation** | Art. 5(1)(e) | Define retention periods; delete/anonymize after course completion |
| **Accuracy** | Art. 5(1)(d) | Allow students to correct their data; keep knowledge bases current |
| **Integrity & confidentiality** | Art. 5(1)(f) | Encryption, access controls, secure infrastructure |
| **Accountability** | Art. 5(2) | Document all processing activities; demonstrate compliance |

### 3.3 Data Protection Impact Assessment (DPIA)

**A DPIA is mandatory** for VzdelAI under Art. 35(3) because:
- Systematic evaluation of personal aspects (learning behavior profiling)
- Large-scale processing of student data
- Vulnerable data subjects (students in dependent relationship with university)

#### DPIA Content Requirements

| Section | Content |
|---------|---------|
| Description | Systematic description of processing operations and purposes |
| Necessity | Assessment of necessity and proportionality |
| Risk assessment | Risks to rights and freedoms of students |
| Mitigation | Measures to address risks, including safeguards and security |
| DPO consultation | Data Protection Officer review and sign-off |

### 3.4 Student Data Rights

| Right | Article | Implementation |
|-------|---------|---------------|
| **Right to be informed** | Art. 13–14 | Clear privacy notice explaining AI data processing |
| **Right of access** | Art. 15 | Students can request all data VzdelAI holds about them |
| **Right to rectification** | Art. 16 | Students can correct inaccurate data |
| **Right to erasure** | Art. 17 | Students can request deletion of their interaction history |
| **Right to data portability** | Art. 20 | Export interaction history and learning records in machine-readable format |
| **Right to object** | Art. 21 | Students can object to profiling for learning analytics |
| **Right not to be subject to automated decisions** | Art. 22 | AI-only assessment decisions require human review mechanism |

### 3.5 Anonymization & Pseudonymization

| Technique | Application in VzdelAI |
|-----------|----------------------|
| **Pseudonymization** | Replace student identifiers with tokens in analytics data; mapping table stored separately |
| **Anonymization** | Aggregate analytics (class-level statistics) for research and publications |
| **Differential privacy** | Add noise to aggregate statistics to prevent re-identification |
| **Data segregation** | Separate identity data from interaction data in storage |

### 3.6 Cross-Border Data Transfer

If VzdelAI uses cloud LLM APIs (OpenAI, Anthropic), student data may leave the EU:

| Scenario | GDPR Compliance Path |
|----------|---------------------|
| **Azure OpenAI (EU region)** | Data stays in EU — simplest compliance path |
| **OpenAI API (US)** | Requires Standard Contractual Clauses (SCCs) + supplementary measures |
| **Ollama (self-hosted)** | No cross-border transfer — fully compliant |
| **Anthropic Claude (US)** | Requires SCCs + supplementary measures |

**Recommendation:** Use **Azure OpenAI with EU data residency** for production; **Ollama** for maximum data sovereignty; avoid sending identifiable student data to non-EU APIs.

---

## 4. Slovakia National Context

### 4.1 "Responsible Use of AI in Education" Plan 2025–2027

**Source:** MŠVVaM SR (Ministry of Education, Research, Development and Youth of the Slovak Republic)
**URL:** [MŠVVaM SR](https://www.minedu.sk/)

| Aspect | Details |
|--------|---------|
| **Title (SK)** | Plán zodpovedného využívania AI vo vzdelávaní 2025–2027 |
| **Scope** | All levels of education in Slovakia |
| **Key goals** | Integrate AI into curricula; train teachers; establish competence centres; ensure responsible use |

#### Key Measures

| Measure | Timeline | Description |
|---------|----------|-------------|
| AI curriculum integration | 2026/2027 school year | AI concepts embedded in subjects across educational levels |
| Teacher training | 2025–2027 | Systematic AI literacy training for educators |
| AI Competence Centres | 2026–2029 | Establish centres at selected Slovak universities |
| Ethical guidelines | 2025 | National guidelines for responsible AI use in education |
| Pilot projects | 2025–2027 | Support for innovative AI education projects |

### 4.2 AI Competence Centres at Slovak Universities

| Aspect | Details |
|--------|---------|
| **Period** | 2026–2029 |
| **Purpose** | Build AI expertise and infrastructure at Slovak higher education institutions |
| **Activities** | Research, development, training, knowledge transfer, industry collaboration |
| **Funding** | EU structural funds + national co-financing |
| **Opportunity for VzdelAI** | University of Žilina could leverage VzdelAI as a flagship project for Competence Centre application |

### 4.3 BratislavAI Forum

| Aspect | Details |
|--------|---------|
| **What** | Regular ministerial-level meetings on AI policy in education |
| **Participants** | Slovak ministries, international partners, academia, industry |
| **Topics** | AI regulation implementation, best practices, cross-border collaboration |
| **Relevance** | Venue for presenting VzdelAI results and influencing national AI education policy |

### 4.4 Slovak Data Protection Authority (Úrad na ochranu osobných údajov SR)

| Aspect | Details |
|--------|---------|
| **Role** | National GDPR supervisory authority |
| **URL** | [dataprotection.gov.sk](https://dataprotection.gov.sk/) |
| **Relevance** | DPIA consultation; guidance on educational data processing; enforcement |
| **AI Act role** | Expected to serve as (or coordinate with) national AI Act market surveillance authority |

---

## 5. Compliance Roadmap for VzdelAI

### Phase 1: Foundation (Months 1–3)

| Action | Responsibility |
|--------|---------------|
| Appoint AI compliance lead | Project management |
| Conduct initial risk assessment | Compliance lead + technical team |
| Draft DPIA | Compliance lead + DPO |
| Establish data processing agreement | University legal + DPO |
| Define lawful processing basis | University legal |
| Create privacy notice for students | Compliance lead + legal |

### Phase 2: Technical Implementation (Months 3–6)

| Action | Responsibility |
|--------|---------------|
| Implement logging infrastructure (xAPI) | Technical team |
| Deploy Azure OpenAI with EU data residency | Technical team |
| Implement pseudonymization layer | Technical team |
| Build human oversight mechanisms (teacher review) | Technical team |
| Implement student data rights (access, deletion, export) | Technical team |
| Set up access controls (RBAC) | Technical team |

### Phase 3: Documentation & Assessment (Months 6–9)

| Action | Responsibility |
|--------|---------------|
| Complete technical documentation (Art. 11) | Technical team + compliance |
| Establish quality management system (Art. 17) | Project management |
| Conduct bias testing | Technical team + domain experts |
| Finalize risk management documentation | Compliance lead |
| Prepare for conformity self-assessment | Compliance lead |

### Phase 4: Compliance & Monitoring (Ongoing)

| Action | Responsibility |
|--------|---------------|
| Conduct conformity self-assessment | Compliance lead |
| Register in EU AI Act database | Compliance lead |
| Implement post-market monitoring | Technical team + compliance |
| Regular risk assessment updates | Compliance lead |
| GDPR compliance audits | DPO |
| Respond to student data requests | Data controller (university) |

---

## 6. Compliance Checklist Summary

### EU AI Act — High-Risk Obligations

- [ ] Risk management system established and documented
- [ ] Data governance procedures in place
- [ ] Technical documentation complete
- [ ] Automatic event logging implemented
- [ ] User instructions / transparency measures in place
- [ ] Human oversight mechanisms operational
- [ ] Accuracy, robustness, and cybersecurity verified
- [ ] Quality management system documented
- [ ] Conformity self-assessment completed
- [ ] EU Declaration of Conformity drafted
- [ ] Registered in EU AI Act database
- [ ] Post-market monitoring plan active

### GDPR

- [ ] Lawful processing basis established
- [ ] Privacy notice published
- [ ] DPIA completed and reviewed by DPO
- [ ] Data processing agreements with third parties (LLM providers)
- [ ] Student rights mechanisms implemented (access, erasure, portability)
- [ ] Cross-border data transfer safeguards in place
- [ ] Data retention policy defined
- [ ] Pseudonymization/anonymization applied
- [ ] Security measures documented

---

## References

- European Parliament & Council. (2024). *Regulation (EU) 2024/1689 — Artificial Intelligence Act.* https://eur-lex.europa.eu/eli/reg/2024/1689
- European Parliament & Council. (2016). *Regulation (EU) 2016/679 — General Data Protection Regulation.* https://eur-lex.europa.eu/eli/reg/2016/679
- European Commission. (2025). *AI Act Implementation Guidelines.* https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- MŠVVaM SR. (2025). *Plán zodpovedného využívania AI vo vzdelávaní 2025–2027.* https://www.minedu.sk/
- Úrad na ochranu osobných údajov SR. (2025). *Data Protection Authority.* https://dataprotection.gov.sk/
- European Data Protection Board. (2025). *Guidelines on AI and GDPR.* https://www.edpb.europa.eu/
- Future of Life Institute. (2024). *EU AI Act Explorer.* https://artificialintelligenceact.eu/
