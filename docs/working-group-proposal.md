# Working-group proposal

## Purpose

Run a bounded experiment to determine whether governed AI personas can improve an existing engineering decision workflow while preserving human authority, confidentiality, and operational simplicity.

## Proposed scope

Begin with two demonstrators:

1. **BOM-to-reviewed-IaC:** translate a synthetic MTP recommendation into a traceable BOM and a reviewed infrastructure-as-code draft.
2. **Invention-to-expert-review:** identify a candidate technical contribution in synthetic project artifacts, produce a preliminary falsification report, and stop at a consent gate before any external transmission.

## Participation model

Use an open call for small teams. A candidate team may bring its own methods and tools, provided it accepts the common evidence contract, safety boundaries, evaluation protocol, and publication rules. If several teams participate, compare them on the same cases before selecting or combining approaches.

Possible contributors include systems engineering, integration, industrialization, platform/DevOps/SRE, test, architecture, product, security, data/ML, legal/IP, finance, and procurement.

## Eight-week pilot

| Phase | Weeks | Output |
|---|---:|---|
| Frame | 1 | Decision question, baseline, authorized corpus, risks |
| Design | 2 | Agent contracts, schemas, gates, evaluation plan |
| Build | 3–4 | Minimal demonstrators and audit trail |
| Exercise | 5–6 | Blind or counterbalanced comparison on synthetic/public cases |
| Challenge | 7 | Independent expert review and red-team session |
| Decide | 8 | Continue, revise, merge approaches, or stop |

## Gates

| Gate | Decision |
|---|---|
| G0 — Authorization | Are sources, purposes, participants, and retention rules approved? |
| G1 — Design readiness | Are claims, metrics, baselines, failure modes, and stop conditions explicit? |
| G2 — Safe execution | Can the demonstrator run without exposing restricted data or taking external action? |
| G3 — Evidence review | Did it improve decision preparation without unacceptable errors or effort? |
| G4 — Scale decision | Is the evidence strong enough for another bounded deployment? |

## Minimum evaluation

- compare against the current human workflow, not against doing nothing;
- use negative cases where no opportunity should be raised;
- measure false positives and expert review burden;
- record whether the agent changed a decision for a justified reason;
- perform an ablation/removal test on each persona;
- publish failures and unchanged decisions as valid outcomes.

## Expected decision after the pilot

The working group does not seek approval for an enterprise platform. It seeks evidence for one of four decisions: **stop**, **revise**, **repeat on a new case**, or **prepare a controlled operational pilot**.

