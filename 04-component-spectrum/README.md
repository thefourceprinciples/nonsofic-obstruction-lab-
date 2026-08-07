# MPP–NSOF–001 — Dyadic Component-Defect Decomposition

**Status:** `PROPOSAL / OPEN`

This directory tests whether the many-expander/component-matching step in Proposition 2.3 admits a useful multiscale reformulation. The source proof is already established; this is an exploratory reparameterization, not a replacement theorem.

## Motivation

After restricting a sofic approximation to `Γ`, the source proof obtains a disjoint union of expanding `Γ`-components whose sizes need not be uniformly comparable. The proof controls this with a bounded median-normalized component-size function and the expansion of the ambient `G`-graph.

The present proposal asks whether the same phenomenon can be organized by dyadic component-size shells.

## Proposed shells

For the original `Γ`-component partition `Q_n`, define

```text
S_j(n) = { C in Q_n : 2^j <= |C| < 2^(j+1) }.
```

Define shell mass

```text
q_j(n) = (1 / |Y_n|) * sum_{C in S_j(n)} |C|.
```

Then

```text
q_j(n) >= 0,
sum_j q_j(n) = 1.
```

This is only bookkeeping: no new theorem follows from the definition.

## Proposed defect quantities

For a transport permutation `τ_i` approximating `t_i`, define a shell-resolved unmatched mass schematically by

```text
e_{i,j}(n)
  = (1 / |Y_n|)
    * sum over C in S_j(n)
      unmatched_mass(τ_i C).
```

The exact normalization and whether defect should be charged to the source shell, target shell, or both remain open design choices.

A second useful quantity may be a transition matrix

```text
T_i(j,k)
  = normalized mass sent from source shell j
    into a dominant target component in shell k.
```

The source theorem implies strong asymptotic constraints on these transitions after bad components are discarded. The first task is to derive those constraints exactly rather than assume them.

## Broad/thin research question

Borrowing only the proof architecture of a multiscale obstruction analysis, test whether bad behavior can be divided into two regimes:

```text
BROAD:
non-negligible defect or transported mass is spread across many size scales;

THIN:
most surviving mass is concentrated in a narrow window of size scales.
```

The names are descriptive only. They do not import Navier–Stokes estimates into group theory.

The goal would be to determine whether:

1. ambient expansion quantitatively suppresses the broad regime;
2. component matching and injectivity control the thin regime;
3. the resulting estimates recover, sharpen, or fail to improve the existing median argument.

## Falsification criteria

This proposal should be abandoned or substantially revised if any of the following occurs:

- the dyadic shell map discards exactly the information used by the median/coarea argument;
- shell transitions cannot be controlled uniformly from the hypotheses of Proposition 2.3;
- the decomposition merely restates the source proof with more notation and no quantitative or conceptual gain;
- a simple counterexample shows that broad/thin classification is not exhaustive under the declared definitions.

A negative result is still useful if it identifies why the source proof needs its bounded nonlinear normalization rather than a scale-shell representation.

## First deliverable

Derive the source proof's inequalities (dominant component estimate, almost-monotonicity, total variation, coarea concentration, near-size matching) in shell language and mark each transformation as:

```text
EXACT REWRITE
ONE-WAY BOUND
LOSSY SUMMARY
NOT AVAILABLE
```

Only exact rewrites or proved bounds may be used in later theorem statements.
