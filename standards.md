# Standards & API Reference

> Project: Learning Management System · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**IEEE 1484.12.1-2020 — IEEE Standard for Learning Object Metadata (LOM)**
- URL: https://standards.ieee.org/standard/1484_12_1-2020.html
- Defines a conceptual data schema specifying the structure of metadata for learning objects (any digital or non-digital entity used for learning, education, or training). LOM metadata covers general, lifecycle, educational, technical, rights, relation, annotation, and classification categories. Relevant for any LMS catalogue or content repository that needs to tag, search, and reuse learning objects in an interoperable way.

**ISO/IEC 40500:2012 — Web Content Accessibility Guidelines (WCAG) 2.0**
- URL: https://www.iso.org/standard/58625.html
- ISO adoption of W3C's WCAG 2.0. Educational institutions in the US (ADA Title II), EU (European Accessibility Act), and Australia (DDA) are legally required to meet at minimum WCAG 2.1 Level AA; WCAG 2.2 (2023) is the current normative baseline for new LMS development. Any LMS MVP must satisfy WCAG 2.2 AA to achieve legal and institutional procurement compliance.

### W3C & IETF Standards

**W3C Web Content Accessibility Guidelines (WCAG) 2.2**
- URL: https://www.w3.org/TR/WCAG22/
- The current normative accessibility standard for web applications. Adds nine new success criteria beyond WCAG 2.1, including focus appearance, dragging movements, and accessible authentication. Compliance is legally mandated for educational LMS deployments in the EU, US, and Australia. LMS platforms are routinely evaluated against WCAG 2.2 AA during institutional procurement.

**W3C Verifiable Credentials Data Model 2.0 (VC)**
- URL: https://www.w3.org/TR/vc-data-model-2.0/
- The W3C standard underpinning digital credentials, micro-credentials, and Open Badges 3.0. Both 1EdTech Open Badges 3.0 and the Comprehensive Learner Record (CLR) 2.0 are designed as VC-compliant documents. An LMS issuing verifiable certificates or badges must implement this model for cryptographic verification and portability.

**RFC 7519 — JSON Web Tokens (JWT)**
- URL: https://datatracker.ietf.org/doc/html/rfc7519
- Compact, URL-safe means of representing claims between two parties. JWTs are the token format used by LTI 1.3, OAuth 2.0 bearer tokens, and OpenID Connect ID tokens — all required for modern LMS-to-tool integrations and SSO. Any LMS implementing LTI 1.3 or OIDC must correctly validate and issue signed JWTs.

**RFC 6749 — OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- The authorization framework underlying LTI 1.3 service authentication, HRIS integrations, and third-party content marketplace connectors. LMS platforms use OAuth 2.0 client credentials grant for machine-to-machine API access and authorization code flow for user-delegated API access.

**RFC 7591 / RFC 7592 — OAuth 2.0 Dynamic Client Registration**
- URL: https://datatracker.ietf.org/doc/html/rfc7591
- Used by LTI 1.3 to enable dynamic registration of external tools without manual credential exchange. Institutions increasingly require dynamic registration support to simplify the LTI tool integration workflow.

### Data Model & API Specifications

**xAPI (Experience API) — ADL Specification**
- URL: https://github.com/adlnet/xAPI-Spec
- Implementation Guide: https://adlnet.gov/projects/xapi/
- The primary learning activity data exchange format. Defines a REST API (Learning Record Store, LRS) and a JSON statement model (`actor → verb → object`) for recording learning events from any context — LMS, mobile app, simulator, on-the-job activity. An LMS must implement both an xAPI sender (for content launched within the LMS) and optionally a compliant LRS endpoint for storing statements from external sources.

**SCORM (Sharable Content Object Reference Model) 1.2 / 2004**
- URL: https://scorm.com/scorm-explained/technical-scorm/
- ADL SCORM 2004 4th Edition: https://adlnet.gov/projects/scorm/
- The dominant legacy standard for packaging and runtime communication between eLearning content and an LMS. SCORM 1.2 uses a JavaScript API for completion/score reporting; SCORM 2004 adds sequencing and navigation. Both remain mandatory table-stakes features; the LMS must implement the full SCORM runtime API to support the large installed base of SCORM-packaged content.

**cmi5 — AICC/ADL Profile of xAPI**
- URL: https://aicc.github.io/CMI-5_Spec_Current/
- GitHub: https://github.com/AICC/CMI-5_Spec_Current
- The modern successor to SCORM for LMS-to-content communication. cmi5 defines standard launch parameters, session lifecycle, and statement vocabulary as an xAPI profile, bridging SCORM's simplicity with xAPI's flexibility. Platforms targeting enterprise or government buyers are increasingly expected to support cmi5 alongside SCORM.

**OpenAPI Specification 3.1 (OAS)**
- URL: https://spec.openapis.org/oas/v3.1.0
- The de-facto standard for documenting REST APIs. An LMS should publish its integration API as an OpenAPI 3.1 document to enable automated client generation, interactive API explorers (Swagger UI/Redoc), and third-party integration tooling. All major commercial LMS platforms (Docebo, Absorb, D2L Brightspace) publish OpenAPI-conformant API documentation.

### 1EdTech (IMS Global) Consortium Standards

**IMS LTI (Learning Tools Interoperability) 1.3 + LTI Advantage**
- Core Specification: https://www.imsglobal.org/spec/lti/v1p3
- 1EdTech Overview: https://www.1edtech.org/standards/lti
- Why Adopt: https://www.1edtech.org/standards/lti/why-adopt-lti-1p3
- The primary interoperability standard for embedding and launching third-party tools (assessment engines, video platforms, virtual labs, publisher content) within an LMS. LTI 1.3 replaces OAuth 1.0a signing (used in LTI 1.1) with OpenID Connect and signed JWTs. LTI Advantage bundles three mandatory service extensions: Names and Role Provisioning Services (NRPS), Deep Linking 2.0, and Assignment and Grade Services (AGS). Any LMS MVP targeting institutional adoption must certify LTI Advantage compliance.

**IMS Caliper Analytics 1.2**
- Specification: https://www.imsglobal.org/spec/caliper/v1p2
- Implementation Guide: https://www.imsglobal.org/spec/caliper/v1p2/impl
- GitHub: https://github.com/1EdTech/caliper-spec
- A sensor framework and event vocabulary for capturing granular learning activity data from LMS and EdTech applications and transmitting it to analytics endpoints. Caliper defines 18 metric profiles covering sessions, assessments, media, reading, and tool interactions. Complements xAPI; Caliper is more widely adopted in North American higher education analytics pipelines. LMS platforms targeting higher-ed analytics integrations should implement Caliper sensor emission.

**IMS QTI (Question and Test Interoperability) 3.0**
- Specification: https://www.imsglobal.org/spec/qti/v3p0/oview
- Implementation Guide: https://www.imsglobal.org/spec/qti/v3p0/impl
- Beginner's Guide: https://www.imsglobal.org/spec/qti/v3p0/guide
- The standard for authoring, exchanging, and delivering assessment items and tests across platforms. QTI 3.0 adds native HTML5 rendering (eliminating transform-based rendering), Computer Adaptive Testing (CAT) support, Portable Custom Interactions (PCI) for technology-enhanced items, and integrated APIP accessibility features. An LMS quiz engine should support QTI 3.0 import/export to enable interoperability with item banks and assessment platforms.

**1EdTech Open Badges 3.0**
- URL: https://www.1edtech.org/standards/open-badges
- W3C Verifiable Credential-based digital badge standard for recognising learning achievements. Open Badges 3.0 is designed to be included as achievements within a Comprehensive Learner Record (CLR 2.0). LMS platforms offering micro-credential or certification issuance should implement Open Badges 3.0 for cryptographically verifiable, portable recognition.

**1EdTech Comprehensive Learner Record (CLR) Standard 2.0**
- URL: https://www.1edtech.org/standards/clr
- Specification: https://www.imsglobal.org/spec/clr/v2p0
- Next-generation standard for secure, verifiable lifetime learning records encompassing courses, competencies, skills, and employer-recognised achievements. CLR 2.0 is VC-based (W3C Verifiable Credentials). Recommended by AACRAO as the standard for lifetime learning records. Relevant for any LMS targeting higher-education or skills-based learning where learner achievement portability is a requirement.

### Security & Authentication Standards

**SAML 2.0 (Security Assertion Markup Language)**
- URL: https://docs.oasis-open.org/security/saml/Post2.0/sstc-saml-tech-overview-2.0.html
- The enterprise SSO standard for LMS integration with institutional identity providers (Active Directory, Okta, Azure AD, Shibboleth). SAML 2.0 is the predominant SSO protocol in higher education (via Shibboleth federation) and government deployments. Any LMS targeting institutional buyers must support SAML 2.0 SP-initiated and IdP-initiated flows.

**OpenID Connect 1.0 (OIDC)**
- URL: https://openid.net/specs/openid-connect-core-1_0.html
- Identity layer built on OAuth 2.0 and JWT; the authentication protocol used by LTI 1.3, corporate SSO integrations (Google Workspace, Microsoft Entra ID), and modern API authentication flows. OIDC is the preferred protocol for consumer-facing LMS deployments and is increasingly adopted by enterprises transitioning away from SAML.

**OWASP Application Security Verification Standard (ASVS) Level 2**
- URL: https://owasp.org/www-project-application-security-verification-standard/
- Framework for web application security testing and verification. LMS platforms handling student PII, assessment data, and HRIS payloads should target ASVS Level 2 compliance. Key controls include input validation, session management, access control, cryptography, and API security.

**NIST SP 800-63B — Digital Identity Guidelines (Authentication)**
- URL: https://pages.nist.gov/800-63-3/sp800-63b.html
- US federal standard for digital authentication assurance levels (AAL1–AAL3). Relevant for LMS deployments serving US government agencies or institutions requiring phishing-resistant authentication for administrators and instructors.

### Regulatory Frameworks

**GDPR (General Data Protection Regulation) — EU 2016/679**
- URL: https://gdpr-info.eu/
- Applies whenever an LMS processes personal data of EU residents. Requires lawful basis for processing learner behavioural data, explicit consent or legitimate interest for AI-based personalisation, data minimisation, the right to erasure, data portability, and a Data Processing Agreement (DPA) with all sub-processors. LMS platforms using learner data to train shared AI models must obtain explicit consent or ensure data is not used beyond tenant boundaries.

**FERPA (Family Educational Rights and Privacy Act) — US**
- URL: https://studentprivacy.ed.gov/
- Governs how US educational institutions handle student educational records. LMS vendors acting as "school officials" must sign a FERPA-compliant data agreement prohibiting commercial use of student data, mandating breach notification, and enforcing data retention/disposal policies. Behavioural engagement metrics collected by modern LMS platforms (page views, time-on-task, discussion posts) are commonly classified as educational records under FERPA.

**EU AI Act (Regulation 2024/1689) — Annex III High-Risk AI**
- URL: https://artificialintelligenceact.eu/annex/3/
- Compliance Deadline: August 2, 2026
- AI systems used in education to determine access, evaluate learning outcomes, or steer learning processes are classified as high-risk under Annex III. From August 2026, LMS platforms deploying AI that influences assessment decisions or learning progression in EU markets must implement: a risk management system, training data governance documentation, transparency and explainability mechanisms, human oversight controls, and accuracy/robustness monitoring. The "Digital Omnibus" legislative package (proposed late 2025) could extend this deadline to December 2027, but should not be relied upon.

---

## Similar Products — Developer Documentation & APIs

### Moodle

- **Description:** World's most widely deployed open-source LMS with 1,700+ plugins and support for SCORM, xAPI, and LTI. Built on PHP/MySQL; community-governed under Moodle HQ.
- **API Documentation:** https://moodledev.io/docs/5.1/apis (Developer Resource Hub — current release)
- **Web Services Reference:** https://docs.moodle.org/dev/Web_service_API_functions
- **External Services Guide:** https://moodledev.io/docs/5.0/apis/subsystems/external
- **SDKs/Libraries:** No official SDK; community REST client libraries available in Python, JavaScript, Ruby, and PHP via the Moodle developer community
- **Developer Guide:** https://moodledev.io — primary developer portal with plugin development, REST API, and hook documentation
- **Standards:** REST (XML/JSON responses); `wstoken`-authenticated via `GET`/`POST` with `wsfunction` parameter; non-standard URL scheme
- **Authentication:** Token-based (API token obtained via admin or user login); LDAP, SAML 2.0, and OAuth 2.0 for user authentication

### Canvas (Instructure)

- **Description:** Leading SaaS LMS in North American higher education; open-core (AGPL v3 community edition); rich LTI ecosystem and clean modern UX.
- **API Documentation:** https://developerdocs.instructure.com/services/canvas (Instructure Developer Documentation Portal — primary)
- **REST API Reference:** https://canvas.instructure.com/doc/api/
- **SDKs/Libraries:** Official Canvas Ruby gem; community Python (`canvasapi`), Node.js, and .NET wrappers; see https://github.com/instructure
- **Developer Guide:** https://developerdocs.instructure.com (includes OAuth setup, rate limits, pagination, and versioning)
- **Standards:** REST/JSON; OpenAPI-compatible; pagination via `Link` headers; versioning via URL path (`/api/v1/`)
- **Authentication:** OAuth 2.0 authorization code flow; API tokens for developer/admin access; LTI 1.3 for tool integrations

### D2L Brightspace

- **Description:** Cloud-native LMS with 20% North American higher-education enrollment share; leading AI features (Binder, Le@n) and strong competency-based education support.
- **API Documentation:** https://docs.valence.desire2learn.com/index.html (Valence Developer Platform — updated April 2026)
- **API Properties & Versioning:** https://docs.valence.desire2learn.com/res/apiprop.html
- **SDKs/Libraries:** D2L Web Services SDK (.NET): https://github.com/Brightspace/d2lws-sdk; community Python and JavaScript wrappers
- **Developer Guide:** https://community.d2l.com/brightspace/kb/articles/1102-getting-started-with-brightspace-api-automation
- **Standards:** REST/JSON; OAuth 2.0; platform-neutral by design (supports GET, DELETE, POST, PUT via HTTPS); versioned endpoints
- **Authentication:** OAuth 2.0; ID keypair (App ID + App Key) for legacy Valence authentication; transitioning to OAuth 2.0 client credentials for new integrations

### Docebo

- **Description:** AI-native corporate LMS ($243M revenue, 2025); leading generative AI content authoring (Docebo Creator), adaptive paths, and skills taxonomy automation.
- **API Documentation:** https://developer.docebo.com/ (Docebo Developer Portal)
- **API Browser:** Available at `https://<your-platform>.docebosaas.com/api-browser/` for tenant-specific interactive reference
- **API Guides:** https://developer.docebo.com/docs/api-guides
- **SDKs/Libraries:** No official SDK; REST-based with JSON; community integrations via Zapier, MuleSoft, and Workato connectors
- **Developer Guide:** https://developer.docebo.com/docs/get-started-with-the-docebo-api-browser
- **Standards:** REST/JSON; OpenAPI-compatible; versioned; OAuth 2.0 bearer token
- **Authentication:** OAuth 2.0 (full OAuth 2.0 server built-in; client credentials and authorization code flows supported)

### Absorb LMS

- **Description:** Mid-market corporate LMS with generative AI course creation (Create AI); REST API with multi-region deployment; $6–$16/user/month.
- **API Documentation:** https://docs.myabsorb.com/ (Integration API v2 — full reference)
- **Integration API v2:** https://docs.myabsorb.com/integration-api/v2/docs
- **REST Endpoints (by region):**
  - US: https://rest.myabsorb.com
  - EU: https://rest.myabsorb.eu
  - AU: https://rest.myabsorb.com.au
- **SDKs/Libraries:** Community Ruby wrapper: https://github.com/npezza93/absorb_api; Python dlt source via https://dlthub.com/context/source/absorb-lms
- **Standards:** REST/JSON; versioned via `x-api-version` header; multi-region base URLs
- **Authentication:** API token (`x-api-key` private key + admin credentials POST to `/authenticate`); token-based auth on all subsequent requests

### Cornerstone OnDemand

- **Description:** Enterprise corporate LMS/HCM with deep compliance training management, skills graph, and extended enterprise; ~7,000 customers; ~$830M revenue.
- **API Documentation:** https://csod.dev/guides/getting-started/ (Cornerstone Developer Portal)
- **Reporting API (RAPI):** https://csod.dev/guides/reporting/rapi/
- **SDKs/Libraries:** Community JavaScript client: https://github.com/digitregroup/cornerstone-client
- **GitHub:** https://github.com/cornerstoneondemand
- **Standards:** REST/JSON; OAuth 2.0; SCORM, xAPI, AICC, and cmi5 content standards supported natively
- **Authentication:** OAuth 2.0 client credentials grant; client ID and secret required (provisioned by System Administrator — no self-service registration); tokens expire after 3,600 seconds; rate limits are contract-specific and not publicly documented

### Open edX

- **Description:** Open-source MOOC-grade learning platform (AGPL v3) used by MIT, Harvard, Google, and major enterprises; governed by Axim Collaborative (non-profit).
- **API Documentation:** https://docs.openedx.org/projects/edx-platform/en/latest/references/lms_apis.html (LMS API Reference — latest release)
- **REST API Concepts:** https://docs.openedx.org/projects/edx-platform/en/latest/concepts/rest_apis.html
- **Interactive API Explorer:** Available at `/api-docs/` on any Open edX installation (Swagger UI)
- **SDKs/Libraries:** `api-doc-tools` for generating OpenAPI docs: https://github.com/openedx/api-doc-tools; community Python and JavaScript clients
- **Developer Guide:** https://blog.lawrencemcdaniel.com/getting-started-with-open-edx-apis/ (community guide); official at https://docs.openedx.org
- **Standards:** REST/JSON; JWT bearer token authentication; OpenAPI 3.x documentation via Swagger
- **Authentication:** JWT token (obtained via `/oauth2/access_token` endpoint); personal access tokens for developer use; machine-to-machine via client credentials

---

## Notes

### Emerging & Evolving Areas

- **AI Act Uncertainty:** The EU AI Act Annex III high-risk compliance deadline (August 2, 2026) for education AI is subject to potential postponement via the "Digital Omnibus" package, but should be treated as binding during development planning.
- **W3C Verifiable Credentials adoption:** Open Badges 3.0 and CLR 2.0 are VC-based, but tooling for cryptographic verification at scale (DID methods, revocation registries) is still maturing. Implementing VC-native credential issuance in 2026 is achievable but requires careful selection of DID method (e.g., `did:web` for institutional deployments).
- **cmi5 adoption pace:** cmi5 is the endorsed SCORM successor, but installed-base content remains predominantly SCORM 1.2/2004. An LMS must support all three for the foreseeable future; cmi5 support can be positioned as a differentiator for new content authoring workflows.
- **LTI 1.1 deprecation:** 1EdTech has not formally sunset LTI 1.1, but major commercial LMS platforms are dropping support. An AI-native LMS should implement LTI 1.3 + LTI Advantage only and not invest engineering effort in LTI 1.1 compatibility.
- **Caliper vs. xAPI:** No convergence standard exists between Caliper and xAPI; deploying both sensor libraries increases instrumentation overhead. For a new platform, xAPI + LRS is the more portable and widely tooled choice; Caliper sensor support can be added as a plugin for higher-education market penetration.
