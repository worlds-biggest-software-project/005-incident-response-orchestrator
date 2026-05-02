# Standards & API Reference

> Project: Incident Response Orchestrator · Generated: 2026-05-03

## Industry Standards & Specifications

### ISO Standards

#### ISO/IEC 27035 — Information Security Incident Management
- **Standard Numbers:** ISO/IEC 27035-1:2016, ISO/IEC 27035-2:2023
- **Official Link:** https://www.iso.org/standard/78974.html
- **Description:** International standard specifying planning, detection, reporting, assessment, and response procedures for IT security incidents. Provides a structured five-phase incident lifecycle: plan and prepare, detect and report, assess and decide, respond, and learn and improve. Organizations implementing this standard define security incident management processes aligned to operational and governance frameworks.

#### ISO/IEC 27001:2013 — Information Security Management
- **Official Link:** https://www.iso.org/standard/54534.html
- **Description:** Establishes information security incident management as a control objective (Annex A.16). ISO 27001 focuses specifically on managing security incidents to minimize impact on the organization. It mandates incident response procedures integrated with broader ISMS practices.

#### ISO/IEC 19464:2014 — Advanced Message Queuing Protocol (AMQP) v1.0
- **Official Link:** https://www.iso.org/standard/64955.html
- **Description:** International standard for AMQP, a message-oriented middleware protocol. Relevant for incident alert routing, async notification delivery, and reliable event queuing in incident orchestration workflows. Provides standardized error handling and message reliability guarantees.

### W3C & IETF Standards

#### RFC 6749 — The OAuth 2.0 Authorization Framework
- **Official Link:** https://datatracker.ietf.org/doc/html/rfc6749
- **Description:** IETF standard defining OAuth 2.0 authorization flows. Essential for incident response platforms requiring secure API access, third-party integrations (Slack, Jira, PagerDuty), and delegated permissions for incident automation workflows.

#### RFC 6750 — OAuth 2.0 Bearer Token Usage
- **Official Link:** https://www.ietf.org/rfc/rfc6750.txt
- **Description:** Specifies how to use bearer tokens in HTTP requests to access OAuth 2.0 protected resources. Supports stateless authentication for incident API endpoints and webhook integrations.

#### OpenID Connect Core 1.0
- **Official Link:** https://openid.net/specs/openid-connect-core-1_0.html
- **Description:** Identity layer built on OAuth 2.0. Enables single sign-on (SSO) for incident response teams, multi-tenant user management, and user identity assertions in incident workflows.

#### OpenAPI Specification v3.2.0
- **Official Link:** https://spec.openapis.org/oas/v3.2.0.html
- **Description:** Vendor-neutral format for describing REST APIs. Industry standard for incident orchestrator API documentation, enabling API discovery, client SDK generation, and contract-driven testing for incident management integrations.

#### GraphQL Specification
- **Official Link:** https://spec.graphql.org/October2021/
- **Description:** Query language and execution engine for flexible, client-driven data retrieval. Alternative to REST for incident API, enabling clients to request only required fields (incident metadata, timelines, attachments) and reducing bandwidth for mobile incident responders.

### Data Model & API Specifications

#### JSON Schema (Draft 2020-12)
- **Official Link:** https://json-schema.org/
- **Description:** Standard for validating JSON data structures. Critical for incident orchestrator data model validation: incident payloads, alert schemas, runbook parameters, postmortem templates. OpenAPI 3.1.0 provides native JSON Schema integration.

#### OpenTelemetry Protocol (OTLP)
- **Official Link:** https://opentelemetry.io/docs/specs/otel/protocol/
- **Description:** CNCF standard protocol for sending telemetry data (metrics, logs, traces) to observability backends. Incident orchestrators consume OTLP signals from Datadog, New Relic, Prometheus, and other vendors to trigger and contextualize incidents. Provides vendor-neutral data format.

#### AsyncAPI Specification
- **Official Link:** https://www.asyncapi.com/
- **Description:** Defines asynchronous API patterns (message brokers, webhooks, pub/sub). Essential for incident webhook specifications, real-time alert ingestion from monitoring systems, and event-driven automation workflows.

#### Prometheus Alertmanager Management API
- **Official Link:** https://prometheus.io/docs/alerting/latest/management_api/
- **Description:** Standard REST API for alert ingestion, routing, grouping, and silencing in Prometheus ecosystems. Defines the canonical pattern for metric-based alert payloads and alert lifecycle management.

### Security & Authentication Standards

#### NIST Cybersecurity Framework (CSF) 2.0 — Respond & Recover Functions
- **Official Link:** https://www.nist.gov/cyberframework
- **Description:** Government-backed framework defining six cybersecurity functions: Govern, Identify, Protect, Detect, Respond, Recover. Incident response orchestrators map to the Respond function (RS: Actions regarding detected incidents) and Recover function (RC: Restoration of affected assets and operations).

#### NIST Special Publication 800-61 Rev. 3
- **Official Link:** https://csrc.nist.gov/pubs/sp/800/61/r3/final
- **Description:** Updated 2025. Incident Response Recommendations and Considerations for Cybersecurity Risk Management mapped to NIST CSF 2.0. Defines authoritative incident response phases: Preparation, Detection & Analysis, Containment/Eradication/Recovery, Post-Incident Activity. Provides playbook templates and assessment criteria.

#### OWASP Incident Response Guidance
- **Official Link:** https://owasp.org/www-project-agentic-skills-top-10/incident-response.html
- **Description:** Structured playbook patterns for web application and generative AI security incidents. Includes best practices for incident declaration, communication, automation, and postmortem analysis. OWASP GenAI Incident Response Guide v1.0 aligns with NIST SP 800-61r3 and MITRE ATLAS.

#### ITIL 4 — Incident Management Process
- **Official Link:** https://www.axelos.com/certifications/itil-certifications
- **Description:** IT Infrastructure Library defines canonical six-step incident management process: identification, logging, categorisation, prioritisation, diagnosis, resolution. Most enterprise incident tools map workflows to ITIL terminology for process governance.

### Reliability & SRE Standards

#### Google Site Reliability Engineering (SRE) — SLO/SLI/Error Budget Framework
- **Official Link:** https://sre.google/workbook/implementing-slos/
- **Description:** Industry de-facto standard for defining Service Level Indicators (SLIs), Service Level Objectives (SLOs), and error budgets. Incident orchestrators increasingly use SLO-aware severity classification to prioritize incidents based on reliability impact rather than manual assignment.

### MCP Server Specifications

#### Model Context Protocol (MCP) — Version 2025-11-25
- **Official Link:** https://modelcontextprotocol.io/specification/2025-11-25
- **Description:** Open protocol standardizing integration between LLM applications and external tools/data sources. Enables incident orchestrators to expose runbooks, playbooks, and incident context as MCP resources and tools, allowing AI agents to autonomously execute remediation steps with guardrails.

#### MCP Server Architecture & Transport
- **Standards:** JSON-RPC 2.0 over stdio or Server-Sent Events (SSE)
- **Description:** MCP servers expose Resources (data retrieval), Tools (side-effect execution), and Prompts (reusable workflows). Incident orchestrators implementing MCP allow LLM-based automation to read runbooks in natural language, evaluate system state, execute safe remediations, and escalate complex decisions.

---

## Similar Products — Developer Documentation & APIs

### PagerDuty
- **Description:** Market-leading on-call alerting, escalation policies, and incident lifecycle management with 700+ integrations. Event Intelligence (ML-based alert deduplication) is the most mature in the category. AI-generated incident summaries and postmortem drafts are premium add-ons.
- **API Documentation:** https://developer.pagerduty.com/api-reference/
- **API Capabilities:** Events API v2 (alert ingestion), REST API (incident CRUD, escalation), webhooks for event subscriptions
- **SDKs:** Python, JavaScript/Node.js, Go, Ruby, Java available via official repositories
- **Developer Guide:** https://developer.pagerduty.com/docs/
- **Standards:** REST/JSON (OpenAPI-documented), OAuth 2.0 authentication, webhook subscriptions
- **Authentication:** OAuth 2.0 / API Token

### incident.io
- **Description:** All-in-one Slack-native incident management combining on-call scheduling, status pages, and AI-generated postmortems in a single mid-market product. Frictionless Slack UX with /incident slash commands. Postmortem drafts auto-populate from incident timelines.
- **API Documentation:** https://api-docs.incident.io/
- **API Capabilities:** Incident CRUD, on-call schedule queries, postmortem generation, status page updates
- **SDKs:** JavaScript, Python libraries available
- **Developer Guide:** https://docs.incident.io/
- **Standards:** REST/JSON, OpenAPI 3.x specification, rate limit 1200 req/min per API key
- **Authentication:** API Key (bearer token)

### Rootly
- **Description:** Slack-native incident workflow automation with AI-generated postmortems and guided runbook execution. Strong in automating response steps triggered on incident declaration. Runbook execution integrated within Slack incident channel to avoid context switching.
- **API Documentation:** https://docs.rootly.com/incidents/incidents
- **API Capabilities:** Custom incident automation workflows, AI runbook execution, postmortem generation from Slack conversation context
- **SDKs:** Node.js/TypeScript SDKs available
- **Developer Guide:** https://rootly.com/sre/rootly-api-custom-automations-for-incident-control
- **Standards:** REST/JSON, OpenAPI-documented, webhook subscriptions for automation triggers
- **Authentication:** API Key / OAuth 2.0

### FireHydrant
- **Description:** Full incident lifecycle platform with 350+ API endpoints, runbooks, retros, and service catalog. Provides service ingestion automation via YAML or API. Strong postmortem and retrospective tooling. Acquired by Freshworks (December 2025); future roadmap uncertain post-acquisition.
- **API Documentation:** https://docs.firehydrant.com/reference/firehydrant-api
- **API Capabilities:** Incident declaration/updates, service catalog management, change events, runbook execution, retrospectives
- **SDKs:** Go, Python, TypeScript/Node.js SDKs available via GitHub
- **Developer Guide:** https://docs.firehydrant.com/docs/
- **Standards:** REST/JSON, OpenAPI 3.0, Terraform support for infrastructure-as-code
- **Authentication:** Bearer Token (API key or bot token)

### Datadog
- **Description:** Comprehensive observability platform with native incident management. Incidents API allows creation and management of incidents linked to monitors. Integration with Datadog On-Call for escalation and Workflow Automation for complex runbook orchestration.
- **API Documentation:** https://docs.datadoghq.com/api/latest/incidents/
- **API Capabilities:** Create/update incidents, incident services, timeline events, metric-based severity inference
- **SDKs:** Python, JavaScript, Go, Ruby, Java available
- **Developer Guide:** https://docs.datadoghq.com/getting_started/incident_management/
- **Standards:** REST/JSON, OpenAPI 3.0, OTLP ingestion for telemetry
- **Authentication:** API Key + Application Key (dual-key system)

### Prometheus + Alertmanager
- **Description:** Open-source standard for metric-based alerting. Alertmanager handles alert grouping, routing, silencing, and notification. Widely used in Kubernetes and cloud-native environments. Foundation for alert ingestion in many incident orchestrators.
- **API Documentation:** https://prometheus.io/docs/alerting/latest/management_api/
- **API Capabilities:** Alert ingestion (/api/v2/alerts), silence management, receiver configuration, status endpoint
- **SDKs:** Prometheus client libraries in Python, Go, Ruby, Node.js, Java
- **Developer Guide:** https://prometheus.io/docs/tutorials/alerting_based_on_metrics/
- **Standards:** REST/JSON, OpenAPI-documented (swagger spec available), gRPC remote write protocol
- **Authentication:** Basic auth (if exposed behind reverse proxy); typically internal to cluster

### Squadcast
- **Description:** SRE-focused incident management with reliability workflows, on-call scheduling, and error budget tracking integrated with incident lifecycle. Cost-effective PagerDuty alternative with growing feature parity. Native SLO-aware incident context.
- **API Documentation:** https://developers.squadcast.com/api/
- **API Capabilities:** On-call schedule queries, incident CRUD, escalation policies, service topology/dependency mapping
- **SDKs:** Python, JavaScript/Node.js available
- **Developer Guide:** https://support.squadcast.com/
- **Standards:** REST/JSON, v3 API endpoints (v2 deprecated), OWASP API security alignment
- **Authentication:** API Token / Bearer Token

### Shoreline.io
- **Description:** AI-driven automated remediation platform acquired by NVIDIA. Transforms static runbooks into live notebooks with real-time debug data and pre-approved repair activities. Auto-remediation of 50% of incidents in seconds; remaining 50% debugged and resolved in minutes. MTTR reduction >75%.
- **API Documentation:** https://www.shoreline.io/ (product focused; limited public API docs)
- **API Capabilities:** Automatic remediation execution, runbook library (120+ templates), monitor/alarm creation, fleet-scale incident response
- **SDKs:** Terraform support for infrastructure automation
- **Developer Guide:** https://www.shoreline.io/blog/the-guide-to-automating-runbook-execution
- **Standards:** Cloud-agnostic API, integrates with Kubernetes, AWS, GCP, observability tools via webhooks
- **Authentication:** API Key / RBAC tokens

### Grafana Loki + Alerting
- **Description:** Open-source log aggregation and log-based alerting. Loki Ruler evaluates LogQL queries and sends alerts to Alertmanager. Complements metric-based alerting with log context. Part of the CNCF observability stack.
- **API Documentation:** https://grafana.com/docs/loki/latest/alert/
- **API Capabilities:** Alert rule creation/management, log querying, Alertmanager integration, ruler ring configuration
- **SDKs:** Python (Loki SDK), Prometheus client libraries for metrics
- **Developer Guide:** https://grafana.com/docs/grafana/latest/alerting/set-up/configure-alertmanager/
- **Standards:** REST/JSON, LogQL query language (Prometheus-like), OpenTelemetry receiver support
- **Authentication:** API Token / OAuth 2.0 via Grafana (if exposed through Grafana dashboard)

---

## Standards Gaps & Emerging Areas

### Autonomous Runbook Execution
Current standards (ITIL, NIST SP 800-61) define runbooks as static procedures executed by humans. No formal standard yet exists for AI-driven autonomous execution with human guardrails. MCP specification (2025-11-25) provides the transport layer but execution semantics (confidence thresholds, escalation logic) remain vendor-specific.

### Cross-Incident Pattern Mining
No published standard for LLM-based postmortem corpus analysis to identify systemic fragilities. OWASP GenAI Incident Response Guide (2025) discusses AI incident handling but not organizational-scale pattern analysis. Zalando's 2025 case study validates the capability but standards-bodies have not yet formalized guidance.

### SLO-Aware Severity Classification
Google SRE framework defines SLO/SLI/error budget concepts, but no standardized wire format for incident severity inference based on SLO impact. Individual platforms (Squadcast, Datadog) implement proprietary approaches; standardization via OpenAPI extension or IETF RFC proposed but not yet ratified.

### AI Agent Incident Response Playbooks
NIST SP 800-61 Rev. 3 aligns incident response to CSF 2.0 functions but assumes human decision-makers. MITRE ATLAS (AI threat taxonomy) and OWASP LLM Top-10 define attack vectors; OWASP GenAI Incident Response Guide (2025) provides playbook patterns but lacks formal specification for AI agent decision boundaries and confidence scoring.

### Alert Correlation and Triage Semantics
OpenTelemetry (OTLP) provides telemetry transport but no standard semantics for alert correlation metadata (deployment context, dependency graphs, historical patterns). Individual vendors implement proprietary correlation engines; no industry consensus on data model for semantic deduplication.

### Webhook Signature and Delivery Guarantees
OpenAPI and AsyncAPI define webhook schemas but lack standardized signature verification and at-least-once delivery semantics. OWASP guidance exists but no IETF RFC. Critical for secure incident ingestion from monitoring systems.

### MCP for Incident Automation
MCP 2025-11-25 specification is nascent. No incident-response-specific MCP server registry, runbook-sharing repository, or standardized incident context schema. Incident orchestrators will need to define canonical resource types (runbooks, playbooks, escalation policies) as MCP extensions.

---

## Notes

### Standards Maturity and Adoption

**Mature, widely adopted (8+ years):**
- OAuth 2.0 (RFC 6749, 2012)
- OpenAPI (2016, formalized as OAS 3.0)
- ITIL 4 (2019)
- NIST SP 800-61 Rev. 2 (2012) → Rev. 3 (2025)

**Emerging, rapid adoption (0–3 years):**
- OpenTelemetry (CNCF 2019, production maturity 2023–2024)
- NIST CSF 2.0 (2024, mapped to SP 800-61 Rev. 3 in 2025)
- Model Context Protocol (2024, OpenAI adoption Sept 2025)
- OWASP GenAI Incident Response Guide (2025)

**Underspecified, vendor-specific:**
- Autonomous runbook execution
- Cross-incident pattern mining
- SLO-aware severity inference
- Alert correlation metadata

### Recommended Alignment

For the Incident Response Orchestrator project:

1. **API Design:** Align REST API to OpenAPI 3.1 (JSON Schema 2020-12 native support) and OAuth 2.0 for third-party integrations.
2. **Incident Lifecycle:** Map to NIST SP 800-61 Rev. 3 phases (Preparation, Detection & Analysis, Containment/Eradication/Recovery, Post-Incident Activity) and ITIL terminology for enterprise adoption.
3. **Telemetry Ingestion:** Support OpenTelemetry Protocol (OTLP) for vendor-neutral alert/trace collection. Provide Prometheus Alertmanager compatibility for cloud-native users.
4. **SRE Integration:** Implement error budget and SLO-aware context using Google SRE framework (SLI/SLO/error budget definitions).
5. **AI Automation:** Implement MCP (2025-11-25) as the foundation for AI agent runbook execution, exposing runbooks/playbooks as MCP resources with confidence thresholds and escalation guardrails (NIST AI 600-1 guidance).
6. **Security:** Align incident response procedures to OWASP guidance, support mTLS for internal service-to-service communication, and implement GDPR/CCPA-aware audit logging (ISO 27001 Annex A.16).
7. **Postmortem Automation:** Design LLM-based postmortem generation for alignment with OWASP GenAI Incident Response Guide and emerging standards for responsible AI in security operations.

### Key Sources & Further Reading

- **NIST Publications:** https://csrc.nist.gov/ (incident response, cybersecurity framework, AI governance)
- **OpenTelemetry:** https://opentelemetry.io/ (observability standards)
- **OpenAPI Initiative:** https://www.openapis.org/ (API standards)
- **OWASP:** https://owasp.org/ (security incident response, AI incident handling, LLM top-10)
- **Google SRE:** https://sre.google/ (reliability engineering best practices)
- **IETF Datatracker:** https://datatracker.ietf.org/ (OAuth, AMQP, emerging standards)
- **Model Context Protocol:** https://modelcontextprotocol.io/ (AI automation)
