# FA–NSOF–KERNEL–REPRO–001 — Reproduction Protocol

## 1. Audit question

Does the released Lean solution at the pinned OpenAI revision prove the exact trusted statement

```lean
∃ (G : Type) (_ : Group G),
  Group.IsFinitelyPresented G ∧ ¬ SoficGroups.Sofic G
```

using no axioms beyond `propext`, `Quot.sound`, and `Classical.choice`, with acceptance by Lean's kernel and an independent nanoda replay?

## 2. Source lock

- Repository: `openai/ten-proofs`
- Commit: `94bc0feb6a9ff12c7d31d6de640a725c9d43d2b6`
- Solution: `NonSoficGroup.lean`
- Solution Git blob: `dd1f8e63960300c8674fcd491007d2a628fbc6fe`
- Trusted challenge: `ComparatorChallenges/D_NonSoficGroup.lean`
- Trusted challenge Git blob: `158d97224fbd51c203ff07a2f74041ffa2c6013b`
- Comparator config: `ComparatorChallenges/D_NonSoficGroup.json`
- Comparator config Git blob: `af023106a83552d7fafb4f0d122f121a095f802c`

## 3. Dependency lock

From the pinned project manifest/toolchain:

- Lean: `v4.32.0`
- mathlib: `81a5d257c8e410db227a6665ed08f64fea08e997`
- Comparator: `07bc4ea40f2266dcb861820a2ec1fa3244ed307f`
- lean4export: `4e7915201d3f9f04470d9eae002fa695f7cdc589`
- lean4checker: `b7398199245524275543dec6113229c9bb4902e5`

External checker/sandbox pins used by this audit:

- landrun: `811cfff51ceaf3d9843708aa6d22e9b84ccac8b4`
- nanoda: `418320295890faed83a96fd97907b12a3b6728c2`

## 4. Required checks

### 4.1 Static source scan

Record whether the published solution text contains literal proof placeholders or explicit local axiom declarations. Static scanning is useful evidence but is not a proof check.

### 4.2 Ordinary Lean build

Run:

```sh
lake exe cache get
lake build NonSoficGroup
```

A successful exit code establishes Lean acceptance under the pinned toolchain and dependencies.

### 4.3 Target theorem and axiom query

Create a small trusted query module importing `NonSoficGroup` and run:

```lean
#print SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group
#print axioms SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group
```

Retain the complete output.

### 4.4 Comparator certification

The published challenge configuration targets exactly:

```text
SoficGroups.SourceTopLevelCompressionFinal.exists_finitelyPresented_nonsofic_group
```

and permits only:

```text
propext
Quot.sound
Classical.choice
```

with `enable_nanoda: true`.

Comparator must run in a fresh environment in which the potentially adversarial solution has not previously been built. The comparator documentation also recommends a `systemd-run` wrapper around the checker to harden the landrun threat model. If that wrapper is unavailable, record the deviation explicitly rather than silently calling the run fully hardened.

### 4.5 Independent nanoda replay

`nanoda_bin` must be built from the pinned source revision and available to Comparator. The run is valid only if nanoda succeeds with the challenge configuration's independent-kernel check enabled.

## 5. Clean-room discipline

The ordinary Lean build and Comparator audit should use separate fresh jobs/VMs. Do not precompile `NonSoficGroup.lean` in the Comparator job before Comparator handles the solution.

The trusted base includes the challenge module, its transitive imports, the project configuration, the pinned toolchain, and the checking software. The audit should therefore preserve exact hashes and versions for each.

## 6. Required evidence

A complete record contains:

- exact source commit;
- clean `git status` before execution;
- SHA-256 hashes of load-bearing files;
- OS, kernel, and architecture;
- Lean and Lake versions;
- ordinary build exit code and full log;
- printed target theorem;
- printed axiom dependencies;
- nanoda result;
- Comparator exit code and full log;
- whether the recommended `systemd-run` hardening wrapper was used;
- workflow/run URL or signed local execution statement;
- timestamp and auditor identity or pseudonym.

## 7. Pass criteria

Mark the full kernel reproduction **PASS** only if all declared criteria are met:

- source checkout equals the pinned commit;
- working tree is clean before execution;
- `lake build NonSoficGroup` exits 0 in the ordinary-build environment;
- target theorem/axiom query exits 0;
- Comparator succeeds on `D_NonSoficGroup.json` in a fresh environment;
- nanoda succeeds through the enabled Comparator check;
- the reported axiom dependencies are within the declared whitelist;
- complete logs are retained;
- any sandbox-hardening deviation is clearly recorded.

A failure of reproduction is not automatically a refutation of the mathematics. Possible causes include dependency or platform breakage, insufficient resources, sandbox incompatibility, or a genuine formal defect.

## 8. What a PASS establishes

A PASS establishes that, under the pinned formal definitions and dependency graph, the exact target proposition is accepted by the declared formal-checking stack and that the proof-term dependency stays within the configured foundational axiom whitelist.

## 9. What a PASS does not establish

It does not by itself prove:

- that the formal definition of `Sofic` matches every convention in the literature without further inspection;
- that the manuscript and Lean development correspond line by line;
- that every imported mathematical theorem has the intended informal interpretation;
- that Proposition 2.3's prose proof has received an independent human re-proof;
- that the kernel, independent checker, compiler, operating system, hardware, or sandbox are logically infallible.

Those are separate semantic, mathematical, and trusted-computing-base audits.
