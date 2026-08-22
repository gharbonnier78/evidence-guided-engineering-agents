# Market Discovery v0 — pedagogical, review and lean/ablation discipline

**Status:** local harness extension under `harness-adoption.yaml`.

## 1. Why this exists

Market Discovery v0 is not only a commercial experiment. It is also a learning system. The process must therefore produce three distinct outputs:

1. **evidence** — what was actually observed;
2. **decision state** — what the evidence currently permits us to believe or do;
3. **human understanding** — whether an accountable person can explain the result, its limits, provenance, alternatives and economic consequences.

No amount of automated scoring, retrieval, LLM synthesis or workflow completion substitutes for those three layers.

## 2. Human-understanding gate

A market claim, offer hypothesis, tool justification, acquisition thesis or capability hypothesis must not become canonical merely because an automated workflow accepted it.

Before promotion, at least one accountable human must be able to explain in plain language:

- the observed evidence;
- what is inference rather than observation;
- the strongest alternative explanation;
- what would falsify the current interpretation;
- what the evidence does **not** establish;
- the decision or action this result may support;
- the economic consequence if the interpretation is wrong;
- the exact next evidence needed.

If this explanation cannot be produced, the result remains provisional regardless of automation confidence.

## 3. Lean / minimum-sufficient-mechanism rule

Every mechanism added to Market Discovery v0 is a hypothesis and is removable:

- paid database;
- prospect score;
- persona role;
- connector;
- LLM step;
- enrichment source;
- workflow stage;
- interview question;
- expert intervention;
- reporting artifact;
- automation.

The default question is not “can we add this?” but:

> Does this component measurably change a decision, reduce uncertainty, improve target quality, increase conversion quality, reduce delivery effort/risk, or improve unit economics beyond a simpler baseline?

If not, remove it.

## 4. Ablation protocol

When a component appears useful, test it against a simpler process whenever practical.

Examples:

- public sources only **vs** public sources + paid enrichment;
- human-only target selection **vs** human + LLM ranking;
- simple rules **vs** weighted scoring model;
- direct expert judgment **vs** persona-mediated analysis;
- generic discovery interview **vs** problem-signal-specific interview;
- manual proposal drafting **vs** evidence-guided assisted drafting;
- single-expert delivery **vs** orchestrated multi-expert capability composition.

For each ablation, predefine the decision-relevant metric before observing the result. Candidate metrics include:

- proportion of retained candidates that yield a meaningful conversation;
- false-positive rate in target qualification;
- time per qualified problem record;
- conversion to proposal;
- conversion to paid pilot;
- contribution margin;
- founder/expert hours;
- client-rated usefulness;
- decision changed / risk reduced / work avoided;
- rework rate;
- explanation quality and auditability.

Do not optimize a proxy merely because it is easy to measure.

## 5. Progressive sophistication rule

Use the least sophisticated model that is sufficient for the current decision.

Examples:

- start with categorical evidence levels before building a learned lead-ranking model;
- start with simple contribution-margin accounting before Monte Carlo business modelling;
- start with manual expert matching before building marketplace matching algorithms;
- start with explicit rules before training ML;
- use advanced ML, optimisation, Bayesian methods, simulation or quantum/hybrid methods only when the problem and evidence justify them.

Sophistication is not progress by itself.

## 6. Evidence-status discipline

Every material statement in the initiative should be classifiable as one of:

- **Observed fact** — directly supported by a cited source or recorded interaction;
- **Reported statement** — stated by an interviewee/client/provider but not independently verified;
- **Inference** — analyst interpretation of evidence;
- **Hypothesis** — proposition intentionally under test;
- **Measured outcome** — observed result of an executed experiment/pilot;
- **Rejected / falsified** — contradicted by sufficient evidence for the bounded question;
- **Unknown** — material uncertainty not yet resolved.

Do not collapse these states in summaries.

## 7. Review discipline

Significant transitions should be reviewable by someone who did not author the conclusion.

Review should focus on:

- source provenance;
- hidden assumptions;
- selection bias;
- survivorship bias;
- confirmation bias;
- confounding between company quality and market need;
- conflation of interest with willingness-to-pay;
- conflation of acquisition value with customer value;
- proxy metrics that may be easy to optimize but weakly related to business value;
- post-hoc threshold changes;
- undocumented exclusion of negative evidence;
- overclaiming from a tiny sample.

A reviewer may request a replay, counterexample, additional source, simpler baseline or ablation before promotion.

## 8. Pedagogical descent for difficult concepts

When the initiative introduces a concept that materially influences a decision — for example contribution margin, Bayesian updating, causal inference, calibration, confidence intervals, POMDP reasoning, option value, sensitivity analysis or acquisition finance — the explanation should include, at minimum:

1. vocabulary;
2. intuition;
3. one concrete example from the current initiative;
4. mathematical or formal formulation when relevant;
5. plain-language interpretation;
6. one check or reconstruction the accountable human can perform;
7. a common misconception;
8. an understanding gate.

The pedagogical layer explains the decision mechanism; it never replaces evidence.

## 9. Learning from negative results

A failed outreach, rejected proposal, unprofitable pilot, useless data source or unnecessary persona is not noise to hide. It is evidence when the failure mode is recorded carefully.

Each negative result should state:

- what was attempted;
- what was expected;
- what happened;
- plausible competing explanations;
- whether the hypothesis is rejected, weakened or merely unresolved;
- what will change next;
- whether a workflow/tool/persona should be removed.

This is the main route by which the initiative should improve.

## 10. Upstream promotion to the scientific-research-harness

Market Discovery v0 is a consumer of the generic harness. Domain-specific facts remain here.

However, a rule should be proposed upstream when repeated experience shows that it is reusable across research and engineering contexts, for example:

- minimum-sufficient-mechanism / removal tests;
- formal ablation of workflow components, not only model components;
- explicit separation of measured evidence from operational telemetry and commercial proxies;
- human-understanding gates;
- methods for learning from negative results without retrospective rewriting;
- evidence requirements for justifying paid tools or extra automation.

Upstream changes must be reviewed as harness changes, not silently assumed from one project.

## 11. Current application to Market Discovery v0

The immediate practical consequences are:

- do not buy prospecting data before a documented information gap exists;
- do not automate candidate scoring before a simple human-readable baseline exists;
- do not build a marketplace before repeated capability-gap evidence exists;
- do not call conversational enthusiasm validation;
- do not call a paid pilot profitable until direct costs and human effort are recorded;
- do not retain personas, workflow steps or reports that fail a removal test;
- preserve rejected targets, failed hypotheses and ablation results in the chronicle.
