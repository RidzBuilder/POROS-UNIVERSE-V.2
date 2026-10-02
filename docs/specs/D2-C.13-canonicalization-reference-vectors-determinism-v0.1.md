# D2-C.13 — Canonicalization Reference Vectors & Determinism Specification v0.1

**Status:** DRAFT / NOT LOCKED  
**Profile:** POROS-CJ-0.1  
**Digest:** SHA-256

## Determinism contract
For a given valid record, canonicalization MUST produce identical UTF-8 bytes across conforming implementations. Canonical output MUST:
- encode UTF-8;
- use JSON objects with lexicographically sorted member names;
- preserve array order;
- omit no semantically present fields;
- represent booleans and null using JSON primitives;
- use compact separators with no insignificant whitespace;
- use deterministic escaping;
- reject non-finite numbers;
- normalize no semantic values beyond the declared schema.

The canonical byte stream is hashed with SHA-256 and encoded as lowercase hexadecimal.

## Reference vectors
### V-001 — scalar/object ordering
Input object member order is intentionally non-canonical:
`{"b":2,"a":1,"active":true,"note":null}`

Expected canonical JSON:
`{"a":1,"active":true,"b":2,"note":null}`

### V-002 — nested ordering
Input:
`{"z":{"b":2,"a":1},"a":[{"d":4,"c":3},1]}`

Expected canonical JSON:
`{"a":[{"c":3,"d":4},1],"z":{"a":1,"b":2}}`

### V-003 — array order preservation
Input:
`{"items":["b","a",{"y":2,"x":1}]}`

Expected canonical JSON:
`{"items":["b","a",{"x":1,"y":2}]}`
Array element order MUST remain b,a,...

### V-004 — insignificant whitespace
Inputs `{"a":1,"b":[true,null]}` and a whitespace-expanded equivalent MUST yield identical canonical bytes and identical SHA-256 digest.

## Rejection vectors
- NaN / Infinity / -Infinity
- duplicate object keys before parsing
- invalid UTF-8
- schema-invalid record
- unsupported canonicalization profile
- ambiguous numeric representation outside the schema contract

## Conformance rule
A conforming implementation passes only if all positive vectors canonicalize identically and all rejection vectors are rejected. This specification does not itself constitute execution evidence.
