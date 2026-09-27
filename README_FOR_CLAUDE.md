# TRUE — CLAUDE BUILD PACK

This folder contains the phase instructions for building True across multiple Claude sessions/accounts with limited context.

## Repository
https://github.com/bnyehia22/Educational-platform-.git

## How to use

Upload the phase file needed for the current session together with the current repository and `PROJECT_CONTEXT.md`.

Run phases strictly in this order:

1. `00-foundation.md`
2. `01-courses.md`
3. `02-video-storage.md`
4. `03-commerce-payments.md`
5. `04-entitlements-device-playback.md`
6. `05-dashboards-admin.md`
7. `06-security-testing-integration.md`

## Important

This is ONE project, not seven projects.

Every session must:
- inspect the existing repository
- continue from the current code
- preserve working functionality
- implement its phase
- test
- update `PROJECT_CONTEXT.md`
- create/update `PHASE_REPORT.md`

## If using GitHub

The repository URL is currently configured as:

`https://github.com/bnyehia22/Educational-platform-.git`

Replace `https://github.com/bnyehia22/Educational-platform-.git` with the actual URL before giving the files to Claude if you want the URL embedded in prompts.

## If using ZIP

Move the complete repository between sessions, excluding:
- node_modules
- .next
- build artifacts
- .env
- credentials/secrets

Keep:
- source code
- Prisma migrations
- tests
- package manifests/lockfile
- `.env.example`
- PROJECT_CONTEXT.md
- PHASE_REPORT.md
