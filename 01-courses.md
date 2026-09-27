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

# PHASE 01 — COURSES / CURRICULUM / TEACHER

## Objective
Build the complete course-authoring workflow on top of the existing foundation.

## Implement

### Teacher
- teacher dashboard
- course list
- create course
- edit course
- draft/published/archived states
- course price
- category
- thumbnail/metadata
- optional individual lesson purchasing
- sections
- lessons
- lesson ordering
- section ordering
- lesson metadata
- publish validation

### Student-facing catalog
- published course listing
- course details
- curriculum preview
- pricing
- locked/unlocked visual states where access logic is not yet available

### Authorization
- teacher can only manage own courses
- teacher cannot modify another teacher's course
- student cannot mutate course data
- admin can manage according to role rules

### Data integrity
Preserve price values in a way that later orders can snapshot the historical price.
Do not build fake payment completion.

## Acceptance criteria
- teacher can create a complete course
- sections and lessons can be created and reordered
- course can be drafted/published
- unpublished course is not publicly accessible as a normal published course
- teacher isolation is enforced server-side
- student catalog reads real database data
- tests cover CRUD and authorization

## Handoff
Update `PROJECT_CONTEXT.md` and `PHASE_REPORT.md`.
