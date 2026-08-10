# Toy experiment: BOM to reviewed IaC

## Claim under test

A governed BOM persona can improve traceability and defect discovery when translating an approved synthetic MTP recommendation into a BOM and IaC draft, without increasing expert review effort beyond an agreed threshold.

## Baseline

An engineer performs the same task using the existing templates and approved sizing workbook.

## Experimental workflow

1. Create a synthetic MTP with requirements, ambiguities, and known traps.
2. Freeze the approved sizing calculator and reference catalog.
3. Run baseline and agent-assisted workflows on the same case.
4. Require both to produce BOM, assumptions, dependencies, IaC draft, tests, and observability obligations.
5. Have independent experts review outputs blind to their origin where practical.
6. Replay every derived value to its source.

## Measures

- seeded defect detection;
- unsupported components or fabricated compatibility claims;
- requirement-to-BOM-to-IaC trace completeness;
- expert correction time;
- sensitivity to changed load and availability assumptions;
- divergence between approved BOM and IaC;
- usefulness of generated installation documentation.

## Falsification conditions

The claim is weakened if the agent misses more critical traps, increases review effort materially, invents dependencies, obscures the approved calculator, or produces IaC that cannot be traced to the BOM.

## Data

Use synthetic products, loads, prices, versions, and telemetry. Do not use customer or internal infrastructure data in this public experiment.

