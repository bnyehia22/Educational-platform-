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

# PHASE 00 — FOUNDATION

## Objective
Create the production foundation for True from scratch while keeping the architecture ready for all later phases.

## Stack
Use the project's declared stack. If starting from an empty repository, prefer:
- Next.js + TypeScript
- PostgreSQL
- Prisma
- Tailwind CSS
- secure authentication/session approach
- Zod or equivalent validation
- modular monolith
- Docker configuration where useful

Do not introduce microservices unless a concrete requirement makes them necessary.

## Implement

### Repository
- initialize the application
- sensible folder structure
- scripts for dev/build/test/typecheck/lint
- `.env.example`
- README with setup instructions
- safe configuration validation

### Database
Create the schema foundation for:
- users
- roles / role assignments
- teacher_profiles
- student_profiles
- categories
- courses
- course_sections
- lessons
- videos
- video_assets
- storage_providers
- orders
- order_items
- payment_requests
- payment_proofs
- entitlements
- progress
- devices
- device_reset_requests
- notifications
- payment_settings
- audit_logs

Use:
- proper foreign keys
- unique constraints
- indexes
- timestamps
- explicit enums/statuses
- appropriate cascade/restrict behavior

Do not implement later workflows as fake placeholders.

### Authentication and RBAC
Implement:
- registration
- login
- logout
- secure password hashing
- secure session handling
- STUDENT / TEACHER / ADMIN roles
- server-side authorization helpers
- protected routes/pages/actions

Teacher data must be isolated.
Student private data must be isolated.
Admin-only operations must be server-protected.

### True UI foundation
Create:
- RTL layout
- responsive shell
- typography
- navigation foundation
- buttons
- forms
- cards
- tables
- alerts
- loading states
- empty states
- error states

## Acceptance criteria
- app starts
- database migration works
- authentication works
- RBAC works server-side
- protected routes work
- base True identity exists
- typecheck/lint/tests/build are run where available
- no secrets committed

## Handoff
Update `PROJECT_CONTEXT.md` with the actual stack, schema decisions, commands, and known limitations.
Create `PHASE_REPORT.md`.
