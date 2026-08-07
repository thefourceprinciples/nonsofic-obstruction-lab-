# Nonsofic Obstruction Lab

A reproducibility-first research repository for recent constructions of nonsofic groups and the finite-approximation obstructions behind them.

## Scope

This repository has four immediate goals:

1. independently reproduce the released Lean/Comparator certificate for the existence of a finitely presented nonsofic group;
2. reconstruct the dependency structure of the central nonsoficity criterion, especially the many-expander/component-matching step;
3. develop quantitative, explicitly labeled exploratory formulations of carrier defect and multiscale component structure;
4. keep established results, computational observations, conjectures, and new proposals strictly separated.

**No new nonsoficity theorem is currently claimed by this repository.**

## Start here

- [`STATUS.md`](STATUS.md) — exact current claim boundary and pending gates.
- [`ROADMAP.md`](ROADMAP.md) — staged research plan from reproduction to external review.
- [`docs/CLAIM_STATUS.md`](docs/CLAIM_STATUS.md) — vocabulary separating established results, reproduction, computation, proposals, and open claims.
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to submit reproductions, corrections, counterexamples, or formal work.

## Current research tracks

- `01-kernel-reproduction/` — pinned clean-room reproduction protocol for the OpenAI Lean certificate.
- `02-source-ledger/` — source, version, dependency, and claim-status records.
- `03-proposition-2-3/` — hypothesis-by-hypothesis reconstruction of the key criterion and its proof dependencies.
- `04-component-spectrum/` — exploratory dyadic component-size decomposition and multiscale defect bookkeeping.
- `05-carrier-defect/` — permutation and unitary carrier-defect formulations; exploratory unless explicitly proved.
- `06-formalization/` — future local Lean formalizations and statement correspondence checks.
- `docs/` — terminology, claim-status rules, contribution policy, and research boundaries.

## Claim discipline

Every substantive claim should be tagged with one of the statuses defined in [`docs/CLAIM_STATUS.md`](docs/CLAIM_STATUS.md). In particular:

- a successful finite computation is not a universal theorem;
- a successful Lean build is not automatically a semantic audit of the manuscript;
- reuse of a theorem by another paper is evidence of mathematical uptake, not a substitute for line-by-line verification;
- an analogy or proposed reformulation is not an established equivalence until the bridge is proved.

## Reproducibility target

The first audit is pinned to:

- repository: `openai/ten-proofs`
- commit: `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6`
- Lean: `v4.32.0`
- target theorem: `SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group`

See [`01-kernel-reproduction/REPRODUCTION_PROTOCOL.md`](01-kernel-reproduction/REPRODUCTION_PROTOCOL.md). A manual two-job GitHub Actions workflow is included at `.github/workflows/kernel-reproduction.yml`; it keeps the ordinary Lean build separate from the fresh Comparator/nanoda job.

## Primary external sources

- OpenAI, *Ten Advances in Mathematics and Theoretical Computer Science* and the public `openai/ten-proofs` formalization repository.
- Francesco Fournier-Facio, *A torsion-free non-sofic group*, arXiv:2608.02025.
- Gábor Kun and Andreas Thom, *Nonsofic wreath products of residually finite groups*, arXiv:2608.06222.

A source appearing here does not imply endorsement of every informal claim surrounding it. Exact source roles and pins are recorded in `02-source-ledger/`.

## Research principle

The repository is designed to make claims cheap to inspect: state the object, hypothesis, carrier, metric, proof or computation, provenance, and falsifier as explicitly as possible.

If an exploratory idea fails, the failure record remains useful.
