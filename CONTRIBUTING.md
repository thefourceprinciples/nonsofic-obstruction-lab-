# Contributing

Contributions are welcome when they make a claim easier to inspect, reproduce, correct, or falsify.

## Good first contributions

- reproduce the kernel audit on a fresh machine and attach complete logs;
- identify an incorrect pin, statement, citation, or dependency;
- trace one hypothesis of Proposition 2.3 through the proof and record exact use sites;
- provide a counterexample to an exploratory reformulation;
- improve a finite-search benchmark without changing its mathematical status;
- formalize a small definition or interface with a clear trust boundary.

## Required claim labeling

New mathematical content should use the vocabulary in `docs/CLAIM_STATUS.md`.

If a pull request contains a new conjecture or research idea, label it `PROPOSAL` or `OPEN` unless it includes a complete proof and the proof has been separately reviewed.

If a pull request contains a numerical or finite search result, report it as `COMPUTATIONAL-OBSERVATION` and include:

```text
code revision
input/presentation
parameters
random seed(s), if any
solver/version
hardware where relevant
complete result file or checksum
```

## Reproduction reports

A kernel reproduction report should not say “independently confirmed” unless it satisfies every pass criterion in `01-kernel-reproduction/REPRODUCTION_PROTOCOL.md`.

Partial runs are useful. Record them as partial.

## Style

Prefer:

```text
precise statement
explicit hypotheses
source pin
short derivation
failure condition
```

over broad claims or field-spanning analogy.

Exploratory analogies may be discussed when they generate a concrete mathematical definition, lemma, computation, or falsifiable question. The repository does not treat analogy itself as proof.

## Corrections

Corrections should preserve the historical record whenever possible. If a source or experiment changes materially, add a new version and state what changed instead of silently rewriting the earlier result.
