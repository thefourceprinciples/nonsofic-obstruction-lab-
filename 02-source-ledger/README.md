# Source and Dependency Ledger

This directory records the external mathematical sources used by the lab, what each source actually establishes, and which claims remain open.

## S1 — OpenAI nonsofic-group construction

- Source: OpenAI, *Ten Advances in Mathematics and Theoretical Computer Science*.
- Formal repository: https://github.com/openai/ten-proofs
- Audited repository pin: `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6`
- Formal target: `SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group`
- Repository-local status: `ESTABLISHED / SOURCE-PINNED`; independent clean-room kernel reproduction here is still pending.

Role in this lab: primary construction, formal certificate, and source of the central criterion under reconstruction.

## S2 — Fournier-Facio torsion-free construction

- Francesco Fournier-Facio, *A torsion-free non-sofic group*.
- arXiv: https://arxiv.org/abs/2608.02025
- Initial submission: 2026-08-03.
- Reported result: a different source of nonsofic examples, using the same technical criterion, including torsion-free groups.
- Repository-local status: `ESTABLISHED / INDEPENDENTLY-REUSED` with respect to the criterion's mathematical use.

Role in this lab: feature ablation. It shows that torsion, the specific binary-Leavitt implementation, and Thompson's group V as the particular witness are not required for every construction using the criterion.

## S3 — Kun–Thom wreath-product construction

- Gábor Kun and Andreas Thom, *Nonsofic wreath products of residually finite groups*.
- arXiv: https://arxiv.org/abs/2608.06222
- Initial submission: 2026-08-06.
- Reported result: further applications of the proof mechanism yielding nonsofic generalized wreath products from explicit residually finite Kazhdan groups.
- Repository-local status: `ESTABLISHED / INDEPENDENTLY-REUSED` for the extended mechanism.

Role in this lab: evidence that the obstruction architecture is reusable beyond one isolated construction and a source of candidate generalizations/negative controls.

## S4 — Comparator

- Repository: https://github.com/leanprover/comparator
- Project pin used by `ten-proofs`: `07bc4ea40f2266dcb861820a2ec1fa3244ed307f`
- Role: exact-statement matching, permitted-axiom checking, Lean-kernel replay, and optional nanoda replay.

## Source policy

A source entry is not a summary of community consensus. It records a specific technical role.

When a source is corrected, superseded, or challenged:

1. retain the old pin;
2. add the new version/pin;
3. state exactly which claim changed;
4. do not silently overwrite the historical record.
