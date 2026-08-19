# From Human Identity to Verifiable Agent Authority

**Research note — 19 August 2026**

> Status: exploratory architecture synthesis. This note distinguishes public evidence, emerging standards, vendor capabilities, and research propositions. It does not claim that any single vendor or protocol solves the end-to-end problem.

## Trigger source

Ashok Singal, **“From verifying humans to AI agents: Socure prepares for the next identity challenge”**, *Biometric Update*, 16 August 2026.

Source: https://www.biometricupdate.com/202608/from-verifying-humans-to-ai-agents-socure-prepares-for-the-next-identity-challenge

## Executive summary

The key shift is not merely that fraudsters can use AI. Legitimate AI agents will increasingly act for people, employees, companies and public bodies. Identity infrastructure must therefore move from a mostly human-centric question — *who are you?* — to an attributable authority chain:

```text
Principal -> Delegation -> Agent/runtime identity -> Mission/purpose
          -> Authorization -> Tool/service -> Effect -> Evidence
```

That chain is necessary but not sufficient. An authenticated and authorized agent may still be unreliable, drifted, poorly grounded, or coupled to a changed downstream system. A second **Assurance Plane** is therefore required:

```text
Relevance -> Validity -> Reliability -> Robustness/stability
          -> Evidence quality -> Monitoring -> Change control
          -> Requalification -> Recovery
```

The working proposition is:

> **Trustworthy agent action = Attributable Authority AND Continuously Qualified Assurance.**

Trust should not be granted once. It should be continuously re-earned against versioned evidence and operating conditions.

## Who is NIST and why is it relevant?

The **National Institute of Standards and Technology (NIST)** is a U.S. federal agency within the Department of Commerce. It is not an AI or identity vendor. NIST develops measurement science, technical guidance, test methods, standards foundations, interoperability practices and reference resources used by government and industry.

Its AI work is relevant in three complementary ways:

1. **AI Risk Management Framework (AI RMF).** NIST organizes AI risk management around Govern, Map, Measure and Manage. Trustworthiness is explicitly multi-dimensional: valid and reliable, safe, secure and resilient, accountable and transparent, explainable and interpretable, privacy-enhanced, and fair with harmful bias managed.
2. **Lifecycle reliability and drift.** NIST explicitly treats reliability as performance over time under defined conditions, and recommends ongoing testing, monitoring, drift detection, incident response, change management and decommissioning where risk exceeds tolerance.
3. **Agent-specific work in 2026.** The NCCoE concept project on *Software and AI Agent Identity and Authorization* explores standards-based identification, management and authorization of software agents, including agents that can take consequential actions such as deploying code. NIST’s separate *Building Evaluation Probes into Agentic AI* project examines evidence-grounding quality with machine-readable probes for faithfulness, completeness and sufficiency.

Key public references:

- AI RMF: https://www.nist.gov/itl/ai-risk-management-framework
- Trustworthiness characteristics: https://airc.nist.gov/airmf-resources/airmf/3-sec-characteristics/
- Playbook — Measure: https://airc.nist.gov/airmf-resources/playbook/measure/
- Playbook — Manage: https://airc.nist.gov/airmf-resources/playbook/manage/
- NCCoE agent identity/authorization: https://www.nccoe.nist.gov/projects/software-and-ai-agent-identity-and-authorization
- Agentic AI evaluation probes: https://www.nist.gov/programs-projects/building-evaluation-probes-agentic-ai

NIST does **not** “guarantee” trustworthiness. Its contribution is a measurement, governance and lifecycle framework for building justified confidence and managing residual risk.

## Who is Socure and what is its business?

**Socure, Inc.** is a commercial U.S. identity and risk technology company. Its business covers digital identity verification, fraud prevention, KYC/KYB, compliance and sanctions screening, authentication, device/behavior intelligence and risk decisioning. Socure markets to financial services, fintech, government, gaming, marketplaces, healthcare, telecom and e-commerce, and states that it serves more than 3,000 customers.

Its platform **RiskOS** is positioned as an AI-native identity/fraud/risk/compliance decisioning and orchestration layer. It combines Socure models and identity intelligence with configurable workflows and external data/integration sources.

Relevant public references:

- Company/business: https://www.socure.com/company
- RiskOS: https://www.socure.com/solutions/riskos
- RiskOS documentation: https://help.socure.com/riskos/docs/socure-platform

Socure is important here for two reasons. First, the Biometric Update article is an industrial signal that a major identity-risk vendor sees **legitimate agent identity and delegated authority** as the next identity challenge. Second, RiskOS already exposes concrete lifecycle practices relevant to assurance:

- workflow major/minor versioning and version history;
- frozen published/live workflows and explicit restore/duplicate processes;
- model-version visibility;
- Active / Challenger / Latest model comparison, including shadow mode;
- API version pinning to avoid unexpected behavioral changes;
- audit logs recording what changed, who changed it and when.

References:

- Workflow lifecycle/versioning: https://help.socure.com/riskos/docs/manage-workflow-lifecycle
- Model Active/Challenger/Latest: https://help.socure.com/riskos/docs/case-review-process
- API version pinning: https://help.socure.com/riskos/reference/postevaluation
- Audit logs: https://help.socure.com/riskos/docs/use-audit-logs

### Important limitation

Socure’s current MCP Server connects AI development tools to RiskOS documentation, workflows and API schemas. Socure’s documentation states that this MCP surface does **not** execute RiskOS transactions or evaluations.

Therefore:

> **Authenticated MCP access is not, by itself, verified delegated authority for a consequential action.**

A key may authenticate access to a service boundary without proving the principal, delegated mission, runtime instance, exact allowed operation, or resulting effect.

## Cross-check with adjacent standards and work

### IETF / OAuth

Several 2026 Internet-Drafts explore agent authentication, task-bound authorization, operation authorization, delegation chains and agent grants. These are drafts rather than settled standards, but they show a clear direction toward contextual, attenuated, multi-hop authorization.

- https://datatracker.ietf.org/doc/html/draft-klrc-aiagent-auth-02
- https://datatracker.ietf.org/doc/draft-aap-oauth-profile/

### OpenID AuthZEN

AuthZEN is relevant because it externalizes the policy decision instead of reducing trust to a score: may this agent, acting for this principal, invoke this tool with these arguments, under this context and prerequisite evidence?

- https://openid.net/authzen-at-identiverse-2026-authorization-in-the-agent-era/

### Verifiable Trust / Verana / Fabrice Rochette / 2060

A complementary approach comes from the **Verifiable Trust** specification stewarded by the Verana Foundation. The public specification uses resolvable DIDs, Verifiable Credentials, Verifiable Public Registries and trust resolution to establish a verify-first Internet trust layer. The latest public specification identifies **Fabrice Rochette (The Verana Foundation)** as editor.

- Specification: https://verana-labs.github.io/verifiable-trust-spec/
- GitHub: https://github.com/verana-labs/verifiable-trust-spec
- Foundation: https://veranafoundation.org/

Public 2060 material identifies Fabrice Rochette as CEO and describes **2060** as an independent research and engineering company, a founding member of the Verana Foundation and the developer of **Hologram**, a commercial product line for verifiable AI-agent trust infrastructure.

- 2060: https://2060.io/
- Hologram/projects: https://2060.io/projects

The VC/DID/Verana perspective can complement OAuth/AuthZEN rather than replace it: credentials can establish portable attestations and governance context; a policy-decision layer can still decide whether a concrete operation is allowed **now**.

### Runtime/workload identity

A logical agent persona and the exact executing workload are different security objects. SPIFFE is a useful adjacent reference for portable workload identity:

- https://spiffe.io/docs/latest/spiffe-specs/spiffe/

## Architectural synthesis: Authority Plane x Assurance Plane

### Authority Plane

Keep distinct:

- **Identity** — who/what is the actor?
- **Authentication** — how is that identity demonstrated now?
- **Delegation** — what authority was transferred, by whom, with what attenuation and expiry?
- **Mission/purpose** — why is the agent acting?
- **Authorization** — may this exact action occur now?
- **Observed effect** — what actually happened?
- **Evidence** — what proves the chain afterwards?

### Assurance Plane

The authorization decision should also depend on whether the agent remains qualified under current conditions:

- **Relevance** — does the agent still solve the current task and stakeholder need?
- **Validity** — is the intended use still satisfied?
- **Reliability** — does it perform as required over time under defined conditions?
- **Robustness/stability** — does behavior remain acceptable under perturbation and integration variability?
- **Evidence quality** — are sources faithful, complete, sufficient, traceable and versioned?
- **Security/resilience** — can dependencies withstand misuse, compromise or partial failure?
- **Change integrity** — are material changes detected?
- **Requalification** — do changes trigger proportionate retest/reapproval?
- **Recovery** — can the organization stop, roll back, contain and explain failure?

A model version alone is insufficient. The effective execution envelope may depend on model, prompt/policy, retrieval corpus, embeddings/indexes, MCP/A2A tools, API/schema versions, workflow/rule versions, authorization policies, environment and downstream-system contracts.

## AI-assisted engineering governance

This trust architecture is directly relevant to AI-assisted engineering. An agent that reads a specification is not in the same authority class as an agent that creates code, modifies infrastructure, transmits information, merges a change or deploys to production.

```text
Accountable owner
  -> approved mission and source manifest
  -> delegated agent authority
  -> identified agent/runtime
  -> bounded tool capability
  -> policy decision / human gate
  -> engineering effect
  -> test + operational evidence
  -> decision record + replay
```

The key question is no longer only *“did the AI produce a good answer?”* but also:

> *Was this agent authorized to make this type of change, using these sources, for this purpose, under still-valid operating conditions, and can the resulting decision/effect be replayed?*

Related public repositories:

- https://github.com/gharbonnier78/evidence-guided-engineering-agents
- https://github.com/gharbonnier78/quality-intelligence-systems-governance
- https://github.com/gharbonnier78/scientific-research-harness

## Beyond enterprise: individual, enterprise, government and inter-government governance

The same trust primitives can appear at several scales, although the legal and institutional rules differ.

| Scale | Example | Additional governance concerns |
|---|---|---|
| Individual / citizen | personal agent books travel, pays invoices, files forms | consent, privacy, revocation, liability, spending limits, accessibility |
| Enterprise-wide | agents read repositories, prepare changes, buy services, operate workflows | segregation of duties, purpose limitation, audit, IP/confidentiality, continuity |
| Public administration | agent assists civil servant or prepares a citizen case | due process, legal basis, equal treatment, appeal, records retention |
| Government-wide | agents coordinate across ministries / sovereign systems | mandate, sovereignty, classified information, national security |
| Inter-governmental | agents exchange credentials, permits, customs/treaty data | federation, jurisdiction, mutual recognition, trust anchors, dispute resolution |

EU Digital Identity Wallet work is useful as an adjacent precedent for cross-organization and cross-border trust infrastructure, although it does not itself solve AI-agent delegation:

- https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox

## Testing the trust chain

Nominal functional coverage is not enough. The system should be challenged with meaningful authority and assurance mutants.

Examples:

```text
valid:      Principal P -> Agent A -> read repository X
mutant 1:   Principal P -> Agent B -> read repository X
mutant 2:   Agent A -> write repository X
mutant 3:   Agent A -> read repository Y
mutant 4:   Agent A acts after delegation expiry
mutant 5:   forbidden sub-delegation A -> B
mutant 6:   another principal reuses A's session
mutant 7:   required human approval evidence is absent
mutant 8:   model changes without requalification
mutant 9:   retrieval corpus changes without evidence digest change
mutant 10:  tool/API semantics change behind the same endpoint
mutant 11:  evidence supports only part of the claim
mutant 12:  rollback path is unavailable
```

A research metric worth testing — **not an established standard** — is an **Agent Delegation Mutation Score (ADMS)**:

```text
ADMS = detected/rejected security-significant authority mutants
       ---------------------------------------------------------
       injected security-significant authority mutants
```

This must not become an opaque KPI. Mutants should be stratified by consequence, likelihood, attack surface and governance class; rare critical failures may justify a probability-of-detection treatment instead.

## Perspectives and challenges

1. Identity is necessary but insufficient.
2. Delegation should attenuate rather than expand authority.
3. Purpose should become machine-checkable.
4. Logical agent identity and runtime identity should be bound but kept distinct.
5. Trustworthiness is temporal; evidence can expire after material change.
6. Evidence presence is not evidence sufficiency.
7. Human approval must be bound to the exact decision and effect, not used ceremonially.
8. Controlled evolution must include tools, policies, corpora, schemas and downstream systems, not only models.
9. Requalification must be proportionate: neither “retest everything” nor silent inheritance is sustainable.
10. Verifiability must not become surveillance; minimization and selective disclosure remain first-class.
11. Federation across enterprises, citizens and governments is harder than enterprise IAM because roots of authority differ.
12. MCP/A2A are interoperability layers, not complete governance architectures.
13. AI-assisted governance must itself remain inspectable, versioned, testable and reversible.

## Working research proposition

> A portable, purpose-bound, evidence-bearing delegation layer can allow AI agents to act across tools and organizational boundaries while preserving human or institutional accountability — but only if identity, delegation, runtime provenance, authorization, evidence quality, operating conditions and observed effect remain separable and independently testable.

The accompanying arXiv-style PDF expands this note into a structured literature/architecture synthesis suitable as a LinkedIn attachment.