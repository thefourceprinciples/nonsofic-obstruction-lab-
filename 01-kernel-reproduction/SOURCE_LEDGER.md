# Kernel Reproduction Source Ledger

| Item | Pin / identifier | Role |
|---|---|---|
| `openai/ten-proofs` | `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6` | Audited repository revision |
| `NonSoficGroup.lean` | Git blob `dd1f8e63960300c8674fcd491007d2a628fbc6fe` | Published solution |
| `ComparatorChallenges/D_NonSoficGroup.lean` | Git blob `158d97224fbd51c203ff07a2f74041ffa2c6013b` | Trusted statement and local definitions |
| `ComparatorChallenges/D_NonSoficGroup.json` | Git blob `af023106a83552d7fafb4f0d122f121a095f802c` | Comparator theorem/axiom policy |
| Lean | `v4.32.0` | Primary elaborator/kernel toolchain |
| mathlib | `81a5d257c8e410db227a6665ed08f64fea08e997` | Imported library environment |
| Comparator | `07bc4ea40f2266dcb861820a2ec1fa3244ed307f` | Exact-statement, axiom, and kernel comparison |
| lean4export | `4e7915201d3f9f04470d9eae002fa695f7cdc589` | Environment export for Comparator |
| lean4checker | `b7398199245524275543dec6113229c9bb4902e5` | Comparator dependency |
| landrun | `811cfff51ceaf3d9843708aa6d22e9b84ccac8b4` | Sandbox used by Comparator |
| nanoda | `418320295890faed83a96fd97907b12a3b6728c2` | Independent Rust checker |

## Target theorem

```text
SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group
```

Trusted statement:

```lean
∃ (G : Type) (_ : Group G),
  Group.IsFinitelyPresented G ∧ ¬ SoficGroups.Sofic G
```

## Published Comparator policy

The challenge configuration targets only the theorem above, permits:

```text
propext
Quot.sound
Classical.choice
```

and sets `enable_nanoda` to `true`.

## Status

`SOURCE-PINNED`; clean independent execution still pending in this repository.
