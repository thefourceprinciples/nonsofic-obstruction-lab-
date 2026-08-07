# NSOF–P23–MAP–001

## Quantitative dependency reconstruction of Proposition 2.3

**Status:** `ESTABLISHED` for the source proposition; `PROPOSAL / OPEN` for this repository's quantitative reformulations.

The immediate goal is not to improve the theorem. It is to reconstruct its proof so precisely that every hypothesis, quantitative estimate, imported theorem, and error transfer has an inspectable role.

## Source statement

At the current OpenAI manuscript revision, Proposition 2.3 assumes:

```text
Γ ≤ G are infinite groups
Γ has property (T)
G = <Γ, t1, ..., tm>, with m ≥ 1
ti Γ ti^-1 ≤ Γ for 1 ≤ i ≤ m
J ≤ G is finitely generated
[Γ, J] = 1
Γ ∩ J = {1}
t1 J t1^-1 ≤ Γ
```

It additionally assumes that `G` admits a sofic approximation whose generator graphs, for some finite symmetric generating set, differ by `o(|Y_n|)` edges from uniformly bounded-degree graphs with a uniform positive expansion constant.

Conclusion:

```text
J is LEF.
```

**Important scope note:** property (T) is required in the proposition only for `Γ`. In the concrete application, property (T) of `G` is used to obtain the expanding sofic approximation required by the proposition.

Primary source: OpenAI, *Ten Advances in Mathematics and Theoretical Computer Science*, Chapter 3, Proposition 2.3.

## Proof architecture to reconstruct

The manuscript organizes the proof around the following route:

```text
restrict the G approximation to Γ
        |
        v
Kun decomposition into expanding Γ-components
        |
        v
transport components by the ti
        |
        v
locate dominant original components
        |
        v
median-normalized component-size function
        |
        v
ambient expansion forces size concentration
        |
        v
first transported partition matches almost injectively
        |
        v
J almost preserves original Γ-components
        |
        v
select one expanding component and repair partial actions
        |
        v
Kun–Thom single-expander theorem
        |
        v
J is LEF
```

## Reconstruction deliverables

For each proof step we will record:

```text
input hypotheses
external theorem/lemma invoked
finite generating sets used
quantitative constants introduced
exceptional-set size
edge-edit budget
component-size or boundary estimate
map/permutation being transported
output invariant
exact dependency on previous steps
```

The first target is a `HYPOTHESIS_LEDGER.md` mapping each assumption to every place it is consumed.

## Research question opened by the reconstruction

After the source proof is reconstructed, we will test one explicitly exploratory idea:

> Can the many-component matching argument be profitably reformulated using dyadic component-size shells and a multiscale defect budget?

That question lives in `04-component-spectrum/`. No equivalence or strengthening is presently claimed.
