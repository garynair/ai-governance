# AI Governance

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)

A curated list of standards, regulations, tools, and platforms for governing AI systems — from regulatory compliance in regulated industries down to runtime policy enforcement for autonomous agents.

**Scope:** Anything that materially helps a practitioner build, ship, audit, or operate AI — including autonomous agents — in a way that is accountable, auditable, and compliant. Not pure AI ethics commentary, alignment philosophy, or generic AI news.

**Why now:** The EU AI Act's high-risk obligations under Annex III apply from 2 August 2026. ISO/IEC 42001 certification programs are live, and NIST AI RMF is production-ready. China's Interim Measures for generative AI have been in force since 2023, and India's DPDP Rules 2025 are now operationalising its data protection law with phased deadlines. The OWASP Agentic AI Top 10 documents real attack patterns. Claude Code, Copilot, Cursor, and autonomous agent frameworks are now standard tools in enterprise software teams. Governance is no longer optional.

Contributions welcome.

---

## Contents

- [Why Governance Matters](#why-governance-matters)
- [Regulatory Frameworks](#regulatory-frameworks)
- [International Standards and Standards Bodies](#international-standards-and-standards-bodies)
- [Industry Standards, Threat Models, and Guidance](#industry-standards-threat-models-and-guidance)
- [Research Papers](#research-papers)
- [Open-Source Governance Toolkits and Primitives](#open-source-governance-toolkits-and-primitives)
- [Free Governance Tools](#free-governance-tools)
- [Commercial and Enterprise Governance Platforms](#commercial-and-enterprise-governance-platforms)
- [Claude Code and MCP Governance](#claude-code-and-mcp-governance)
- [Policy Engines and Authorization](#policy-engines-and-authorization)
- [Audit, Observability, and Cost Control](#audit-observability-and-cost-control)
- [Security, Red-Teaming, and Threat Models](#security-red-teaming-and-threat-models)
- [Model and Data Governance](#model-and-data-governance)
- [Agentic Architecture Patterns](#agentic-architecture-patterns)
- [Bias, Fairness, and Impact Assessment](#bias-fairness-and-impact-assessment)
- [Government, Regulators, and Institutional Guidance](#government-regulators-and-institutional-guidance)
- [Learning Resources](#learning-resources)
- [Industry Conferences](#industry-conferences)
- [Newsletters and Blogs](#newsletters-and-blogs)
- [Books](#books)
- [Related Lists](#related-lists)

---

## Why Governance Matters

AI agents with tool access operate with the same blast radius as a poorly-scoped IAM role. They can read files they shouldn't, call APIs they weren't meant to, run up unbounded costs, and take irreversible actions — all without a governance layer.

Prompt injection causes agents to execute attacker-controlled instructions via untrusted tool output. Excessive agency allows agents to take actions beyond their intended scope. Unbounded costs emerge when agents loop or call expensive APIs without budget controls. Audit gaps mean that when something goes wrong, there is no record of what the agent did or why. Compliance exposure under the EU AI Act, ISO 42001, and NIST AI RMF requires documented governance evidence.

A governed agent runs with least-privilege tool access, an immutable audit trail, budget enforcement, and policy checks that fire before any irreversible action. A governed AI program, more broadly, can evidence to a regulator, auditor, or customer that the AI it ships is accountable and defensible.

---

## Regulatory Frameworks

- [EU Artificial Intelligence Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj) - The foundational EU regulation classifying AI systems by risk tier with mandatory requirements for high-risk systems. General-purpose AI model obligations effective August 2025. High-risk obligations under Annex III begin 2 August 2026.
- [EU AI Act Explorer](https://artificialintelligenceact.eu/) - Searchable explorer for the Act's articles, definitions, and timelines.
- [General-Purpose AI Code of Practice](https://code-of-practice.ai/) - Voluntary compliance instrument published by the European Commission in July 2025 for providers of general-purpose AI models under Articles 53 and 55 of the AI Act. Chapters on transparency, copyright, and safety and security.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) - NIST's voluntary framework for managing AI risk. Four functions: Govern, Map, Measure, Manage. Widely adopted as the US enterprise governance baseline and a procurement filter.
- [NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/) - Practical implementation guidance mapping each AI RMF subcategory to suggested actions, outcomes, and measurement approaches.
- [NIST AI 600-1: Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) - Companion profile to the AI RMF covering twelve risk areas specific to generative AI, including confabulation, information security, data privacy, and value-chain integration, plus specific considerations for agentic systems: planning, tool use, goal pursuit, and multi-step reasoning.
- [Executive Order 14110 on Safe, Secure, and Trustworthy AI](https://www.federalregister.gov/documents/2023/11/01/2023-24283/safe-secure-and-trustworthy-development-and-use-of-artificial-intelligence) - US federal requirements for AI safety testing, red-teaming, and disclosure for frontier models.
- [Blueprint for an AI Bill of Rights](https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/) - White House principles for AI systems that affect Americans. Rescinded as US federal policy in January 2025 and retained here only as an archived reference, its five principles still shape procurement language and several state-level bills.
- [UK ICO Guidance on AI and Data Protection](https://ico.org.uk/for-organizations/uk-gdpr-guidance-and-resources/artificial-intelligence/) - The UK regulator's positioning on automated decisions and AI under UK GDPR.
- [FCA Consumer Duty](https://www.fca.org.uk/firms/consumer-duty) - UK financial-services regulator's framework, increasingly applied to AI-mediated outcomes.
- [NHS DSPT](https://www.dsptoolkit.nhs.uk/) - NHS Data Security and Protection Toolkit. The compliance gate for healthtech ingesting NHS data.
- [Singapore Model AI Governance Framework](https://www.pdpc.gov.sg/help-and-resources/2020/01/model-artificial-intelligence-governance-framework) - Widely referenced voluntary framework from Singapore's PDPC. Practical and well-structured for deployers.
- [Canada Artificial Intelligence and Data Act (AIDA)](https://ised-isde.canada.ca/site/innovation-better-canada/en/artificial-intelligence-and-data-act) - Canada's proposed AI regulation, part of Bill C-27 (prorogued January 2025; did not become law). Retains relevance as the reference point for Canadian AI governance discussions.
- [China: Interim Measures for the Management of Generative AI Services](https://www.chinalawtranslate.com/en/generative-ai-interim/) - China's first dedicated generative AI regulation, in force since August 2023 and jointly issued by seven state authorities led by the Cyberspace Administration of China. Covers providers of text, image, audio, video, and code generation services to the public. English translation via China Law Translate.
- [Digital Personal Data Protection Act, 2023 (India)](https://www.meity.gov.in/content/digital-personal-data-protection-act-2023) - India's federal data protection law, governing the processing of digital personal data. The Digital Personal Data Protection Rules 2025, notified 13 November 2025, operationalize it with phased compliance deadlines.
- [OECD AI Principles](https://oecd.ai/en/ai-principles) - The baseline international principles adopted by 46 countries. Foundational vocabulary for cross-border deployments.

---

## International Standards and Standards Bodies

- [ISO/IEC 23053](https://www.iso.org/standard/74438.html) - Framework for AI systems using machine learning. Defines key concepts, components, and lifecycle stages.
- [ISO/IEC 23894](https://www.iso.org/standard/77304.html) - Guidance on AI risk management. Companion to ISO 42001 for operationalising risk processes.
- [ISO/IEC 42001:2023](https://www.iso.org/standard/81230.html) - The international standard for AI management systems. Specifies requirements for establishing, implementing, maintaining, and continually improving an AI management system within an organization. Certifiable, and certification programs are now live.
- [ISO/IEC 42005:2025](https://www.iso.org/standard/42005) - Guidance on AI system impact assessment: how and when to assess the effects of an AI system on individuals and society, and how to document it. Annex A maps it onto ISO/IEC 42001.
- [ISO/IEC TR 24028](https://www.iso.org/standard/77608.html) - Overview of trustworthiness in AI. Covers accuracy, robustness, reliability, safety, security, and privacy.
- [IETF SCITT WG](https://datatracker.ietf.org/wg/scitt/about/) - Supply Chain Integrity, Transparency and Trust. The relevant working group for cryptographic audit chains for software supply chains and increasingly for AI provenance.
- [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) - Adjacent standard for cryptographically signed attestations.
- [ETSI TC ESI](https://www.etsi.org/committee/esi) - European Telecommunications Standards Institute, Electronic Signatures and Infrastructure. Where the RFC 3161 trusted timestamping conversation lives.
- [OASIS](https://www.oasis-open.org/) - Standards body where several AI-trust-related profiles are being drafted.
- [IEEE 2089-2021](https://standards.ieee.org/ieee/2089/7633/) - Standard for age-appropriate digital services. Relevant to AI systems that interact with or make decisions about minors.

---

## Industry Standards, Threat Models, and Guidance

- [CISA Guidelines for Secure AI Development](https://www.cisa.gov/topics/artificial-intelligence) - US Cybersecurity and Infrastructure Security Agency guidance on secure AI system development and deployment.
- [Cloud Security Alliance AI Safety Initiative](https://cloudsecurityalliance.org/research/topics/artificial-intelligence/) - Enterprise guidance on AI security, governance, and trust. Includes the AI Controls Matrix and assessment tools.
- [CSA MAESTRO](https://github.com/CloudSecurityAlliance/MAESTRO) - Seven-layer threat modeling framework for agentic AI from the Cloud Security Alliance, separating traditional per-layer threats from agentic ones arising from autonomy and non-determinism.
- [ENISA AI Threat Landscape](https://www.enisa.europa.eu/publications/artificial-intelligence-cybersecurity-challenges) - EU Agency for Cybersecurity reports on AI-specific threats, risk assessments, and guidelines for EU organizations.
- [MITRE ATLAS](https://atlas.mitre.org/) - Adversarial Threat Landscape for AI Systems. Tactics, techniques, and real-world case studies for attacks against ML and AI systems, modeled on ATT&CK.
- [MITRE ATT&CK for AI](https://attack.mitre.org/) - Machine learning attack techniques mapped to the ATT&CK framework for integration with existing threat intelligence programs.
- [OWASP Agentic AI: Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/) - Threat-model reference for autonomous agents from the OWASP Agentic Security Initiative, with a taxonomy spanning agent design, memory, planning and autonomy, tool use, and deployment.
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) - The ten most critical security risks for LLM-powered applications: prompt injection, insecure output handling, training data poisoning, model denial of service, and supply chain vulnerabilities.

---

## Research Papers

- [Concrete Problems in AI Safety (Amodei et al., 2016)](https://arxiv.org/abs/1606.06565) - The canonical pre-LLM safety paper. Still foundational vocabulary for the field.
- [On the Opportunities and Risks of Foundation Models (Bommasani et al., 2021)](https://arxiv.org/abs/2108.07258) - Stanford CRFM's comprehensive survey of risks from large pre-trained models. The paper that put foundation model governance on the enterprise agenda.
- [Constitutional AI: Harmlessness from AI Feedback (Bai et al., 2022)](https://arxiv.org/abs/2212.08073) - Anthropic's paper on guiding model behavior via a written constitution.
- [Risks from Learned Optimization in Advanced Machine Learning Systems (Hubinger et al., 2019)](https://arxiv.org/abs/1906.01820) - Introduces mesa-optimization and deceptive alignment. Foundational for anyone designing oversight mechanisms for learned systems.
- [Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training (Hubinger et al., 2024)](https://arxiv.org/abs/2401.05566) - On models that behave differently in training versus deployment. Directly relevant to deployment-time audit requirements.
- [Alignment Faking in Large Language Models (Greenblatt et al., 2024)](https://arxiv.org/abs/2412.14093) - Anthropic paper demonstrating that models can strategically comply during training while pursuing different goals at deployment. A significant input to the case for tamper-evident audit records.
- [Datasheets for Datasets (Gebru et al., 2018)](https://arxiv.org/abs/1803.09010) - Established the expectation for dataset documentation: provenance, composition, collection process, and recommended uses. Directly cited in EU AI Act Article 10 training data requirements.
- [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993) - Established the model card format. Now a de facto standard for responsible AI disclosure and referenced in several national AI governance frameworks.

---

## Open-Source Governance Toolkits and Primitives

- [AffixIO](https://github.com/AffixIO/SDK) - Agentic Pay Kit (npm `affixio`) with host-side signed yes/no ACTION attestation before agent pay and tool gates (x402BeforePay / Agentic Pay / KYA; not person KYC). ([npm](https://www.npmjs.com/package/affixio)) ([docs](https://www.affix-io.com/agent-trust/))
- [Agentlas OS](https://github.com/agentlas-ai/Agentlas-OS) - Apache-2.0 local-first Agent Operation Environment (AOE) with explicit permission scopes, least-privilege tool access, verification gates, and local execution receipts across Claude Code, Codex, Gemini CLI, Cursor, and local models.
- [AgentLock](https://github.com/webpro255/agentlock) - Pre-action authorization for AI agent tool calls. Deny-by-default gate with five decision types, session-level behavioral scoring, Ed25519 signed receipts, and hash-chained audit. Published adversarial benchmark with regression data.
- [Agent Passport System](https://github.com/aeoess/agent-passport-system) - Apache-2.0 protocol for agent identity, scoped delegation, runtime enforcement, and signed action receipts. Includes TypeScript and Python SDKs and an MCP server with 150 governance tools.
- [attenu-guard](https://github.com/attenu-io/attenu-guard) - In-process permission enforcement across AI-agent delegation chains: a sub-agent gets a strict subset of its parent's authority, denials happen before the tool body runs, and the audit ledger verifies offline. Python + TypeScript, 17 framework adapters. Apache-2.0; `pip install attenu-guard`.
- [Busabase](https://github.com/busabase/busabase) - MIT-licensed database and workspace for AI agents with a governed mutation boundary: scoped MCP and OpenAPI credentials can propose ChangeRequests but cannot force them into canonical data, while exact diffs, submitter attribution, comments, reviews, commits, and history remain inspectable. Self-hostable and local-first.
- [Chock](https://github.com/open-coder-ai/chock) - Governance-as-code for AI coding agents. Policies committed to the repo compile to pre-tool-use hooks (Claude Code, Cursor), git hooks, and a CI gate, so rules travel with every clone and fork. Per-agent coverage report marks a policy "enforced" only where an installed mechanism is witnessed, and "advisory" where it is prose. Apache-2.0; `pip install chock`.
- [Clay Seal Identity](https://github.com/clayseal/clayseal-identity) - Short-lived attested agent credentials (SPIFFE JWT/X.509, proof-of-possession, Biscuit capability tokens) with offline verification and optional MCP FastMCP tool authorization. MIT; `pip install clayseal-identity`.
- [CorvinOS](https://github.com/CorvinLabs/CorvinOS) - Self-hosted agentic OS with hash-chained tamper-evident audit log (GDPR Art. 30/32), per-user consent gate (deny-by-default), EU AI Act Art. 50 bot-disclosure, and GDPR Art. 17 erasure orchestrator — all as load-bearing architecture constraints. `pip install corvinos`. Apache-2.0.
- [decision-os-min](https://github.com/Aliipou/decision-os-min) - Python execution-governance runtime: Ed25519-signed action-bound decisions, one-time capability spend, a PEP that refuses unsigned effects, optional OPA/Cedar as replaceable PDPs, hash-chained audit. PolyForm-Noncommercial-1.0.0.
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Input and output validation framework for LLM responses. Define schemas, validators, and automated correction actions that enforce structure and safety constraints at inference time.
- [Helio](https://github.com/gethelio/helio) - Apache-2.0 governance proxy for MCP agents. Every tool call passes a policy engine, evidence grounding checks, approval workflows, and cross-tool spend budgets that deplete one shared pot across several tools and servers, then lands in an audit trail. Runs in front of unmodified agents and MCP servers; the runtime and dashboard ship in one package (`npx @gethelio/proxy init`). See also [Claude Code and MCP Governance](#claude-code-and-mcp-governance).
- [Hexis](https://github.com/Bevel-Software/Hexis) - Git-backed platform for skills, tools, and context for AI agents. Role-based access, reviewed changes, and an encrypted secrets vault govern what each person and their MCP client can use.
- [HOL Guard](https://hol.org/guard) - Open-source local-first runtime governance layer for AI agents that evaluates supported tool actions before execution, applies policy checks for prompt injection, secret exposure, unsafe commands, package and MCP risks, and records approval or block receipts.
- [Humanbound](https://github.com/humanbound/humanbound) - Open source testing framework that scores agent behavior against a security policy, targeting the risks in the OWASP Top 10 for Agentic Applications (prompt injection and goal hijacking listed first), and turns failed tests into guardrail rules.
- [Kakunin](https://github.com/nqzai/kakunin-core) - Compliance and identity infrastructure for AI agents. Issues X.509 certificates via AWS KMS, enforces per-agent action scope before execution, scores behavior against a rolling baseline, and auto-revokes credentials when risk crosses a threshold, with a tamper-evident audit trail for MiCA and the EU AI Act. Platform AGPL-3.0; SDKs Apache-2.0.
- [Kepil](https://github.com/oleg-vdv/kepil) - AGPL-3.0 gate plus journal for agent actions. Every action is checked against a machine-readable per-job mandate before a model is called, fail-closed, and lands in an append-only hash-chained journal verified by a separate implementation in another language. Irreversible actions stop and wait for a person. Ships an MCP server exposing seven tools for creating orders, running steps, asking whether an action is permitted, and verifying the journal — confirming an irreversible action is deliberately not among them, enforced by a test. Python standard library only, no dependencies, state in plain JSON files.
- [KYDE Gateway](https://github.com/kydehq/gateway) - Drop-in OpenAI-compatible proxy for OpenAI, Anthropic, Gemini, Copilot, local models, and others that records every agent action into an Ed25519-signed, hash-chained ledger and enforces DLP and per-MCP-tool policies before requests reach the upstream. Source-available BSL-1.1.
- [LiteLLM](https://github.com/BerriAI/litellm) - Proxy layer for LLM API calls with per-key budgets, rate limiting, spend tracking, and model routing across all major providers.
- [LlamaFirewall](https://github.com/meta-llama/PurpleLlama/tree/main/LlamaFirewall) - Meta's open-source guardrail framework for agents. Composes PromptGuard 2 jailbreak detection, chain-of-thought alignment checks, and CodeShield static analysis behind a single policy engine.
- [MAREF](https://github.com/maref-org/maref) - Open-source agent governance operating system with TLA+ formal verification, 10-state Gray Code governance state machine, per-agent Ed25519 identity, circuit breaker with HALT absorbing state, and LoRA/ontology dual drift detection. Covers 10/10 OWASP Agentic Top 10 risks. Apache 2.0.
- [MARGINAL](https://github.com/SignalLayerLabs/Marginal) - Apache-2.0 local-first runtime governor for AI coding agents. Observes repeated tool work in Shadow Mode and gates narrow enforcement on verified evidence, explicit consent, and integrity checks.
- [MREA](https://github.com/JairValle/mrea-framework) - Multi-role agent framework separating Architect, Auditor, and Implementer roles, with risk classification and a human approval gate before implementation. MIT licensed.
- [Microsoft Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) - Runtime security for AI agents across LangChain, CrewAI, AutoGen, OpenAI Agents, Semantic Kernel, and 15+ frameworks. Covers all 10 OWASP Agentic Top 10 risks with policy evaluation under 0.1ms.
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - NVIDIA's toolkit for adding programmable guardrails to LLM-based systems via Colang configuration language.
- [OpenFirma](https://github.com/Firma-AI/openfirma) - Call-level enforcement boundary for autonomous AI agents. Intercepts every outbound call (HTTPS, syscalls, browser automation) and evaluates Cedar policies locally before execution. Fully deterministic, no SDK integration required, agent never holds credentials.
- [plumb-line](https://github.com/slopstopper/plumb-line) - Apache-2.0 provenance primitive (JS/Python) that propagates mock or low-confidence taint through derived values, plus five Claude Code skills that audit a repository for unverified claims and source-truth gaps.
- [PolicyStrata](https://github.com/raintree-technology/policystrata) - Local-first policy regression testing and runtime decision gates for LLM data-agent stacks, with CI checks across model-visible tools, semantic validation, SQL compilation, database controls, and result release. MIT licensed.
- [Presidio](https://github.com/microsoft/presidio) - Microsoft's PII detection and anonymisation SDK. Identifies and redacts sensitive data in text before it reaches an LLM or audit log.
- [SteerPlane](https://github.com/vijaym2k6/SteerPlane) - Open-source runtime control plane for AI agents: deterministic loop detection, per-session cost ceilings with mid-stream termination, and a hierarchical deny/allow/rate-limit policy engine, enforced via a Python decorator or an OpenAI-compatible gateway proxy. Framework integrations for LangChain, CrewAI, AutoGen, and the OpenAI Agents SDK. No model in the enforcement path. MIT licensed; `pip install steerplane` / `npm install steerplane`.
- [systemprompt-template](https://github.com/systempromptio/systemprompt-template) - Self-hosted governance layer for Claude Code and MCP agents. Authentication, authorization, audit trail, cost controls, and policy enforcement in a single compiled Rust binary. Source-available BSL-1.1.
- [ThumbGate](https://github.com/IgorGanapolsky/ThumbGate) - Local-first PreToolUse enforcement engine for AI coding agents. Runs in the agent's hook system to hard-block secret exfiltration, destructive deletes, and supply-chain attacks before the tool call executes. Turns thumbs-down feedback into auto-promoted prevention rules. Works with Claude Code, Cursor, Codex, Gemini CLI, Amp, Cline, and OpenCode. MIT licensed, npm installable.
- [YYLO](https://github.com/yylo-dev/yylo) - Command-line orchestrator for coding agents with typed task, validation, merge, and release-readiness boundaries. Task start freezes the protected target SHA and creates a dedicated branch/worktree per task; the merge queue owns risk-based review (low risk has no semantic reviewer, high risk two sequential reviewers on one frozen candidate, stopping as REVIEW_FINDINGS_EXHAUSTED rather than an unbounded review loop). Workflow runs retain declared receipt hashes and terminal manifests as receipt-backed repository changes. Orchestrates Pi and Codex subagents. MIT licensed, npm installable as @yylo/cli.
- [Nexuscone](https://github.com/aperintel/nexuscone) - Tamper-evident audit ledger with SHA-256 hash chain, optional Ed25519 signing, optional Bitcoin anchoring via OpenTimestamps. Apache 2.0.
- [in-toto](https://in-toto.io/) - Framework for protecting software supply chain integrity. Adjacent to AI provenance work.
- [Giskard](https://github.com/Giskard-AI/giskard) - Open-source testing framework for ML models and LLM applications. Covers vulnerability scanning, bias detection, and robustness testing in one tool.
- [OpenTimestamps](https://opentimestamps.org/) - Free Bitcoin-anchored timestamping. The substrate for cryptographic audit anchoring.

---

## Free Governance Tools

Interactive tools that answer common governance questions without a signup. Each is also callable by AI agents over HTTP (`POST /api/v1/tools/{tool}/run` with an `X-Agent-Id` header), so the same check an engineer runs in a browser runs in CI or inside a coding agent.

- [AI ROI Calculator](https://systemprompt.io/tools/ai-roi-calculator) - Models the cost and payback of an AI rollout with explicit assumptions, for the business case behind a governance budget.
- [CLAUDE.md Scorer](https://systemprompt.io/tools/claude-md-scorer) - Scores a CLAUDE.md against a structured rubric and reports what is missing. Usable in a hook to fail CI when agent instructions degrade.
- [EU AI Act Risk Classifier](https://systemprompt.io/tools/eu-ai-act-risk-classifier) - Walks the Annex III decision tree and returns your system's risk category (prohibited, high-risk, limited, minimal) with the specific articles that apply. Deterministic, not legal advice.
- [GitHub Actions Permissions Generator](https://systemprompt.io/tools/github-actions-permissions) - Produces a least-privilege `permissions:` block for a workflow instead of the default write-all token.
- [llms.txt Generator and Validator](https://systemprompt.io/tools/llms-txt-generator) - Generates or lints an llms.txt so AI crawlers and agents get a machine-readable index of your site.
- [systemprompt.io Reports MCP Server](https://systemprompt.io/tools/eu-ai-act-compliance-report) - Paid remote MCP server (`https://systemprompt.io/api/v1/mcp/systemprompt-reports/mcp`) returning decision-ready EU AI Act compliance reports (Annex III classification, article-by-article obligation gaps, Annex IV checklist, remediation plan). Paid, per call; discovery and the usage guide are free.

---

## Commercial and Enterprise Governance Platforms

- [Credo AI](https://www.credo.ai/) - Comprehensive AI governance platform covering risk assessment, compliance mapping (EU AI Act, NIST AI RMF, ISO 42001), model cards, and ongoing monitoring across the AI lifecycle. Mature regulator-facing posture.
- [AgenticRail](https://agenticrail.nz/product/) - Hosted pre-execution gate for AI agent step order. The caller declares the intended sequence in advance, any step presented out of order is refused before it executes, and the sequence is sealed on completion. Every decision, permit and refusal alike, is written to an Ed25519-signed, hash-chained receipt that verifies offline against published keys. Closed source, free tier with a public demo key.
- [Certiv](https://certiv.ai/) - Endpoint-native, pre-execution security and governance layer for AI agents. An endpoint agent inspects agent actions and tool calls on the device and enforces policy before they execute, with an audit trail of allowed and blocked actions.
- [CoreBase](https://corebasehq.com/) - Governance layer for agents that read and write to live business systems; databases, REST and GraphQL APIs, MCP servers, and 50+ SaaS apps. Enforces rules on every tool call, holds risky actions for human sign-off, and logs executed and blocked calls alike. Per-tenant Postgres row-level security, embeddable widget, and an API.
- [HiddenLayer](https://hiddenlayer.com/) - AI detection and response platform. Monitors AI models for adversarial attacks, data extraction attempts, and policy violations.
- [Holistic AI](https://www.holisticai.com/) - EU AI Act focused governance platform.
- [Fiddler AI](https://www.fiddler.ai/) - AI observability and audit platform.
- [Trustible](https://trustible.ai/) - AI governance and risk management.
- [Modulos](https://www.modulos.ai/) - One of the first platforms with ISO 42001 product conformity.
- [Saidot](https://www.saidot.com/) - EU AI Act focused governance platform, Helsinki-based.
- [Arthur AI](https://www.arthur.ai/) - Enterprise ML monitoring, explainability, and fairness. Strong financial-services and insurance client base.
- [Gram](https://github.com/speakeasy-api/gram) - Open-source AI control plane for connecting agents to MCPs with role-scoped access, policy enforcement, threat detection, and observable access events.
- [Lumenova AI](https://www.lumenova.ai/) - AI lifecycle governance: risk assessment, explainability monitoring, and compliance reporting focused on model transparency and regulatory evidence.
- [Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/what-is-microsoft-entra-agent-id) - Directory identities for AI agents in Microsoft Entra, with lifecycle management, access reviews, entitlement management, and conditional access applied to agents as to users.
- [OneTrust AI Governance](https://www.onetrust.com/solutions/ai-governance/) - Inventory, risk assessment, and compliance controls for AI systems embedded in broader data governance and privacy programs.
- [Patronus AI](https://www.patronus.ai/) - Automated evaluation and monitoring for LLMs in production. Detects hallucinations, toxicity, PII leakage, and custom policy violations.
- [Penholder](https://penholder.ai) - Preventive human-approval write-gate for AI agents. Intercepts an agent's write to a system of record (Postgres or a governed spreadsheet) and holds it as a durable PENDING proposal that commits only after a human approves — fail-closed on conflict, with an append-only, hash-chained, tamper-evident provenance log. Framework-agnostic and enforced at the write boundary; public network MCP endpoint at api.penholder.ai/mcp.
- [Proofpane](https://proofpane.com) - Runtime governance gateway for AI coding agents (Claude Code, Cursor, Codex) and automation platforms. Enforces policy allow/deny/human-in-the-loop and DLP redaction in the execution path, and writes a hash-chained audit that exports as an offline-verifiable, Ed25519-signed evidence pack mapped to NIST AI RMF, ISO 42001, EU AI Act, GDPR, and SOC 2.
- [Protect AI](https://protectai.com/) - MLSecOps platform covering model scanning, supply chain security, and runtime protection for AI and ML systems.
- [systemprompt.io](https://systemprompt.io) - Self-hosted AI governance infrastructure: a single compiled Rust binary on your own systems that governs, logs, and cost-controls every AI interaction across every provider and client (Claude, Codex, Gemini, or your own agents). Authentication, authorization, audit trail, policy enforcement, and a provider gateway behind one /v1 endpoint. Air-gap capable. Source-available BSL-1.1 via [systemprompt-template](https://github.com/systempromptio/systemprompt-template).

---

## Claude Code and MCP Governance

- [agent-approval-gate](https://github.com/Prime-agentai/agent-approval-gate) - PreToolUse hook enforcing spend, account-creation, and fund-movement gates for autonomous agents. Blocked calls become queued approval tickets; includes an installer and a probe-based verifier for both block and allow paths.
- [Agentic Control Plane](https://github.com/agentic-control-plane/acp-install) - Policy enforcement on every tool call across Claude Code, Codex, Cursor, and MCP clients from one install. Allow, ask, or deny before execution; per-agent and per-workspace spend caps; PII redaction; and an audit trail that resolves each call back to the human who started the run. MIT open core ([GatewayStack](https://github.com/agentic-control-plane/GatewayStack)); runs hosted or fully local.
- [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) - Reference implementations and patterns from Anthropic including agent architectures, tool use, and safety patterns.
- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) - The canonical Claude Code community list covering tooling, hooks, slash-commands, agent skills, and workflows.
- [awesome-claude-code-security](https://github.com/efij/awesome-claude-code-security) - Curated list focused on Claude Code hardening: MCP server security, secrets scanning, prompt injection detection, and red-teaming frameworks.
- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code) - Anthropic's documentation on the permissions model, CLAUDE.md configuration, MCP server setup, and hook system.
- [eu-ai-act-compliance-mcp](https://github.com/CSOAI-ORG/eu-ai-act-compliance-mcp) - MCP server for EU AI Act compliance checking and risk classification of AI systems.
- [Helio](https://github.com/gethelio/helio) - Proxy that governs tool calls from any MCP client. Declarative YAML policies match on tool name, annotations, input parameters, and cumulative state; irreversible actions route to approval workflows; cross-tool spend caps and rate limits apply at the gate; and every call lands in an audit trail with a bundled dashboard. Apache-2.0.
- [mcp-airlock](https://github.com/Shalimov04/mcp-airlock) - Governance proxy in front of an MCP server. Each tool gets a risk tier per environment: read-only, forced dry run, dry run then human confirmation over a signed approve link, or straight through. The confirmation token is HMAC-signed and self-contained, so the proxy keeps no approval store, any replica can finish a confirmation, and each token is spent exactly once; a replay, a tampered argument or a bad signature is refused with a named rule. Blast-radius limits cap how many objects one call and one principal may touch per hour, every call writes a JSONL audit record before and after, and secrets are redacted on the way out. Python, MIT.
- [MCP Specification](https://modelcontextprotocol.io/specification/) - The Model Context Protocol specification, Anthropic's open standard for connecting AI agents to tools and data sources. The de facto standard for agentic tool use; understanding it is prerequisite to governing and auditing it.
- [Mneme](https://github.com/MnemeHQ/mneme) - Compiles a repository's architectural decision records into deterministic checks that run on a Claude Code PreToolUse hook, blocking an agent's proposed edit before it is written. Also integrates with Codex CLI and the Claude Agent SDK. MIT.
- [Provenrail Guard](https://github.com/pofky/provenrail/tree/main/plugins/provenrail-guard) - Claude Code plugin that gates tool calls on a PreToolUse hook. Denies destructive commands (`rm -rf`, `terraform destroy`, `git push --force`, `DROP TABLE`, `chmod 777`) and leaked credentials before they run, escalates lower-confidence cases (`.env` access, deploys, migrations) to a human prompt recorded as oversight, and signs every allow, deny and approval into a hash-chained record that `pr verify` or a browser verifier can recompute offline. Policy is declared in a repo-local `.provenrail.json`. MIT.
- [ProxyKey](https://github.com/neostorm112-boop/proxykey-mcp) - Credential proxy with a remote MCP server for Claude Code, Cursor and other MCP clients. Real API keys stay AES-256-GCM encrypted on the proxy; the agent issues, rotates and revokes virtual passes with per-pass IP binding, rate limits and request logs, and the toolset has no operation that returns a real key. Free hosted service; the encryption module is published at [proxykey-crypto](https://github.com/neostorm112-boop/proxykey-crypto).
- [Snyk agent-scan](https://github.com/snyk/agent-scan) - Scanner for MCP servers, agent configurations, and agent skills; detects tool poisoning, tool shadowing, and prompt injection in tool descriptions, and can proxy MCP traffic. Formerly Invariant Labs MCP-Scan.
- [systemprompt-core](https://github.com/systempromptio/systemprompt-core) - The MCP governance runtime. 30-crate Rust workspace handling authentication, authorization, rate limiting, and logging for MCP server interactions. Published on crates.io under `systemprompt-*`.
- [ThumbGate](https://github.com/IgorGanapolsky/ThumbGate) - PreToolUse hook-based enforcement layer that gates Claude Code's tool calls locally before execution. Hard-blocks secret exfiltration, destructive deletes, and supply-chain attacks. Self-improving rules from captured thumbs-down feedback.
- [ToolHive](https://github.com/stacklok/toolhive) - Runs MCP servers in isolated containers with declared permissions, secrets management, and a signed server registry. Apache-2.0, with Kubernetes and CLI deployment modes.
- [Verax](https://github.com/verax-ai/verax) - MCP server between an agent and its tools: each call passes a policy gate and leaves a signed decision record before it runs, an effect row is reconciled against it after, approval waits for an operator on the same machine, and the ledger stays there. Apache-2.0.

---

## Policy Engines and Authorization

- [Allowly](https://allowly.ai/) - Hosted policy decisions and signed receipts for AI-agent actions; the caller enforces, and receipts verify offline with workspace Ed25519 keys using open-source Python (`allowly-receipt-format`) and TypeScript (`@allowly/verifier`) verifiers, with a [CC BY 4.0 specification and interoperability map](https://github.com/Allowly-AI/allowly-receipt-format/blob/main/INTEROP.md).
- [amu-governance](https://github.com/sangaraju1988/amu-governance) - Lineage-gated access control library for AI-agent shared memory. Gates retrieval on the full column-level derivation of a cached result, not just content tags, to block cross-department leakage through legitimately-computed results. MIT license, `pip install amu-governance`. Author-submitted; accompanying paper published in IEEE Access (2026).
- [AWS Verified Permissions](https://aws.amazon.com/verified-permissions/) - Managed Cedar policy service on AWS. Centralised policy storage with sub-millisecond evaluation latency for agent action authorization.
- [Casbin](https://www.casbin.org/) - Multi-model access control library supporting ACL, RBAC with hierarchy and domain, ABAC, and RESTful models in 10+ languages, including Go, Rust, Python, Java, and Node.js.
- [Cedar](https://www.cedarpolicy.com/) - AWS-designed policy language and engine for fine-grained authorization. Formally verified semantics, expressive human-readable syntax, and high throughput for per-request agent permission decisions.
- [GOPAL](https://github.com/Principled-Evolution/gopal) - Library of OPA/Rego policies encoding AI-governance regulations as executable allow/deny checks, covering the EU AI Act, NIST AI RMF, UK GDPR Arts 22A-22D, aviation (ICAO/FAA/EASA), FERPA, and financial-services rules. Loads into an OPA server for request-path queries or runs under `opa eval`. Apache-2.0.
- [HashiCorp Sentinel](https://www.hashicorp.com/sentinel) - Policy-as-code framework for Terraform, Vault, Consul, and Nomad. Useful for governing infrastructure provisioned by AI agents.
- [Open Policy Agent](https://github.com/open-policy-agent/opa) - CNCF-graduated general-purpose policy engine using the Rego language. Decouples policy from application logic; increasingly used for agent tool authorization.
- [OPA Rego Playground](https://play.openpolicyagent.org/) - Browser-based environment for writing and testing OPA/Rego policies without local setup.
- [Ory Keto](https://github.com/ory/keto) - Open-source permission server implementing Google Zanzibar's relation-based access control model for fine-grained agent tool permissions.

---

## Audit, Observability, and Cost Control

- [aGiTrack](https://github.com/core-aix/agitrack) - Runtime audit trail for terminal coding agents. Wraps Claude Code, Codex, or OpenCode and commits each agent turn to git, recording the prompt, backend, model, and that turn's input, output, cache-read, and cache-write token counts in the commit message, so the trace lives in version control rather than a separate log store. Sub-agent tokens are counted separately. Apache-2.0.
- [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Open-source LLM and agent tracing, evaluation, and dataset tooling built on OpenTelemetry. Self-hostable, with span-level replay of agent runs and strong support for retrieval-augmented generation debugging.
- [Arize AI](https://arize.com/) - ML observability and LLM tracing platform (commercial). Strong tooling for production model debugging and performance monitoring.
- [Bifrost](https://github.com/maximhq/bifrost) - Go-native, OpenAI-compatible AI gateway with multi-provider routing, automatic failover, load balancing, guardrails, MCP gateway support, and built-in logs, metrics, and tracing.
- [CausalLayer MCP](https://github.com/smq9sn5jck-coder/causallayer-mcp) - Deterministic AI liability attribution engine exposed as a remote MCP server. Given a structured incident, returns a CausalCertificateV1: a signed, hash-chained, Bitcoin-anchored receipt allocating fault between AI vendor, deployer, and end-user. Four-factor scoring, Shapley-inspired multi-agent attribution, and jurisdiction-aware regulatory mapping (EU AI Act, NIST AI RMF, AU AI Ethics).
- [ClawBench](https://github.com/TIGER-AI-Lab/ClawBench) - Open-source live-web benchmark for evaluating browser and computer-use agents on 283 tasks across 163 websites, with request interception and execution evidence useful for governance audits.
- [Clay Seal Receipts](https://github.com/clayseal/clayseal-receipts) - Verifiable execution receipts for AI agent actions: policy wrap with shadow mode, signed offline-verifiable receipts so audit trails do not depend on the vendor being online. MIT.
- [Etch](https://etch.systems) - Signed audit chain for AI agent decisions across MCP client tools. Events carry a hybrid Ed25519 + FIPS 205 SLH-DSA-SHA2-128f envelope and Merkle-chain into epochs anchored to both Sigstore Rekor and Bitcoin OpenTimestamps. Offline reference verifier ships as `world-model-mcp` on PyPI; MIT verifier, BSL 1.1 hosted.
- [Evidently AI](https://github.com/evidentlyai/evidently) - Open-source ML and LLM monitoring. Detects data and model drift, generates monitoring reports, and evaluates LLM output quality.
- [Helicone](https://github.com/Helicone/helicone) - Open-source LLM observability proxy. Request logging, cost tracking, caching, and rate limiting via a single proxy endpoint. Self-hostable.
- [HELM AI Kernel](https://github.com/Mindburn-Labs/helm-ai-kernel) - Post-decision tamper-evident audit for MCP tool calls. Every ALLOW/DENY/ESCALATE decision produces a cryptographically signed receipt, bundled into an offline-verifiable EvidencePack, so you can prove what an agent executed under which policy independently of mutable logs. Targets EU AI Act Article 12 and SOC 2 evidence needs.
- [LangFuse](https://langfuse.com/) - Open-source LLM observability. Full trace capture with spans, generations, scores, and costs, plus prompt management. Self-hostable with integrations for LangChain, LlamaIndex, OpenAI, and Anthropic SDKs.
- [Nobulex](https://github.com/arian-gogani/nobulex) - Cryptographic receipt layer for AI agents. Ed25519-signed, JCS-canonical bilateral receipts (pre/post execution), hash-chained, independently verifiable. EU AI Act Article 12 compliance. `pip install nobulex` / `npm install @nobulex/core`.
- [OpenLLMetry](https://github.com/traceloop/openllmetry) - OpenTelemetry-based instrumentation SDK for LLM applications. Traces LLM calls with standard OTel spans and integrates with existing observability stacks.
- [OpenTelemetry](https://opentelemetry.io/) - CNCF standard for distributed tracing, metrics, and logs. The vendor-neutral substrate for building agent observability pipelines.
- [PostHog LLM Observability](https://posthog.com/docs/ai-engineering/observability) - LLM observability inside the broader PostHog product analytics platform.
- [Portkey](https://portkey.ai/) - AI gateway with unified API for 250+ LLMs, request tracing, semantic caching, load balancing, and budget controls.
- [Provena](https://github.com/rajfirke/provena) - Governs context inputs rather than agent actions: SHA-256 hash-chained audit trail, provenance validation (required-field presence), and freshness checking (staleness thresholds plus temporal-language detection) for RAG, tool, memory, and MCP context sources. Policy engine (log/warn/block), multi-agent trail aggregation, and EU AI Act Art. 10/12/13/14 compliance reports. Adapters for LangChain, LlamaIndex, CrewAI, AutoGen, OpenAI Agents SDK, and Google ADK. Zero core dependencies. `pip install provena`. Apache-2.0.
- [Provenrail](https://github.com/pofky/provenrail) - Hash-chained, Ed25519-signed records of agent tool calls, model calls, and guardrail decisions, written to an off-box sink and verifiable without trusting the agent or the vendor. Two independent verifier implementations (a Python CLI and an in-browser JavaScript verifier) are held in lockstep by a frozen conformance-vector suite; anchors carry RFC 3161 trusted timestamps and transparency-log inclusion proofs with witness cosignatures, and both verifiers also validate OpenTimestamps Bitcoin proofs. Records stay on your own infrastructure. MIT client, SDK, verifier and spec; AGPL-3.0 server. `pip install provenrail` / `npm install provenrail`.
- [Traccia](https://github.com/traccia-ai/traccia-py) - OpenTelemetry-native observability, governance, and compliance for AI agents and LLM applications. Integrates with OpenAI Agents SDK, CrewAI, Langchain, Claude Code, and more.
- [Tuning Engines](https://www.tuningengines.com/) - AI control and evidence plane for model, MCP, skill, and agent traffic. Provides governed routing, policy decisions, approval workflows, cost analytics, trace ingestion, and runtime state references.
- [Weights and Biases Weave](https://wandb.ai/site/weave) - Tracing and evaluation for LLM applications with strong integrations for LangChain, LlamaIndex, OpenAI, and Anthropic, and model lineage tracking.
- [WhyLabs AI Observatory](https://whylabs.ai/) - AI observability platform built on whylogs, an open-source data logging library. Monitors LLM applications for drift, data quality issues, and policy violations in production.
- [YYLO Benchmark](https://github.com/yylo-dev/yylo-benchmark) - Evaluation and evidence layer for coding-agent runs, providing two deliberately separate evaluation lanes: isolated attempts execute in private fresh-repository attempt workspaces, while explicitly authorized production-touching workflows execute through a reviewed boundary. Evidence retains the initial workspace receipt plus post-execution repository manifest hashes linked through terminal, evidence, and state; evaluator profile, prompt, rubric, output, generation, and provenance hashes; and evidence/evaluation IDs behind every aggregate. Candidate and judge costs remain separate evidence. Evaluator profiles support deterministic commands and configurable LLM judges. MIT, npm installable as @yylo/benchmark.

---

## Security, Red-Teaming, and Threat Models

- [AgentDojo](https://github.com/ethz-spylab/agentdojo) - Benchmark from ETH Zurich's SPY Lab measuring both utility and security of tool-using agents under indirect prompt injection, with pluggable attacks and defenses.
- [AI Incident Database](https://incidentdatabase.ai/) - Searchable database of 700+ documented AI system failures and harms in deployment. Essential for building realistic threat models and risk assessments.
- [awesome-ai-agent-attacks](https://github.com/webpro255/awesome-ai-agent-attacks) - Curated timeline of 160+ documented AI agent security incidents, breaches, and vulnerabilities (2024-2026). Every entry dated, sourced, and categorized by attack pattern.
- [Darkmoon](https://github.com/ASCIT31/Dark-Moon) - GPL-3.0 autonomous AI penetration testing platform. Agentic reasoning drives real exploit execution across web, API, cloud, identity, CI/CD, IaC, Active Directory, and Kubernetes, producing proof-based findings; a privacy gateway keeps real hosts, addresses, and credentials out of the LLM context.
- [Garak](https://github.com/NVIDIA/garak) - NVIDIA's LLM vulnerability scanner. Probes deployed models for prompt injection, jailbreaks, data leakage, hallucination, and toxicity.
- [LLM Guard](https://github.com/protectai/llm-guard) - Security toolkit for LLM interactions with input and output scanners for prompt injection, PII, toxicity, and sensitive data. Archived by its maintainers in July 2026; listed as a still-usable reference implementation rather than a maintained dependency.
- [LlamaGuard](https://github.com/meta-llama/PurpleLlama/tree/main/Llama-Guard4) - Meta's open-source content-safety classification model (v4, latest) for classifying LLM inputs and outputs against safety policies. Designed to be used as an input-output safeguard in production LLM systems.
- [PromptBench](https://github.com/microsoftarchive/promptbench) - Microsoft's unified evaluation framework for adversarial robustness of LLMs. Tests models against adversarial prompts at character, word, sentence, and semantic levels. Archived; the benchmark corpus remains useful, the code is no longer maintained.
- [promptmap](https://github.com/utkusen/promptmap) - Automated prompt injection testing tool. Systematically tests LLM-integrated applications for injection vulnerabilities.
- [Promptfoo](https://github.com/promptfoo/promptfoo) - Open-source LLM testing and red-teaming. Runs automated evaluations against prompts, catches regressions, and surfaces security vulnerabilities before deployment. Configurable attack strategies and automated evaluation pipelines.
- [PyRIT](https://github.com/Azure/PyRIT) - Microsoft's Python Risk Identification Toolkit for automated red-teaming of generative AI systems including multi-turn and orchestrated agent attacks.
- [Skill Safe](https://skillsafe.online/) - Free pre-installation security review for agent skills and tool configurations, with traceable findings for prompt injection, exfiltration, unsafe actions, and permission risks.
- [Counterfit](https://github.com/Azure/counterfit) - Microsoft's command-line tool for security testing of AI systems. Implements adversarial ML attacks to assess robustness to evasion, poisoning, and extraction.
- [VERITAS Omega Agent Trust Lab](https://github.com/VrtxOmega/veritas-agent-trust-lab) - Open-source blind calibration lab for testing whether agent-assurance decisions survive forged results, parameter substitution, nonce replay, correlated evaluators, evidence deletion, and missing telemetry.

---

## Model and Data Governance

- [DVC](https://dvc.org/) - Git-like versioning for ML datasets and models. Reproducible pipelines, experiment tracking, and audit trail for training data and model artifacts.
- [Great Expectations](https://greatexpectations.io/) - Data quality validation framework. Define expectations for training and inference data and alert when data drifts outside governance bounds.
- [Hugging Face Model Cards](https://huggingface.co/docs/hub/model-cards) - Implementation guide and templates for model cards on the Hugging Face Hub.
- [MLflow Model Registry](https://mlflow.org/docs/latest/model-registry.html) - Centralised model store with versioning, stage transitions, and approval workflows.
- [Model Cards](https://modelcards.withgoogle.com/about) - Google's framework for documenting AI model characteristics, performance, and limitations. De-facto standard for transparent model disclosure.
- [Sigstore](https://www.sigstore.dev/) - Cryptographic signing infrastructure for software artifacts. Enables verification that a model came from a trusted build process. Increasingly used in AI model attestation.
- [SLSA](https://slsa.dev/) - Supply-chain Levels for Software Artifacts applied to ML models and training pipelines. Defines four assurance levels from basic to hermetic builds.

---

## Agentic Architecture Patterns

- [12-Factor Agents](https://github.com/humanlayer/12-factor-agents) - Adaptation of the 12-factor app methodology for LLM agents. Covers configuration, state management, logging, and disposability in agentic contexts.
- [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) - Anthropic's published guidance on safe agentic systems: minimal footprint, human-in-the-loop for high-stakes actions, and preference for reversible over irreversible actions.
- [awesome-agentic-patterns](https://github.com/nibzard/awesome-agentic-patterns) - Curated collection of production agent patterns including sandboxing, credential management, human-in-the-loop workflows, and multi-agent coordination.
- [Bounded Agents](https://github.com/xmuruaga/bounded-agents) - Reference implementation of the Agentic Principal Chain (APC), an external authorization architecture that attenuates delegated scope and budgets across multi-agent chains, evaluates tool actions against session history, and enforces composition restrictions outside the model. Includes the [paper](https://arxiv.org/abs/2608.15888).
- [HumanLayer](https://github.com/humanlayer/humanlayer) - SDK for building human-in-the-loop workflows for AI agents. Wraps tool calls with approval gates, audit trails, and escalation paths.
- [Least privilege as an import contract](https://github.com/chohan-sarmad-ali/delivery-case-studies/blob/main/05-least-privilege-as-an-import-contract.md) - Single-egress architecture for agent systems: all outbound calls originate from one package behind policy checks and mandatory human approval, an import-linter contract enforced in CI keeps it single, and a static AST gate closes the authorization gap the import contract cannot see. Includes the incident that motivated the layering and the limits of each layer.
- [Lilian Weng: LLM-Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/) - Comprehensive survey of agent architectures including planning, memory, tool use, and oversight mechanisms.
- [agentgateway](https://agentgateway.dev/) - Linux Foundation open-source proxy for MCP tool calls and agent-to-agent traffic. Includes an OPA policy engine, RBAC, and OTel emission. A governance control point for agentic tool use.
- [OpenTelemetry GenAI Semantic Conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - The emerging standard for emitting structured observability spans from AI and agent systems. Required reading for anyone building agentic audit infrastructure.
- [AgentBench](https://github.com/THUDM/AgentBench) - Open-source benchmark for evaluating LLM agents on real-world tasks. Useful for establishing a performance baseline before regulated deployment.
- [EU AI Office: General-Purpose AI Guidance](https://digital-strategy.ec.europa.eu/en/policies/ai-office) - The AI Office's developing guidance on general-purpose AI models, increasingly covering agentic capabilities and autonomous decision chains.

---

## Bias, Fairness, and Impact Assessment

- [Fairlearn](https://fairlearn.org/) - Microsoft's open-source toolkit for assessing and improving model fairness. Python API, mitigation algorithms, and a visual dashboard.
- [AI Fairness 360 (AIF360)](https://github.com/IBM/AIF360) - IBM Research's open-source library covering bias detection and mitigation from pre-processing through to post-processing.
- [What-If Tool](https://pair-code.github.io/what-if-tool/) - Google's visual interface for probing ML model behavior across demographic subgroups, without writing code.
- [Aequitas](https://github.com/dssg/aequitas) - Open-source bias and fairness audit toolkit from the University of Chicago Data Science for Social Good group.
- [Algorithmic Impact Assessment (AIA) Guidance](https://www.canada.ca/en/government/system/digital-government/digital-government-innovations/responsible-use-ai/algorithmic-impact-assessment.html) - Canada's published framework for assessing the impact of automated decision-making in public-sector contexts. Widely referenced in private-sector practice.
- [NYC Local Law 144 (Automated Employment Decision Tools)](https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page) - The first US law to mandate bias audits for AI in hiring. Sets a practical floor for what a bias audit must demonstrate.

---

## Government, Regulators, and Institutional Guidance

- [UK Information Commissioner's Office (ICO)](https://ico.org.uk/) - UK data protection regulator. The primary regulator most AI products in the UK encounter.
- [European Commission AI Office](https://digital-strategy.ec.europa.eu/en/policies/ai-office) - The EU AI Office, responsible for implementing the AI Act at EU level.
- [UK AI Safety Institute](https://www.aisi.gov.uk/) - UK government body responsible for evaluating safety of advanced AI models. Publishes evaluation methodologies and results.
- [US AI Safety Institute (NIST)](https://www.nist.gov/aisi) - The US AI Safety Institute, established within NIST.
- [Financial Conduct Authority (FCA)](https://www.fca.org.uk/publications/discussion-papers/dp2-22-ai-and-machine-learning) - UK financial-services regulator. Their AI/ML discussion paper and Consumer Duty guidance are the primary documents for fintech AI governance.
- [Prudential Regulation Authority (PRA)](https://www.bankofengland.co.uk/prudential-regulation) - UK prudential regulator for banks and insurers. Their AI in financial services work runs alongside the FCA's.
- [European Banking Authority (EBA)](https://www.eba.europa.eu/) - EU banking regulator. Their guidelines on internal governance and ICT risk management apply to AI systems in financial services.
- [European Securities and Markets Authority (ESMA)](https://www.esma.europa.eu/) - EU capital markets regulator. Published guidance on AI in investment management and financial advice.
- [US Federal Trade Commission (FTC)](https://www.ftc.gov/business-guidance/blog/2023/02/keep-your-ai-claims-in-check) - US consumer protection regulator. Their AI guidance focuses on deceptive claims, discrimination, and unfair practices in AI-mediated consumer decisions.
- [Google Secure AI Framework](https://safety.google/cybersecurity-advancements/saif/) - Google's framework for securing AI systems with six core elements covering foundations, detection, response, and standardisation.
- [NIST AI Resource Center](https://airc.nist.gov/) - Central hub for NIST AI governance resources including AI RMF, TEVV guidance, and sector-specific playbooks.
- [OpenSSF AI/ML Security Working Group](https://openssf.org/) - Open Source Security Foundation working group on security for AI and ML supply chains. Produces guidance on securing training pipelines and model artifacts.
- [Partnership on AI](https://partnershiponai.org/) - Multi-stakeholder organization producing research and guidance on responsible AI development and deployment practices.
- [UK NCSC: Guidelines for Secure AI System Development](https://www.ncsc.gov.uk/collection/guidelines-secure-ai-system-development) - Co-authored by NCSC (UK), CISA (US), ACSC (Australia), and 15 other national cybersecurity agencies. Practical security guidance across the AI development lifecycle.

---

## Learning Resources

- [EU AI Act Compliance Checker](https://artificialintelligenceact.eu/assessment/eu-ai-act-compliance-checker/) - Interactive tool for assessing whether a specific AI system falls under EU AI Act obligations and which requirements apply.
- [IAPP AI Governance Professional (AIGP)](https://iapp.org/certify/aigp) - Certification covering AI risk assessment, policy development, and compliance implementation. The most widely recognized credential for AI governance practitioners.
- [OWASP LLM AI Security and Governance Checklist](https://genai.owasp.org/) - Practical checklist for teams deploying LLM-powered systems in production.
- [RansomLeak Agentic AI Security exercises](https://ransomleak.com/catalog/ai-security/) - Hands-on browser exercises for the OWASP Agentic AI Top 10 and MCP Top 10, plus an EU AI Act course covering oversight and incident reporting duties.
- [SANS Institute AI Security Resources](https://www.sans.org/artificial-intelligence) - SANS training and research on AI/ML security covering adversarial attacks, model security, and secure deployment practices.
- [Singapore AI Governance Readiness Checklist](https://vyrwork.com/tools/singapore-ai-governance-readiness-checklist) - Free evidence-oriented checklist mapping IMDA's four agentic AI governance dimensions to 24 production-readiness prompts covering risk bounds, accountable ownership, lifecycle controls, and end-user responsibility.
- [State of AI Governance Report](https://www.credo.ai/resources) - Annual enterprise survey of AI governance program maturity, common gaps, and implementation patterns from Credo AI.

---

## Industry Conferences

- [Money 20/20](https://www.money2020.com/) - Algorithmic decisioning and AI in financial services.
- [FAccT](https://facctconference.org/) - ACM Fairness, Accountability, and Transparency Conference. The primary academic venue for ML fairness and accountability research.
- [AIES](https://www.aies-conference.com/) - AAAI/ACM AI Ethics and Society.
- [Compliance Week Europe](https://www.complianceweek.com/) - Compliance officer audience; AI governance is an increasingly prominent track.
- [AI Safety Summit](https://www.gov.uk/government/topical-events/ai-safety-summits) - UK-government-convened summits on frontier AI risks. Published commitments from labs and governments.

---

## Newsletters and Blogs

- [Stratechery on AI Policy](https://stratechery.com/) - Ben Thompson's analysis where it touches AI regulation and market structure.
- [Import AI](https://importai.substack.com/) - Jack Clark's policy-and-research weekly. One of the most consistently well-sourced newsletters in the field.
- [The Algorithm (MIT Technology Review)](https://www.technologyreview.com/newsletters/the-algorithm/) - MIT Technology Review's AI newsletter, strong on regulatory and societal coverage.

---

## Books

- [The Alignment Problem (Brian Christian, 2020)](https://brianchristian.org/the-alignment-problem/) - Accessible introduction to the alignment problem.
- [Algorithms of Oppression (Safiya Umoja Noble, 2018)](https://safiyaunoble.com/research-writing/) - Foundational text on algorithmic bias and its real-world consequences.
- [Atlas of AI (Kate Crawford, 2021)](https://katecrawford.net/) - Examines the material and political dimensions of AI infrastructure. Relevant background for anyone building governance frameworks that go beyond technical compliance.
- [The Ethical Algorithm (Michael Kearns and Aaron Roth, 2019)](https://global.oup.com/academic/product/the-ethical-algorithm-9780190948207) - How to design algorithms that are fair, private, and robust. Written for practitioners, not just researchers.

---

## Related Lists

- [awesome-ai-agent-governance](https://github.com/systempromptio/awesome-ai-agent-governance) - One of this list's two source lists. Actively maintained, narrowly focused on runtime agent governance.
- [awesome-ai-governance](https://github.com/Aperintelligence/awesome-ai-governance) - This list's other source list. Broader focus on AI governance for regulated industries.
- [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) - Comprehensive directory of MCP server implementations.
- [AwesomeResponsibleAI](https://github.com/AthenaCore/AwesomeResponsibleAI) - Academic and policy resources for responsible AI covering ethics, standards, and regulatory frameworks.

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the criteria a new entry must meet.

## License

This list merges and deduplicates two source lists: [awesome-ai-agent-governance](https://github.com/systempromptio/awesome-ai-agent-governance) (runtime governance of AI agents) and [awesome-ai-governance](https://github.com/Aperintelligence/awesome-ai-governance) (AI governance for regulated environments). Both were released under CC0 1.0 Universal.

This list is published under [CC0 1.0 Universal](LICENSE), consistent with the license of both source lists it merges. The linked resources retain their own licenses.
