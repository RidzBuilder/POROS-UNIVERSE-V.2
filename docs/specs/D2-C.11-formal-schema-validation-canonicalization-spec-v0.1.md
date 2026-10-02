# D2-C.11 — Formal Schema Validation & Canonicalization Specification v0.1

**Status:** DRAFT / NOT LOCKED  
**Authority:** POROS UNIVERSE V.2 working specification  
**Decision dependency:** D2-4 identity model remains DEFERRED

## Scope
Defines the formal validation and canonicalization contract for nine POROS identity-experiment record families:
1. authorization
2. environment
3. test
4. execution
5. evidence record
6. verification
7. assessment
8. remediation action
9. decision package

## Common envelope
Each record uses: `schema_id`, `schema_version`, `record_id`, `record_type`, `created_at`, `created_by`, `scope`, `payload`, `provenance`, and `integrity`.

## Validation layers
1. JSON/schema shape
2. required-field and nullability checks
3. enum/domain constraints
4. cross-record reference checks
5. lifecycle transition checks
6. tenant/scope isolation checks
7. integrity/digest checks
8. semantic anti-status-elevation checks

## Canonicalization
The proposed canonical JSON profile is **POROS-CJ-0.1**, using deterministic UTF-8 JSON serialization and SHA-256 integrity digests. Exact byte-level vectors are defined by D2-C.13.

## Status discipline
Schema-valid does not imply authorized, executed, verified, assessed PASS, approved, or locked. A valid digest does not establish evidence truth.

## Open items
Exact canonical byte vectors, registry authority, risk methodology, and D2-4 identity-model selection remain open or deferred.
