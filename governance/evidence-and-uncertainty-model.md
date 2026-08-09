# Evidence and uncertainty model

## Evidence states

Each claim has one of four states:

- **supported** — sufficient relevant evidence currently supports it;
- **contradicted** — relevant evidence conflicts with it;
- **unresolved** — available evidence is insufficient or inconsistent;
- **not assessed** — no valid assessment has yet been performed.

The state is contextual and time-bound, never universal proof.

## Evidence quality dimensions

| Dimension | Question |
|---|---|
| Relevance | Does the evidence address this claim in this context? |
| Credibility | Is the source and collection method trustworthy? |
| Representativity | Does it cover the populations, loads, environments, and regimes of interest? |
| Independence | Are apparent confirmations derived from the same underlying source? |
| Freshness | Is the evidence still valid for the current system and decision? |
| Reproducibility | Can the observation or calculation be replayed? |

## Uncertainty decomposition

Do not use “variance” as a generic synonym for uncertainty. Report at least:

\[
U = U_{data} + U_{model} + U_{context} + U_{source\ gaps} + U_{disagreement}
\]

These terms need not be numerically additive; the expression is a checklist of distinct origins.

Use probabilities only when the estimation process can be explained and calibrated. Otherwise use transparent ordinal levels with evidence gaps. A similarity score is not a probability of patentability, legal validity, business success, or correctness.

## Updating beliefs

New evidence must append a new assessment or supersede an earlier one explicitly. Never overwrite an inconvenient historical conclusion. Preserve what was believed, why, by whom, and what changed.

