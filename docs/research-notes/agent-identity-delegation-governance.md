# From Human Identity to Verifiable Agent Authority

**Research note — 19 August 2026**

## Source that triggered this note

Ashok Singal, *From verifying humans to AI agents: Socure prepares for the next identity challenge*, Biometric Update, 16 August 2026.

Source: https://www.biometricupdate.com/202608/from-verifying-humans-to-ai-agents-socure-prepares-for-the-next-identity-challenge

## Executive summary

The important shift described by Socure is not merely that fraudsters can use AI agents. It is that identity infrastructure can no longer assume that the actor performing a transaction is a human. A legitimate AI agent may act for a person, employee, company or public body. Trust therefore becomes a chain: establish the principal, establish that authority was delegated, identify the agent, bind the delegation to a purpose and scope, authorize each consequential operation, and preserve evidence that the observed action remained within that authority.

A useful conceptual chain is:

```text
Principal -> Delegation -> Agent identity -> Mission / purpose
          -> Authorization -> Tool / service -> Effect -> Evidence
```

A robust architecture should keep separate **identity, authentication, delegation, authorization, mission/purpose, observed action/effect and evidence**. Collapsing them into one unexplained “agent trust score” risks hiding the exact failure mode that governance needs to reconstruct.

## What Socure actually says — and what it does not yet prove

Socure's CPO Chung-Man Tam frames AI agents as a structural shift. Biometric Update reports Socure's view that services will increasingly need to verify the person or organization, the delegated authority, the agent identity and scope, and whether each action is still inside that scope. The article also highlights lifecycle questions such as revocation, continuing authority and agents invoking other agents.

This should not be confused with a claim that Socure has already implemented the whole trust chain. Its current RiskOS MCP Server is an authenticated developer integration surface for documentation, OpenAPI schemas, account configuration, workflow metadata and webhook management. Socure's own documentation states that the MCP Server does **not** execute RiskOS transactions or evaluations. Authenticated MCP access is therefore not, by itself, proof of agent identity, delegated authority, purpose, or authorization for a consequential business action.

## Cross-check with emerging standards and adjacent work

### NIST NCCoE — software and AI agent identity and authorization

NIST's 2026 NCCoE concept work explicitly addresses identification, authorization, auditing and non-repudiation for software and AI agents. The motivating scenario is an agent moving beyond generated text to actions such as deploying code to production. This independently supports Socure's framing that agent identity and authority are becoming infrastructure problems rather than application-specific features.

- https://www.nccoe.nist.gov/projects/software-and-ai-agent-identity-and-authorization
- https://csrc.nist.gov/pubs/other/2026/02/05/accelerating-the-adoption-of-software-and-ai-agent/ipd

### IETF / OAuth — task-bound and multi-hop delegation

Several 2026 Internet-Drafts explore ways to bind authorization to agent identity, task context, operational constraints and delegation chains. They are drafts, not settled standards, but they show where the interoperability problem is moving.

- https://datatracker.ietf.org/doc/html/draft-klrc-aiagent-auth-02
- https://datatracker.ietf.org/doc/draft-aap-oauth-profile/
- https://www.ietf.org/archive/id/draft-liu-agent-operation-authorization-02.html
- https://www.ietf.org/archive/id/draft-liu-ai-agent-authorization-integration-00.html
- https://datatracker.ietf.org/doc/draft-mishra-oauth-agent-grants/

### OpenID Foundation / AuthZEN — authorization at the tool call

The OpenID Foundation's 2026 AuthZEN work is particularly relevant because it targets the policy decision point rather than trying to turn identity into a single trust score. COAZ maps operations such as MCP tool calls to an authorization decision: may this agent, acting for this user, call this tool with these arguments? AARP addresses prerequisites such as human approval, delegated authority or attestation before policy can permit the action.

- https://openid.net/authzen-at-identiverse-2026-authorization-in-the-agent-era/
- https://openid.net/openid-foundation-advances-authorization-for-the-agent-era-with-new-authzen-working-group-drafts/
- https://openid.net/getting-cozy-with-coaz-securing-apis-and-ai-agents-with-standardized-authorization/

### Verifiable Trust / Verana / 2060 — a complementary VC-based perspective

A second perspective comes from the **Verifiable Trust** and **Verifiable Public Registry** work stewarded by the Verana Foundation. Fabrice Rochette is an editor of Verana specifications and is Co-Founder and CEO of **2060 OÜ**. The Verifiable Trust model uses resolvable DIDs, Verifiable Credentials, governed trust registries and DIDComm; a Verifiable Service can advertise MCP or A2A endpoints after a verify-first trust bootstrap.

- Specification: https://verana-labs.github.io/verifiable-trust-spec/
- GitHub: https://github.com/verana-labs/verifiable-trust-spec
- Foundation: https://veranafoundation.org/
- 2060: https://2060.io/
- 2060 projects / Hologram: https://2060.io/projects

2060's Hologram work takes the idea toward deployable AI agents: credential-based authentication, role- and purpose-based access control, MCP connectivity and approval workflows. This is complementary to the OAuth/AuthZEN family rather than necessarily a replacement: VC/DID approaches can establish portable claims and governance context, while policy engines can decide whether a concrete operation is permitted now.

### Workload identity — SPIFFE

SPIFFE is useful as a reminder that an agent is also a running workload. Portable cryptographic workload identity can anchor the runtime instance independently of the human or organizational principal. A complete design may therefore need both **principal/delegation identity** and **workload/runtime identity**.

- https://spiffe.io/docs/latest/spiffe-specs/spiffe/

## Architectural synthesis

A minimal evidence-bearing action record could contain:

```text
principal_id
agent_class
agent_instance_id
agent_provenance
mission_id

delegation_id
delegation_chain
scope
purpose
constraints
valid_from
valid_until

tool_id
resource_id
requested_action
executed_action
policy_decision
human_approval_ref

input_digest
output_digest
effect
timestamp
trace_id
evidence_refs
```

The design principle is:

> **No consequential agent action without attributable authority and reproducible evidence.**

This is intentionally stronger than “log the agent.” The evidence should support a later statement such as: *this identified runtime, acting for this principal under this bounded delegation, performed this operation against this resource, under this policy decision, and produced this observable effect.*

## AI-assisted engineering governance

This trust chain is directly relevant to AI-assisted engineering. An agent that reads documentation and proposes a change has a different authority class from an agent that creates code, modifies infrastructure, transmits information, merges a pull request or deploys to production.

The existing `evidence-guided-engineering-agents` reference architecture already separates action classes and requires human authority for consequential actions. Its current principles include permission inheritance, human authority and replayability. Agent identity and delegation make those governance principles enforceable across tools rather than remaining only behavioral instructions.

```text
Accountable owner
  -> approved mission and source manifest
  -> delegated agent authority
  -> identified agent/runtime
  -> bounded tool capability
  -> policy decision / human gate
  -> engineering action
  -> test and operational evidence
  -> decision record and replay
```

This applies to requirements analysis, architecture, code generation, BOM/IaC preparation, test design, CI/CD, release preparation, configuration changes, observability analysis and incident response. The key question is no longer only *“did the AI produce a good answer?”* but also *“was this agent authorized to make this type of change, using these sources, for this purpose, and can the decision be replayed?”*

Related repositories:

- https://github.com/gharbonnier78/evidence-guided-engineering-agents
- https://github.com/gharbonnier78/quality-intelligence-systems-governance
- https://github.com/gharbonnier78/scientific-research-harness

## Beyond enterprise: a society-wide governance perspective

The same primitives can appear at several scales, although the governance rules must differ by domain.

| Scale | Example delegation | Additional governance concern |
|---|---|---|
| Individual / citizen | personal agent books travel, pays an invoice, submits a form | informed consent, privacy, revocation, liability, accessibility |
| Enterprise-wide | agent reads repositories, prepares changes, buys services, operates workflows | segregation of duties, purpose limitation, audit, approval, IP/confidentiality |
| Public administration | agent assists a civil servant, handles a benefit case, prepares a decision | administrative law, due process, explainability, records retention, equality |
| Government-wide | agents coordinate across ministries or sovereign systems | legal mandate, national security, sovereignty, cross-domain trust |
| Inter-governmental | agents exchange credentials, permits, customs or treaty-related data | federation, jurisdiction, mutual recognition, diplomatic accountability |

The EU Digital Identity Wallet work is relevant to the citizen and cross-border identity side because it establishes common issuer-wallet-relying-party trust infrastructure and interoperable digital credentials across Member States. It does not itself solve AI-agent delegation, but it illustrates how shared trust frameworks can move from one organization to a multi-state ecosystem.

- https://digital-strategy.ec.europa.eu/en/policies/eudi-wallet-toolbox

The European Commission's 2026 work on GenAI adoption in public administrations also makes the organizational governance problem concrete: public bodies are already using GenAI for drafting, knowledge management, information processing and service delivery while facing governance, data-protection, readiness and sovereignty constraints.

- https://interoperable-europe.ec.europa.eu/collection/public-sector-tech-watch/document/adoption-generative-ai-eu-public-administrations-exploring-individual-behaviours-and-organisational

## Testing the authority chain: from coverage to meaningful fault detection

Traditional functional coverage is insufficient for this problem. A system may execute every expected flow while remaining unable to reject a materially wrong delegation.

Examples of authorization/delegation mutants:

```text
valid:      Principal P -> Agent A -> read repository X
mutant 1:   Principal P -> Agent B -> read repository X
mutant 2:   Principal P -> Agent A -> write repository X
mutant 3:   Principal P -> Agent A -> read repository Y
mutant 4:   Agent A acts after delegation expiry
mutant 5:   Agent A delegates to B although sub-delegation is forbidden
mutant 6:   A -> B -> C exceeds maximum delegation depth
mutant 7:   another principal reuses A's token or session
mutant 8:   same permission is used for a different declared purpose
mutant 9:   action is allowed but required human approval evidence is absent
```

A research metric worth testing — **not an established standard** — is an *Agent Delegation Mutation Score* (ADMS):

```text
ADMS = detected/rejected security-significant delegation and authority mutants
       ----------------------------------------------------------------------
       injected security-significant delegation and authority mutants
```

It should not be used as one opaque score. Mutants should be stratified by consequence, likelihood, attack surface and governance class. For rare but critical failures, a probability-of-detection style treatment may be more useful than raw mutation coverage.

## Perspectives and challenges

1. **Identity is necessary but insufficient.** A cryptographically identified agent can still exceed its mandate.
2. **Delegation must be attenuating.** A sub-agent should normally receive no more authority than the delegator possessed and should inherit purpose and expiry constraints.
3. **Purpose must become machine-checkable.** Scopes such as `repo:write` are often too broad for autonomous systems; purpose, resource, operation and context need to travel together.
4. **Runtime identity matters.** “Agent A” as a logical persona and the exact running instance executing a tool call are different security objects.
5. **Revocation must work at machine speed.** Long-running and multi-hop chains create propagation and stale-authority risks.
6. **Evidence must survive organizational boundaries.** A trustworthy record needs common semantics, integrity protection, timestamping and privacy controls.
7. **Human approval cannot be ceremonial.** The system should prove which decision required approval, what the approver saw and which exact action was subsequently executed.
8. **Privacy and minimization remain first-class.** Verifiability must not become universal surveillance. Selective disclosure and minimum necessary context are important design constraints.
9. **Federation is harder than enterprise IAM.** Enterprise, citizen, government and inter-government trust involve different legal roots of authority and mutual-recognition rules.
10. **Standards are moving quickly and remain incomplete.** Many agent-specific IETF documents cited here are Internet-Drafts; interoperability and conformance evidence matter more than choosing a fashionable protocol early.
11. **Governance is a layer above MCP/A2A.** Interoperability protocols can transport calls and messages; membership, policy, dissent, escalation, accountability and replay still require a governance architecture.
12. **AI-assisted governance must remain governable.** Agents may help discover evidence, test policy or prepare decisions, but the mechanism that governs them must itself be inspectable, testable and change-controlled.

## Working research proposition

> A portable, purpose-bound and evidence-bearing delegation layer can allow AI agents to act across tools and organizational boundaries while preserving human or institutional accountability — but only if identity, authorization, delegation, runtime provenance, policy decision and observed effect remain separable and independently testable.

This proposition is useful across biometric/digital identity, AI-assisted engineering, enterprise automation, citizen services and government interoperability. It should be treated as a research and architecture hypothesis, not as evidence that one current vendor or protocol has already solved the end-to-end problem.
