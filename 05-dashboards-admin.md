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

# PHASE 05 — STUDENT / TEACHER / ADMIN EXPERIENCE

## Objective
Complete the commercial True experience using real backend data from previous phases.

## Student Dashboard
Implement:
- overview
- continue learning
- purchased courses
- purchased lessons
- progress
- orders/payment requests
- notifications
- device status
- device reset request
- profile/settings

## Course/player experience
- protected video player
- sections/lessons
- locked/unlocked state
- previous/next
- resume
- clear access errors
- responsive mobile player experience

## Teacher Dashboard
Implement:
- overview metrics
- courses
- curriculum builder
- video manager
- student activity limited to teacher's own content
- orders/payment activity limited to own content
- profile/settings

Do not expose other teachers' data.

## Admin Dashboard
Implement:
- overview
- users
- teachers
- students
- courses
- lessons
- payment requests
- payment proofs
- orders
- device management
- device reset requests
- storage providers
- payment settings
- audit logs
- system settings

## UX
- Arabic-first RTL
- mobile-first
- accessible
- professional True identity
- consistent design system
- loading/error/empty/success states
- confirmations for destructive actions

No static mock dashboards.
Connect screens to real APIs/server actions/database.

## Acceptance criteria
All three roles can perform their intended workflows from the UI.
Authorization is enforced on the server, not just by hiding UI elements.
