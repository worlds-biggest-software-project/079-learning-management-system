# Learning Management System (LMS)

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source learning management system for course creation, delivery, tracking, and personalised learning paths.

The Learning Management System is an open-source platform for academic institutions, enterprises, SMBs, and NGOs to author courses, deliver training, track progress, and adapt learning paths using AI. It targets the gap between aging open-source incumbents (Moodle, Chamilo, Sakai) that lack native AI and expensive AI-native commercial SaaS (Docebo, Cornerstone) that price out smaller organisations and cannot be self-hosted. The project combines table-stakes LMS capabilities with generative content authoring, adaptive sequencing, and skills-graph automation while preserving data sovereignty.

---

## Why LMS?

- Open-source incumbents have no native AI. Moodle, Chamilo, and Sakai offer no AI-driven path adaptation; adaptive learning requires third-party plugins or custom development.
- Commercial AI-native LMS platforms price out smaller buyers. Docebo's ~$25,000/year minimum and Cornerstone's $6–$18/user/month with 500-user minimums exclude SMBs and non-profits.
- SaaS-only AI offerings cannot meet data-sovereignty requirements. Docebo and Cornerstone provide no on-premises or private-cloud option, blocking adoption by government, healthcare, and finance buyers concerned about GDPR, data residency, and learner data used for shared model training.
- Legacy enterprise LMS platforms are losing trust. Anthology (Blackboard) filed Chapter 11 in September 2025 and emerged debt-free in February 2026; institutional defectors are actively seeking alternatives.
- Existing open-source authoring tools are basic. Moodle has no built-in rapid authoring tool comparable to Articulate or Adobe Captivate, and aging admin UX is widely criticised for complexity.

---

## Key Features

### Course Authoring & Content Management

- Course builder supporting video, documents, quizzes, and H5P interactive content
- SCORM 1.2 and SCORM 2004 runtime support for third-party eLearning content packages
- xAPI (Tin Can) statement sending and Learning Record Store (LRS) connectivity for tracking learning activity beyond the LMS boundary
- Generative AI course authoring producing a structured course from a competency description or uploaded source document
- AI-generated formative assessments calibrated to individual learner performance history

### Delivery, Enrolment & Compliance

- Enrolment engine with self-service, manager-assigned, and rule-triggered automatic enrolment
- Certification and compliance tracking with configurable expiry and renewal reminder workflows
- Quiz and assessment engine with multiple question types, rubric-based assessment, and automated grading
- Learner progress dashboard with completion status, quiz scores, and time-in-content recording
- Manager team view showing direct report progress, certification status, and compliance deadlines

### Adaptive Learning & Skills

- Adaptive learning path sequencing based on real-time quiz performance and engagement signals
- Skills framework management linking courses to role competency profiles (ESCO, O*NET)
- Competency-based progression that gates advancement on demonstrated skill rather than seat time
- AI-powered skills gap analysis surfacing content recommendations from profile and performance data
- Automated skills taxonomy inference and maintenance from job description and performance data inputs

### Integrations & Standards

- LTI 1.3 for embedding and launching third-party tools and publisher content
- HRIS roster sync via REST API for Workday, SAP SuccessFactors, BambooHR, and similar systems
- SAML 2.0 and OAuth 2.0 SSO; LDAP authentication
- IMS Caliper Analytics sensor support for learning activity data export
- Reporting API enabling downstream analytics and data warehouse integration

### Accessibility & Reach

- WCAG 2.2 accessible interface meeting US, EU, and Australian institutional requirements
- Mobile-responsive web experience with offline content download for field-based learners
- Extended enterprise capability with separate learner portals and branded experiences for customers, partners, or contractors
- Natural-language analytics querying for L&D managers without data science skills

---

## AI-Native Advantage

AI is built into the platform rather than bolted on. Generative authoring produces complete course modules — structure, assessments, and multimedia — from a competency description in minutes, replacing hours of manual content development. Adaptive path sequencing uses live xAPI and Caliper signals plus a knowledge graph to continuously re-sequence content and adjust difficulty, going beyond the rules-based personalisation ("if score < 70%, show remediation") that characterises incumbents. A skills ontology agent infers and maintains a living skills graph from job descriptions, performance data, and standards such as ESCO and O*NET — work that currently runs as a $200K+ consulting engagement.

---

## Tech Stack & Deployment

The platform is designed to run self-hosted on-premises, in a private cloud, or as a managed cloud service — directly addressing data-sovereignty concerns that block Docebo and Cornerstone adoption in government, healthcare, and finance. It implements the full set of open eLearning standards: SCORM 1.2 / SCORM 2004, xAPI / cmi5, IMS LTI 1.3, IMS QTI, and IMS Caliper Analytics. SDK and integration surface includes a REST reporting API, LTI tool provider/consumer endpoints, an LRS-compatible activity store, SAML 2.0 / OAuth 2.0 SSO, and HRIS connectors for major HR systems.

---

## Market Context

The global LMS market was valued at approximately $28.9B in 2025 and is projected to reach $100.7B–$188.1B by 2032–2035 at a CAGR of 18.2%–20.6% (MarketsandMarkets; Research Nester). Incumbent pricing spans free Moodle hosting at the low end through Canvas at $5–$30/student/year, Cornerstone at $6–$18/user/month with 500-user minimums, and Docebo at a ~$25,000/year minimum. Primary buyers are Chief Learning Officers at enterprises (500–50,000 employees), VPs of HR / L&D at mid-market companies (100–500 employees), academic technology directors at universities, and IT / LMS administrators responsible for integrations and uptime.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
