# TwinCercle — Ultra Super MVP Engineering Handoff

**Purpose:** Give the next coding agent/developer an exact, continuity-safe handoff for the supplied frontend prototype and the current TwinCercle product constitution.

## 1. Mandatory reading order

1. Read the complete repository-root `CONTEXT.md` (the full supplied Master Context, not a shortened recap).
2. Read `README.md` for package contents and demo boundaries.
3. Read `docs/PHASE_STATE.md` for verified work and remaining blockers.
4. Inspect the current repository, package manifests, lockfiles, deployment configuration, tests and git diff before implementing production features.

Do not overwrite, abbreviate or silently reinterpret the full `CONTEXT.md`. When a decision is unresolved, preserve it as unresolved and ask the founder only when it blocks the next implementation step.

## 2. Controlling product decisions

- Product name: **TwinCercle**.
- Canonical domain: `twincercle.com`.
- Product direction: **Unified Digital Ecosystem**.
- MVP strategy: **Balanced**.
- One identity connects enabled modules.
- Marketplace and Local Services are first-class TwinCercle modules; Ekota is not a separate brand, product or website.
- Buyer–seller and customer–provider contact must open native TwinCercle Connect conversations. Do not silently redirect to WhatsApp.
- Marketplace is a discovery/listing/communication layer at launch. TwinCercle does not own stock, become seller of record, deliver products, hold buyer funds, provide escrow or guarantee transactions under the current model.
- Delivery is estimated and confirmed by the parties directly.
- Verification badges must explain the precise check and must not be described as guarantees.
- `username@twincercle.com` is an internal namespace, not conventional SMTP email unless SMTP interoperability is separately implemented.
- Web3 wallet connection is optional. Never request or store seed phrases/private keys.
- Describe the architecture as hybrid unless implementation evidence justifies another claim.

## 3. What this package implements

The root `index.html` is a standalone, responsive frontend prototype with a local demo-state adapter.

| Module | UI/interaction baseline | Persistence in this package |
|---|---|---|
| Overview | Unified home, stats, quick actions, discovery highlights | Browser-local state |
| Discover | Search sample people, products and services | Sample data + local drafts |
| Connect | 1:1 demo conversations, request accept/decline, send local text, mute/block/report | `localStorage` only |
| Marketplace | Categories, search, selected location, listing details, save, report, message seller, create listing draft | `localStorage` only |
| Local Services | Categories, search, selected area, provider details, report, message provider, create service draft | `localStorage` only |
| Business & Trust | Seller and provider draft profiles, product/service draft inventory, verification explainer | `localStorage` only |
| Identity | Profile/handle editor and local preferences | `localStorage` only |
| Notifications | Sample activity and preference toggles | `localStorage` only |
| Security | Passkey/recovery/device architecture explainer | No security operation is performed |
| Operations | Verification/moderation example queue and local reports | Demo-only; no authorization or admin API |
| Mail, Communities, Wallet & Web3 | Staged product previews | Not implemented |

All people, businesses, provider profiles, product data, prices, locations, ratings/status cues and schedules in the sample content are illustrative. The UI labels the prototype boundary and repeats it at sensitive transitions.

## 4. What must not be claimed

Do not describe this package as having any of the following:

- Production authentication, Google OAuth, passkey enrollment, WebAuthn, sessions or real account recovery.
- Real message delivery, XMTP/Waku/MLS integration, E2EE, secure multi-device key synchronization or encrypted attachments.
- Server-side database persistence, API authentication/authorization, owner checks, rate limits, real-time updates or audit logging.
- Actual identity/KYC/business/face/liveness verification or public verification badges.
- Production moderation, support workflows, privileged admin access or appeals.
- Real SMTP, an interoperable `@twincercle.com` mailbox, communities, wallet connection, on-chain identity, payment, escrow, subscriptions, commissions or payouts.
- Guaranteed product quality, seller integrity, provider competence, delivery time, financial returns or income.

The prototype stores message text in this browser's `localStorage`. This is only demo behavior; it is not a secure messaging storage design. Never enter sensitive information in it.

## 5. Frontend behavior and conventions

- `index.html` owns app markup, style tokens, screen templates, sample data and event handlers.
- `assets/twincercle-mark.svg` is the logo/fav icon asset extracted from the supplied reference HTML.
- State key: `twincercle-ultra-mvp-v1` in browser `localStorage`.
- `Security → Reset demo` resets the local prototype state.
- Desktop: persistent left navigation; mobile: five-item bottom navigation plus the More sheet.
- Primary mobile breakpoint: 700px; narrow-screen refinements: 380px.
- Dark/light theme is local state.
- Forms validate on the client for demo usability; this is not a substitute for server-side validation.
- New products/services are draft-only and appear in the user's Business & Trust workspace, not in public discovery.
- Native seller/provider chat uses the listing/provider context in the conversation header.
- Location filters use selected sample city labels; no GPS, map SDK or true radius computation is performed.

Do not introduce a frontend dependency or framework migration as a side effect of a small UI task. The production frontend framework remains a founder decision until the repository audit and ADR.

## 6. Mobile and accessibility requirements for future edits

- Mobile-first at 320px, 360px, 390px and 430px widths; tablet and desktop must also be checked.
- No horizontal page overflow.
- Search and location/category filters must be usable without tiny tap targets.
- Bottom navigation must not cover scrollable content or modal actions; respect safe-area insets.
- Conversation list and conversation detail should switch cleanly on mobile.
- Dialogs should become bottom sheets on narrow screens and stay within dynamic viewport height.
- Visible focus states, labels, accessible icon names, keyboard/Enter/Escape support and reduced-motion preferences must be preserved.
- Maintain readable contrast in both themes.
- Do not load map SDKs on the initial route; maps are lazy enhancement after provider selection.

## 7. Next engineering sequence

### Gate A — repository audit (must precede production framework decisions)

- Inspect root tree, package scripts, lockfile, current branch and deployment config.
- Identify whether the actual repository uses Vite/React, Next.js or a different setup.
- Record existing tests, build commands, environment variable requirements and hosting.
- Compare the actual repository with this standalone prototype.
- Create/update `docs/DECISIONS.md` and `docs/PHASE_STATE.md` with factual results.

### Gate B — identity and account foundation

- Confirm auth provider and passkey/WebAuthn configuration.
- Specify username normalization, reserved names, conflict/recovery and enumeration protections.
- Implement profile ownership, session inventory, revocation and safe account deletion.
- Design two independent recovery paths; no hidden support bypass.
- Add server-side authorization and step-up controls for sensitive actions.

### Gate C — messaging proof of concept

- Run an XMTP proof of concept first; compare Waku separately rather than combining protocols by default.
- Re-verify current SDK capabilities, browser storage encryption, passkey association, installation limits, recovery, offline behavior, delivery and metadata exposure.
- Do not claim E2EE until key lifecycle, device behavior, attachment encryption and security review are complete.
- Keep plaintext message bodies and private keys out of application server logs/storage where the selected design requires client/protocol-side persistence.
- Add message requests, spam controls, block, mute, report and privacy-safe notifications.

### Gate D — Marketplace and Local Services

- Enforce seller/provider ownership on the server.
- Implement draft/review/published/rejected states, listing CRUD, categories, images and policy checks.
- Add selected-country/location search and radius only with consent and a privacy design.
- Implement verification with explicit purpose, approved provider/manual review, secure private storage, access logs, retention/deletion and appeals.
- Restrict regulated/high-risk service categories until legal/compliance approval.
- Ensure seller/provider contact creates or opens a native TwinCercle conversation with a safe context reference.

### Gate E — Operations and launch hardening

- Admin-only routes require server-checked roles, MFA/step-up, least privilege and sanitized immutable audit events.
- Add reporting, moderation, takedown, suspension/restore, appeal and support case workflows.
- Add privacy-safe notifications, idempotent jobs and rate limits.
- Add unit/integration/E2E tests, backups, restore tests, incident response, dependency review, CSP, monitoring and rollback.
- Conduct mobile accessibility/performance QA and independent security review.

### Later product gates

- Mail: internal-only first; SMTP is a separate product/operations project.
- Communities: group security/moderation design before launch; evaluate MLS where appropriate.
- Wallet/Web3: optional, non-custodial; SIWE validation must include nonce, domain, URI, chain, issued-at and expiry; no seed phrase access.
- Billing/referrals: no money movement or public pricing until founder approval, jurisdiction review, tax/refund/chargeback/fraud rules, integer-minor-unit accounting, idempotency and payout policy are defined.

## 8. Required completion report after future coding

Every material implementation task must report:

1. Exact files changed.
2. What is implemented versus prototype, planned or blocked.
3. Commands/tests run and exact results.
4. Mobile/desktop QA results or outstanding visual checks.
5. Security/privacy limitations and user data handled.
6. Human decisions/credentials still required (never ask users to paste secrets into chat).
7. Updated `docs/PHASE_STATE.md` and any relevant ADR.
8. One next recommended implementation step.

**Do not mark a phase complete because a screen renders. Acceptance criteria and tests must pass.**