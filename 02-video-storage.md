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

# PHASE 02 — MULTI-STORAGE VIDEO / UPLOAD / HLS

## Objective
Build True's real video infrastructure. Teachers must upload from the True dashboard; they must never need to open Cloudflare or another storage provider.

## Core architecture

Course
→ Storage Provider
→ Storage Account/Bucket
→ Video Assets

A different course may use a different storage account/provider.

Examples:
- Course A → Cloudflare R2 Account A → Bucket A
- Course B → Cloudflare R2 Account B → Bucket B
- Course C → Backblaze B2
- Course D → another S3-compatible provider

## Storage abstraction
Implement a provider interface/adapter.

Minimum provider types:
- CLOUDFLARE_R2
- S3_COMPATIBLE
- BACKBLAZE_B2 (adapter boundary if full live support is not possible in this environment)

Do NOT hard-code one global bucket.

A course references a storage provider configuration. Secrets belong to secure server-side configuration, not browser code.

## Teacher upload
Flow:

Teacher Dashboard
→ Course
→ Section
→ Lesson
→ Upload Video
→ server authorization
→ direct/multipart/resumable upload
→ processing
→ HLS READY

Implement where practical:
- upload progress
- large file support
- retry/cancel
- upload status
- processing status

The application server should not proxy the entire large video through memory unless unavoidable.

## Video states
- UPLOADING
- PROCESSING
- READY
- FAILED
- ARCHIVED

## Processing
Use FFmpeg or a real processing adapter.
Generate HLS renditions such as:
- 360p
- 480p
- 720p
- optional 1080p

Original uploads remain private.

Never expose permanent public original-video URLs.

## Security
- storage credentials never reach browser
- teacher cannot choose an unauthorized provider
- provider resolution is server-side
- uploaded files are treated as untrusted
- validate type/size
- private buckets/objects
- safe object naming
- no secrets in source control

## Playback foundation
Create the server-side authorization boundary for later protected playback.
Do not grant playback merely because a client knows an asset ID.

## Acceptance criteria
- teacher uploads from True UI
- course-specific provider is resolved server-side
- multiple storage accounts/providers are architecturally supported
- video records and processing states work
- HLS pipeline/adapter is implemented
- originals are private
- tests cover provider/course/teacher isolation

## Handoff
Update `PROJECT_CONTEXT.md` and `PHASE_REPORT.md`, including what external video infrastructure was actually tested.
