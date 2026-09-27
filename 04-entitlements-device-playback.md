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

# PHASE 04 — ENTITLEMENTS / ONE DEVICE / PROTECTED PLAYBACK

## Objective
Turn approved purchases into real access and enforce one-device playback.

## Entitlements
Implement:
- COURSE entitlement
- LESSON entitlement
- ACTIVE / REVOKED
- permanent access with `expires_at = NULL`

Rules:
- course entitlement logically unlocks all lessons in that course
- lesson entitlement unlocks only that lesson
- no entitlement means no protected content

Do not create unnecessary duplicate lesson entitlements for every course purchase.

## One-device account binding
Each account may have ONE active registered device.

Use:
- server-side device record
- persistent installation/device identifier
- secure device token
- session binding
- platform metadata

Do NOT rely only on IP address or user-agent.

First authorized protected-content activation/playback:
→ register the current device if the account has no active device.

Same device:
→ allowed.

Different device:
→ protected playback denied.

Use Arabic message equivalent to:
"هذا الحساب مرتبط بجهاز آخر. لا يمكن تشغيل المحتوى من هذا الجهاز."

## Device reset
Student can submit a reset request.

Admin can:
- review
- approve
- reject
- enter note/reason

Approved reset:
- revoke old device
- allow controlled registration of the next authorized device

Log:
- requester
- old device
- reviewer
- timestamps
- reason/note
- result

## Protected playback
Before issuing playback authorization verify:
1. authenticated user
2. valid active device
3. active entitlement
4. lesson/course relationship
5. video status READY

Then issue short-lived playback authorization/token as appropriate.

Never expose storage credentials.
Never expose permanent original-video URLs.

## Progress
Implement:
- current position
- completion/progress
- resume playback
- lesson navigation

## Acceptance criteria
- approved course purchase plays
- unpaid course does not play
- lesson-only purchase is scoped
- same device works
- second device is blocked
- reset flow works
- progress/resume works
- all authorization combinations have tests

## Important limitation
Do not claim absolute prevention of screen recording unless real DRM is implemented.
