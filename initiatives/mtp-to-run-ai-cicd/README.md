# MTP-to-Run — Evidence-Guided Industrialization and AI-Augmented CI/CD

**Status:** discussion draft / working initiative
**Audience:** Technical Authority, Innovation, Architecture, Integration, DevOps/SRE, Cybersecurity, Product, Industrial Experts, Quality and Test
**Visibility:** public synthetic specification; no organization, customer, product or employee data

This initiative contains a proposal for a bounded working group and a 90-day pilot connecting:

`MTP recommendations → solution constraints → BOM family → governed IaC → testbed evidence → release recommendation → approved operational learning`.

The proposal extends existing AI-Augmented Test Authority and STRAT-Q work. It does not create an autonomous authority, replace product or architecture ownership, or authorize production changes without accountable human approval.

## Start here

- [Full proposal](docs/proposal.md)
- [Generic French sponsor note](docs/sponsor-note-fr.md)
- [Example Solution Manifest](examples/solution-manifest.example.yaml)
- [Proposed gates](governance/gates.yaml)
- [Diagram catalogue](diagrams/README.md)

## Repository structure

```text
docs/                 Proposal and discussion note
diagrams/src/         Editable SysML, UML and BPMN sources
diagrams/rendered/    Rendered SVG views
examples/             Non-production demonstration inputs
schemas/              Machine-readable contracts
governance/           Proposed gates and decision rules
```

## Repository position

This is an initiative of the wider Evidence-Guided Engineering Agents repository. Extraction into an independently versioned codebase should be considered only if the pilot produces an executable transformation engine, IaC generators or connectors with their own release lifecycle.

## Important boundaries

- Generated code is a proposal until reviewed and validated.
- The system may prepare a GO / CONDITIONAL GO / NO-GO dossier; accountable humans decide and sign.
- Customer telemetry is not reused merely because it is non-personal. Contract, confidentiality, purpose, security and lot-level approval gates apply.
- MTP recommendations remain distinguishable from contractual requirements, architecture decisions and sizing assumptions.
- No production autonomous remediation is included in the initial pilot.
- G0–G9 reuse the board's shared Policy & Human Gate Service; this initiative defines domain criteria rather than a parallel gate platform.
- The two-week framing phase ends at the distinct P0 milestone. The pilot cannot start before its baseline, thresholds, budget and measurement protocol are approved.
- Learning evidence uses a closed source type: customer telemetry, pilot testbed evidence or synthetic evidence.
