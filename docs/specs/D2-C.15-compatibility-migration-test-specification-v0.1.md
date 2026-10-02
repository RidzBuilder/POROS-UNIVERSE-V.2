# D2-C.15 — Compatibility & Migration Test Specification v0.1

**Status:** DRAFT / NOT LOCKED

## Compatibility policy
Schema evolution MUST be explicit. A version change requires a declared compatibility class:
- compatible additive change;
- constrained compatible change;
- breaking change.

Unknown fields MUST NOT silently alter semantics. Removed or renamed fields require an explicit migration mapping.

## Migration invariants
1. record identity remains stable unless explicitly versioned;
2. tenant/scope boundaries remain unchanged;
3. semantic status is preserved;
4. provenance is preserved;
5. integrity is recomputed after migration;
6. canonicalization profile is declared;
7. migration does not manufacture verification, assessment, approval, or lock status.

## Test classes
- round-trip old → new → canonical
- semantic equivalence
- prohibited-field removal
- enum migration
- timestamp normalization
- scope preservation
- reference integrity
- digest invalidation/recomputation
- rollback/idempotence

## Pass criteria
A migration passes only when declared invariants hold and no forbidden status elevation occurs. Migration success is not semantic equivalence until semantic tests pass.

## Deferred scope
No migration is authorized against production records. D2-4 remains DEFERRED.
