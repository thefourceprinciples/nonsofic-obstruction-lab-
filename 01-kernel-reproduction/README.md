# FA–NSOF–KERNEL–REPRO–001

## Independent Lean-kernel reproduction package for the nonsofic-group certificate

This directory documents an independent reproduction target for the Lean certificate released in `openai/ten-proofs` for:

```lean
SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group
```

The trusted challenge states:

```lean
theorem exists_finitelyPresented_nonsofic_group :
    ∃ (G : Type) (_ : Group G),
      Group.IsFinitelyPresented G ∧ ¬ SoficGroups.Sofic G
```

The audit deliberately separates four claims:

1. **Source identity** — the exact repository revision and dependency graph are pinned.
2. **Ordinary Lean acceptance** — Lean 4.32.0 elaborates and its kernel accepts `NonSoficGroup.lean`.
3. **Independent kernel replay** — nanoda independently type-checks the exported declarations with `sorryAx` forbidden.
4. **Comparator certification** — Comparator verifies that the solution proves the exact trusted challenge statement and stays within the permitted axiom set.

A successful run does **not** by itself establish that every formal definition or imported theorem perfectly captures every intended informal statement in the manuscript. Semantic correspondence remains a separate audit.

Current repository status: **protocol prepared; independent clean-room execution pending**.

See [`REPRODUCTION_PROTOCOL.md`](REPRODUCTION_PROTOCOL.md) for the pass criteria and trust boundary.
