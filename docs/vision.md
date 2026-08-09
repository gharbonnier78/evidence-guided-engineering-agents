# Vision and boundaries

## Problem statement

Complex engineering decisions are rarely blocked by a total absence of information. They are blocked by fragmented evidence, hidden assumptions, competing objectives, weak feedback loops, and irreversible actions taken before uncertainty is understood.

The proposed system is an **Evidence-Guided Falsification Recommender**: a governed set of AI personas that generates candidate directions, searches for reasons they may fail, simulates consequences where appropriate, and learns from the evidence produced by subsequent action.

## Core claim

> For selected engineering decisions, a permission-aware and evidence-linked agent workflow can improve the completeness, challenge quality, and replayability of decision preparation without transferring accountability away from humans.

This is a hypothesis to test, not an established fact.

## Principles

1. **Evidence before fluency.** A well-written recommendation is not evidence.
2. **Falsification before promotion.** Search actively for counterexamples, prior art, missing dependencies, and failure modes.
3. **Uncertainty remains visible.** Do not collapse conflicting evidence into one unexplained score.
4. **Minimum sufficient complexity.** Combine only mechanisms covering genuinely distinct evidence sources or failure modes.
5. **Removal test.** If removing a persona or model does not materially degrade a predefined outcome, remove it.
6. **Permission inheritance.** An agent cannot broaden the access rights of its user or source.
7. **Human authority.** Consequential actions require a named accountable decision owner.
8. **Replayability.** Preserve source versions, model/tool versions, prompts or policies, outputs, dissent, decisions, and outcomes.
9. **Reversible first step.** Prefer the cheapest credible experiment that reduces decision-relevant uncertainty.
10. **Reuse before reinvention.** Integrate reliable commercial or internal capabilities when they satisfy the evidence contract.

## Non-goals

The system is not intended to:

- replace engineers, architects, legal counsel, patent professionals, finance, procurement, security, or management;
- monitor employees covertly;
- ingest all available enterprise data by default;
- make autonomous filing, contracting, hiring, funding, release, or production decisions;
- claim legal, financial, safety, or patent certainty;
- optimize a single score while hiding trade-offs.

## Success criteria for an initial pilot

Compared with an agreed baseline workflow, the pilot should measure:

- relevant evidence recovered;
- important counterarguments discovered;
- unsupported claims and hallucinated facts;
- time required from domain experts;
- decision changes caused by new evidence;
- trace completeness and replayability;
- false-positive burden;
- participant trust and perceived intrusiveness.

Scaling is permitted only after an explicit review of these results.

