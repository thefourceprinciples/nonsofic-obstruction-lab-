# FA–CARRIER–001 — Finite Carrier-Defect Program

**Status:** `PROPOSAL / OPEN`

This directory develops quantitative diagnostics for finite approximation through different carrier families. The purpose is to organize computational searches and possible obstruction certificates without confusing finite evidence with a universal theorem.

## 1. Permutation carrier

Let `G` be a group, let `F` be a finite subset containing the identity, and let

```text
σ : G -> Sym(Y)
```

be a candidate finite permutation model on a nonempty finite set `Y`.

Using normalized Hamming distance `d_H`, define the finite-fragment multiplication defect

```text
M_F(σ)
  = max d_H(σ(gh), σ(g)σ(h))
```

where the maximum is taken over tested `g,h` whose product is included in the declared fragment.

Define identity defect

```text
I_F(σ) = d_H(σ(1), id).
```

For a fragment in which nonidentity elements are expected to be almost maximally separated from the identity, define

```text
S_F(σ)
  = max_{g in F, g != 1} (1 - d_H(σ(g), id)).
```

and the diagnostic

```text
D_F(σ) = max(I_F(σ), M_F(σ), S_F(σ)).
```

For theoretical bookkeeping, define the proposed finite-fragment permutation defect

```text
Delta_perm(G;F)
  = inf D_F(σ)
```

over all permitted finite permutation carriers/models of the declared type.

This notation is repository-local. Any theorem stated using it must first prove equivalence with the standard sofic approximation formulation being used.

## 2. Candidate obstruction quantities

For a finitely generated group with generating set `S` and Cayley ball `B_S(r)`, possible research diagnostics include:

```text
R_perm(G,S)
  = first radius at which a positive universal defect floor is proved;

epsilon_perm(G,S)
  = the corresponding proved defect floor;

C_cert(G,S)
  = a declared complexity measure for the shortest verified obstruction certificate.
```

These are **proposed invariants/diagnostics**, not standard invariants and not currently established to be generating-set independent.

## 3. Finite search versus theorem

For fixed fragment and carrier size, optimization is finite in principle. A computation can therefore report

```text
best_observed_defect(F,n).
```

But

```text
best_observed_defect(F,n) > 0
```

for many tested `n` does not prove a universal positive floor over all carrier sizes.

The promotion gate is:

```text
persistent finite defect
        |
        v
precise lower-bound conjecture
        |
        v
universal structural proof
        |
        v
formal/independent verification
```

## 4. Unitary/hyperlinear branch

A parallel experimental branch will replace finite permutations by finite-dimensional unitary matrices and normalized Hilbert–Schmidt error.

The exact unitary defect functional will be locked only after the repository fixes a standard hyperlinear convention and proves that the finite-fragment diagnostic matches it. Until then:

```text
Delta_unitary
```

is a placeholder research name, not a defined invariant.

Potential computational tools include Riemannian optimization on unitary groups, trace constraints, semidefinite relaxations, and noncommutative polynomial optimization. Numerical plateaus will be labeled `COMPUTATIONAL-OBSERVATION`, never `nonhyperlinear` without a universal proof.

## 5. Intended use

The carrier-defect program should answer questions of the form:

```text
What structure is being transported?
Through which finite carrier family?
Which relations must survive?
Which metric measures failure?
Can the error approach zero?
If not, is the obstruction observed or proved?
```

The strongest possible output is a carrier-specific no-go certificate with an explicit positive lower bound and a verifiable proof.
