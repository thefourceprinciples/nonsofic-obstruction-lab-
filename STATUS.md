# Repository Status

Last updated: 2026-08-07

## Public claim boundary

This repository does **not** currently claim:

- a new nonsofic group;
- a new proof of Proposition 2.3;
- a proof that the proposed dyadic component-spectrum formulation is equivalent to or stronger than the source argument;
- a nonhyperlinear group;
- a decision procedure for soficity or hyperlinearity.

## Active work

### Kernel reproduction

Status: `SOURCE-PINNED / OPEN`

Prepared:

- exact OpenAI repository commit pin;
- trusted challenge and Comparator policy pins;
- Lean/mathlib/Comparator/lean4export/nanoda/landrun dependency pins;
- clean-room pass criteria;
- result template.

Pending:

- independent ordinary Lean build;
- exact theorem/axiom query;
- fresh Comparator run;
- independent nanoda replay through Comparator;
- retained public logs/artifacts.

### Proposition 2.3 dependency map

Status: `OPEN`

Prepared:

- exact source statement;
- hypothesis ledger;
- initial proof architecture.

Pending:

- line-by-line equation and constant ledger;
- explicit use sites for every hypothesis;
- imported theorem dependency graph;
- quantitative error-budget reconstruction.

### Dyadic component spectrum

Status: `PROPOSAL / OPEN`

Prepared:

- dyadic component-size shell definition;
- shell mass and candidate defect bookkeeping;
- broad/thin research question;
- explicit falsification criteria.

Pending:

- exact translation of source inequalities;
- negative controls;
- proof that any proposed shell inequality is genuinely implied by the source hypotheses.

### Carrier defect

Status: `PROPOSAL / OPEN`

Prepared:

- finite permutation-fragment diagnostic;
- finite-search/non-universal-theorem boundary;
- placeholder unitary branch.

Pending:

- definition/equivalence audit against standard sofic conventions;
- benchmark implementation;
- hyperlinear convention lock;
- controlled experiments.

## Next release gate

`v0.1` should not be tagged until the first kernel-reproduction workflow has either:

1. produced a complete PASS with retained logs; or
2. produced a documented partial/failure record that clearly identifies the blocking environment or formal issue.
