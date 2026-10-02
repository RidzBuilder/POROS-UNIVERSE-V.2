# D2-C.12 — Schema Normalization & Machine-Readable Draft Package v0.1

**Status:** DRAFT / NOT LOCKED

## Normalized model
The package normalizes shared identifiers, timestamps, actors, scopes, typed references, provenance, integrity, and finding definitions across the nine D2-C schema families.

## Dependency order
authorization → environment → test → execution → evidence → verification → assessment → remediation → decision package.

## Independent status dimensions
- lifecycle status
- integrity status
- verification status
- assessment status

These dimensions must not be collapsed into a single status field.

## Anti-ambiguity rules
1. Unknown values are not silently coerced.
2. Missing required values fail validation.
3. Null is distinct from absent.
4. References require declared target type.
5. Scope mismatch fails validation.
6. Illegal lifecycle transitions fail validation.
7. Verification cannot be inferred from digest validity.
8. Assessment PASS cannot be inferred from verification.
9. Approval cannot be inferred from schema validity.
10. Lock cannot be inferred from implementation.

## Traceability
D2-C.13 supplies deterministic canonicalization vectors; D2-C.14 supplies conformance fixtures; D2-C.15 supplies compatibility/migration tests; D2-C.16 consolidates the review package.

## Deferred decisions
D2-4 identity model A/B/C remains DEFERRED pending evidence, approval, and Decision Ledger verification.
