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

# PHASE 03 — COMMERCE / WALLET / INSTAPAY

## Objective
Implement manual payment and order workflows. There are NO recurring subscriptions and NO automated payment gateway in this phase.

## Purchases
Support:
1. Full course purchase
2. Individual lesson purchase when enabled by teacher

## Order model
Implement:
- unique order ID
- order items
- historical price snapshots
- total amount
- order status
- user relation
- content relation

## Payment method 1 — Wallet
Student sees:
- amount due
- sender wallet number
- receiver wallet number
- upload transfer screenshot
- submit button

Store:
- method = WALLET
- sender wallet number
- receiver wallet number
- proof
- amount
- order
- user
- status

## Payment method 2 — InstaPay
Student sees:
- amount due
- sender InstaPay username (`@username`)
- upload screenshot from InstaPay transfer
- submit button

Store:
- method = INSTAPAY
- sender username
- proof
- amount
- order
- user
- status

## Payment states
- PENDING
- APPROVED
- REJECTED

No payment request grants access automatically.

## Admin review
Admin must see:
- student
- content
- amount
- method
- sender wallet / receiver wallet OR InstaPay username
- proof screenshot
- current status
- rejection reason

Actions:
- approve
- reject
- enter rejection reason

## Approval transaction
On approval:
1. mark order paid
2. create entitlement
3. notify student
4. create audit log

Approval must be idempotent.
Duplicate approval must never create duplicate entitlements.

## Proof security
Payment proofs are private files.
Do not expose public permanent URLs.
Treat uploads as untrusted.

## Payment settings
Admin can configure destination wallet and InstaPay information.
Do not hard-code them.

## Acceptance criteria
- Wallet flow works
- InstaPay flow works
- required fields validated
- proof uploaded privately
- admin approval/rejection works
- rejection reason works
- duplicate approval prevented
- entitlements are only created after approval
- tests cover critical payment paths

## Handoff
Update `PROJECT_CONTEXT.md` and `PHASE_REPORT.md`.
