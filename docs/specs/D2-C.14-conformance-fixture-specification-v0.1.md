# D2-C.14 — Conformance Fixture Specification & Validation Matrix v0.1

**Status:** DRAFT / NOT LOCKED

## Purpose
Provide deterministic fixtures covering valid, invalid, boundary, lifecycle, scope, integrity, and anti-status-elevation behavior.

## Fixture classes
| ID | Class | Expected |
|---|---|---|
| F-001 | minimal valid authorization | PASS |
| F-002 | missing required envelope field | FAIL |
| F-003 | invalid enum | FAIL |
| F-004 | scope mismatch | FAIL |
| F-005 | illegal lifecycle transition | FAIL |
| F-006 | digest mismatch | FAIL |
| F-007 | valid digest but unverified evidence | PASS schema / NOT VERIFIED |
| F-008 | verified evidence without assessment | PASS verification / NOT ASSESSED |
| F-009 | assessment PASS without authorization | FAIL semantic |
| F-010 | canonicalization V-001..V-004 | PASS |

## Validation matrix
Each fixture is evaluated independently against schema validity, semantic validity, lifecycle legality, scope integrity, canonicalization, and anti-status-elevation rules.

## Evidence discipline
Fixture evaluation results are test evidence only. They do not authorize production execution and do not select D2-4.

## Required artifact fields
Each fixture records fixture_id, schema_id, input, expected_outcome, expected_error_class when applicable, and rationale.
