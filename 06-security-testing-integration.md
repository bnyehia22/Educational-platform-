# TRUE — Claude Development Phase

**Product:** True  
**Repository:** https://github.com/bnyehia22/Educational-platform-.git  
**Workflow:** Sequential development on ONE repository  
**Language:** Arabic-first / RTL  
**Important:** This phase must continue the existing repository. Do not create a separate project.

## Universal execution contract

1. Read `PROJECT_CONTEXT.md` before coding.
2. Inspect the existing repository before changing anything.
3. Implement the phase completely; do not only describe or plan it.
4. Preserve all working functionality from previous phases.
5. Do not replace real business logic with fake/demo behavior.
6. Keep authorization and security server-side.
7. Add/update tests for the functionality you touch.
8. Run all verification that the current environment allows.
9. Fix errors you discover before finishing.
10. Update `PROJECT_CONTEXT.md`.
11. Create/update `PHASE_REPORT.md`.
12. Do not commit or expose secrets, API keys, passwords, `.env`, or cloud credentials.
13. If an external service cannot be tested, document the exact limitation instead of claiming success.
14. Do not ask unnecessary questions. Make reasonable engineering decisions from this phase and the existing project.
15. Do not stop because the phase is large; work through its acceptance criteria in priority order.

## True product identity

The platform brand is **True**.

Build a coherent commercial identity around the name True:
- clean, trustworthy, modern educational technology
- Arabic-first RTL experience
- professional rather than childish
- strong visual hierarchy
- consistent typography, spacing, buttons, forms, cards, tables, states, and navigation
- accessible contrast and responsive mobile behavior
- avoid generic template-looking pages
- centralize design tokens/theme so the visual identity can evolve without rewriting the application

Do not invent a complicated logo system or unrelated branding. Establish a clean product identity that can be refined later.

# PHASE 06 — FINAL INTEGRATION / SECURITY / QA / PRODUCTION

## Objective
Act as the senior engineer taking ownership of the entire True repository.

Do not merely report problems. Fix them.

## Read first
- PROJECT_CONTEXT.md
- all phase reports
- full source tree
- Prisma schema and migrations
- tests
- environment templates
- README

## Integration audit
Verify the complete flow:

Teacher
→ creates course
→ creates sections/lessons
→ uploads video
→ video processing
→ HLS READY

Student
→ registers/logs in
→ browses course
→ creates purchase
→ submits Wallet or InstaPay proof

Admin
→ reviews proof
→ approves

System
→ marks order paid
→ creates entitlement
→ notifies student

Student
→ authorized device
→ protected playback
→ progress/resume

Different device
→ playback denied

Admin
→ approves device reset
→ next device can register through intended flow

## Security audit
Verify and fix:
- password hashing
- secure sessions
- CSRF where applicable
- rate limiting/brute-force protection
- input validation
- server-side authorization
- secure headers
- upload limits/types
- private payment proofs
- private video originals
- storage credential isolation
- secret leakage
- teacher isolation
- student isolation
- transaction safety
- payment idempotency
- safe object paths/names
- audit logs

## Test suite
Run/fix:
- unit tests
- integration tests
- auth/RBAC tests
- course ownership tests
- storage/provider tests
- upload tests
- payment tests
- entitlement tests
- device-binding tests
- playback authorization tests
- progress tests
- critical end-to-end tests

## Build
Run all available:
- typecheck
- lint
- tests
- Prisma validation
- migrations
- production build

Fix errors.

## Production readiness
Check:
- environment variables
- error handling
- logging
- database indexes
- secure defaults
- deployment documentation
- backup considerations
- storage configuration
- video processing configuration
- seed/dev data separation

## Final invariants
1. No approval → no paid entitlement.
2. No entitlement → no protected content.
3. Invalid device → no protected playback.
4. Second device → blocked.
5. Payment approval is idempotent.
6. Payment proofs are private.
7. Original videos are private.
8. Client input never decides authorization.
9. Teacher data is isolated.
10. Secrets are not committed.
11. Storage credentials never reach browser.
12. Course and lesson access rules are enforced server-side.
13. Critical workflows have automated tests.
14. No claim of DRM/absolute anti-recording without real DRM.

## Final report
Create `FINAL_INTEGRATION_REPORT.md` containing:
- implemented modules
- tests executed and results
- build result
- external services actually verified
- genuine limitations
- exact deployment/run commands

Do not claim an external service was tested if credentials/network/service access was unavailable.
