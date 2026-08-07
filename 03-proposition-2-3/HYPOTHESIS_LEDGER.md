# Proposition 2.3 Hypothesis Ledger

**Status:** `PROPOSAL / OPEN` as an audit artifact. The proposition itself is `ESTABLISHED` in the cited source.

This file records the current hypothesis-use map. Entries marked `TO AUDIT` have not yet been traced through every line of the proof.

## H1 — `Γ ≤ G` and both groups infinite

Role:

- provides the subgroup whose restricted sofic approximation is decomposed into expanding components;
- infinitude is relevant to the approximation framework and the single-expander extraction background.

Audit state: `TO AUDIT` for every explicit use of infinitude.

## H2 — `Γ` has property (T)

Role:

- enables the Kun decomposition theorem on the restricted approximation of `Γ`;
- supplies uniform expansion of the resulting `Γ`-components after negligible edge edits.

Audit state: source use identified; quantitative constants still to extract.

## H3 — `G = <Γ, t1, ..., tm>`, `m ≥ 1`

Role:

- gives a finite generator system built from `Γ` plus the compressing elements;
- allows control of the full ambient generator graph through words in the selected generators;
- all `ti` participate in the component-size/ambient-expansion control, while only `t1` is needed later to transfer the `J` action.

Audit state: source use identified; exact word-length/error accumulation still to extract.

## H4 — `ti Γ ti^-1 ≤ Γ`

Role:

- ensures each transported `Γ`-component is approximately governed by `Γ`-words;
- yields the almost-monotonicity of the component-size function under positive compressing generators;
- feeds the median-normalization argument that prevents component sizes from drifting arbitrarily across the ambient expander.

Audit state: source use identified; exact dependence on each `ti` still to extract.

## H5 — `J ≤ G` finitely generated

Role:

- required by the Kun–Thom expander-centralizer theorem used at the end;
- permits a finite set of `J`-generator tests when selecting and repairing one component.

Audit state: source use identified.

## H6 — `[Γ, J] = 1`

Role:

- identifies `ΓJ` as a commuting product once combined with trivial intersection;
- supplies the centralizer structure needed for the final Kun–Thom step.

Audit state: source use identified; every local commutation test to be enumerated.

## H7 — `Γ ∩ J = {1}`

Role:

- together with commutation, identifies `ΓJ` with `Γ × J` rather than a nontrivial central product;
- preserves distinctness needed to interpret the repaired local action as an approximation of `Γ × J`.

Audit state: source use identified; exact distinctness checks still to extract.

## H8 — `t1 J t1^-1 ≤ Γ`

Role:

- transports each fixed `J`-generator into `Γ`;
- after component matching, allows `J`-generator component preservation to be deduced by conjugating a `Γ`-word preservation statement back through the permutation approximating `t1`.

Audit state: source use identified.

## H9 — expanding sofic approximation of `G`

Assumption:

For some finite symmetric generating set, the generator graphs differ in `o(|Y_n|)` edges from uniformly bounded-degree graphs with a uniform positive expansion constant.

Role:

- supplies the ambient expander used to force the bounded median-normalized component-size function to concentrate near its median;
- prevents the transported component system from escaping through uncontrolled size drift.

Audit state: source use identified; all constants and coarea estimates still to extract.

## Application-only input — property (T) of `G`

This is **not** a hypothesis of Proposition 2.3 itself.

In the binary-Leavitt application, property (T) of `G` is used to obtain an expanding sofic approximation if `G` is assumed sofic. That expanding approximation then satisfies H9.

This distinction is important for any attempt to weaken or generalize the criterion.

## Next audit pass

For every numbered equation and error term in the source proof, add:

```text
Step ID:
Source page/line:
Hypotheses consumed:
Input error budget:
Output error budget:
Uniform constant(s):
Asymptotic statement:
Can this step survive if a hypothesis is weakened?:
```
