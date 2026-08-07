# Formalization Track

**Status:** `OPEN`

This directory is reserved for local formal artifacts that are small enough to audit independently of the full published `NonSoficGroup.lean` development.

## Initial targets

1. **Claim-status kernel** — formalize the rule that a finite computational observation cannot be promoted to a universal theorem without an explicit certificate.
2. **Carrier-defect definitions** — once the mathematical definitions are locked, formalize finite-fragment permutation defect and basic monotonicity/well-formedness lemmas.
3. **Proposition 2.3 statement mirror** — encode the source statement without reproving it, to make hypothesis changes mechanically visible.
4. **Hypothesis-ablation test harness** — represent candidate weakened statements as separate conjectures rather than silently editing the established source theorem.

## Trust boundary

A Lean file can establish that a proposition follows from the definitions and imported theorems encoded in that file. It does not by itself establish that:

- the definitions match an informal paper;
- the imported theorem has the intended interpretation;
- a numerical experiment has been correctly connected to the theorem statement;
- a new formulation is mathematically novel.

Those checks remain explicit parts of the repository audit.

## Source independence

Do not copy large portions of the published OpenAI proof into this directory merely to create a second copy. The point of this track is to formalize **small local interfaces, definitions, and new claims** whose provenance and dependency graph can be inspected cheaply.
