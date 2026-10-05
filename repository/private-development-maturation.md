# Private Development & Maturation

**Phase:** ACTIVE  
**Audience:** Private/internal POROS development  
**Publication status:** NOT PUBLIC-RELEASE READY  
**Independent review:** DEFERRED UNTIL MATURITY / PUBLICATION READINESS  
**Governor decision:** DEFERRED  
**D2-4 identity model:** DEFERRED

## Objective

Mature POROS UNIVERSE V.2 through implementation, integration, internal validation, functional testing, and iterative refinement before entering publication-readiness review.

## Ordered workflow

1. Mature D2-C specifications and contracts.
2. Implement required POROS components.
3. Integrate components without crossing Core governance boundaries.
4. Run internal schema/canonicalization/fixture/lifecycle validation.
5. Run functional and end-to-end tests using non-production/private context.
6. Record failures, gaps, and remediation.
7. Validate outputs against the user's required outcomes.
8. Repeat refinement until functional maturity criteria are satisfied.
9. Prepare a publication-readiness candidate.
10. Only then activate D2-D independent review.

## Status discipline

Internal testing is not independent review. A passing test is not governance approval. Functional maturity is not public-release approval. Publication readiness is not a Governor decision.

## Safety boundaries

- No production execution without explicit authorization.
- No production credentials.
- No unsupported claims of evidence verification.
- No implicit selection of identity model A/B/C.
- No baseline lock before the applicable governance gate.

## Maturity exit criteria

The project may move to publication-readiness assessment only when:
- core workflows execute deterministically in the intended private context;
- expected outputs are reproducible;
- known gaps are documented and either remediated or explicitly accepted;
- test evidence is traceable;
- governance boundaries remain intact;
- release scope is explicitly defined.

This file is a development control artifact, not a claim that these criteria have already been met.
