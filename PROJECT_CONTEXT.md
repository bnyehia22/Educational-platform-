# TRUE — PROJECT CONTEXT

## Project
True — Arabic-first educational video platform.

## Repository
https://github.com/bnyehia22/Educational-platform-.git

## Current phase
Phase 00 — Foundation

## Current state
This repository contains the project specification, phase execution instructions, handoff rules, and repository scaffolding. The application implementation is to be created/continued by Claude starting with Phase 00.

## Core roles
- Student
- Teacher
- Admin

## Core business rules
- No subscriptions initially.
- Manual payments only: Wallet and InstaPay.
- Student may buy a full course.
- Teacher may optionally enable individual lesson purchases.
- Access becomes permanent only after admin approval.
- Payment proof is private.
- Course purchase unlocks its lessons logically through entitlements.
- One active device per student account.
- Videos are private and delivered through protected playback.

## Planned stack
- Next.js
- TypeScript
- Tailwind CSS
- PostgreSQL
- Prisma
- Secure authentication/session handling
- HLS/FFmpeg
- Object storage + CDN
- Optional Redis/BullMQ where justified

## Required implementation principles
- Server-side authorization is authoritative.
- Never expose storage credentials.
- Never commit secrets.
- Sensitive operations must be transactional and idempotent.
- Keep audit logs for important administrative actions.
- Use tests and verification after each phase.

## Handoff rule
At the end of every phase:
1. Verify the implementation.
2. Fix discovered issues.
3. Update this file with the actual state.
4. Create/update `PHASE_REPORT.md`.
5. Preserve all previous functionality.

## Next step
Implement Phase 00 according to `00-foundation.md`.
