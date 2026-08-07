# Claim Status Vocabulary

This repository separates mathematical truth status from implementation status and review status. A polished artifact does not receive a stronger mathematical label merely because it is executable, formalized, repeated, or widely discussed.

## Primary mathematical statuses

### `ESTABLISHED`
A result already proved in the cited mathematical literature or in a cited formal development. The exact source must be named.

### `REPRODUCED`
An established formal or computational result has been independently rerun under a documented environment and met a declared reproduction protocol. This label must name what was reproduced; it does not automatically imply a complete semantic or line-by-line human proof audit.

### `VERIFIED-BY:<procedure>`
A named verification procedure succeeded. Examples: `VERIFIED-BY:Lean`, `VERIFIED-BY:Comparator`, `VERIFIED-BY:nanoda`. Different procedures are tracked separately.

### `CONDITIONAL`
A theorem or deduction is valid assuming explicitly listed hypotheses or imported results. The hypotheses are part of the claim.

### `COMPUTATIONAL-OBSERVATION`
A finite computation, numerical optimization, search, or experiment produced the stated result. It must include parameters, code/version information, and enough information to rerun the observation.

### `PROPOSAL`
A new definition, reformulation, proof architecture, invariant, experiment, or conjectural bridge introduced by this repository. A proposal is not evidence that the proposed theorem is true.

### `OPEN`
The repository does not presently have a proof or refutation. Known partial results should be listed without changing this status.

### `OBSTRUCTED`
A declared route cannot currently be completed because a specific hypothesis, lemma, carrier, compatibility condition, or certificate is missing. `OBSTRUCTED` does not mean impossible unless a no-go theorem is supplied.

### `REFUTED`
A precise claim has been defeated by a proof, counterexample, failed formal check that targets the exact claim, or another decisive falsifier. The refuting evidence must be linked.

## Review modifiers

These may be appended without changing the primary mathematical status:

- `SOURCE-PINNED`
- `LEAN-CHECKED`
- `NANODA-CHECKED`
- `COMPARATOR-CHECKED`
- `HUMAN-REVIEWED`
- `INDEPENDENTLY-REUSED`
- `NEEDS-SEMANTIC-AUDIT`
- `NEEDS-NOVELTY-AUDIT`

## Non-promotion rules

The following transitions are forbidden without a new certificate:

```text
COMPUTATIONAL-OBSERVATION -> ESTABLISHED
PROPOSAL                  -> ESTABLISHED
LEAN-CHECKED               -> paper/Lean semantic equivalence
REPRODUCED                 -> independent mathematical re-proof
many supporting artifacts  -> universal theorem
```

A finite search may motivate a universal lower-bound conjecture, but it cannot prove the universal quantifier by accumulation alone.

## Minimum claim card

Every exported research claim should make the following inspectable:

```text
Claim:
Status:
Object/domain:
Hypotheses:
Carrier or proof artifact:
Source/provenance:
Version/hash:
Validation procedure:
Known dependencies:
Known limitations:
Falsifier or correction condition:
```

The purpose is simple: a reader should be able to tell exactly what is being claimed, what supports it, and what would change its status.
