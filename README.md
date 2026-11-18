# TwinCercle — Ultra Super MVP

### A Unified Digital Ecosystem

**Your Identity. Your Privacy. Your Communication. Your World.**

This folder contains a mobile-first, interactive frontend prototype for the current TwinCercle product direction. It brings the Balanced MVP's core product journeys into one connected workspace while keeping future modules visible as clearly labelled previews.

- **Product:** TwinCercle
- **Canonical domain:** https://twincercle.com
- **Repository:** https://github.com/shamimnoorofficial/TwinCercle
- **Product direction:** Unified Digital Ecosystem
- **MVP strategy:** Balanced
- **Prototype status:** Frontend demo only — not a production service

---

## 1. What is included

| Area | Included interaction | Actual status in this package |
|---|---|---|
| Overview | Activity summary, quick actions, marketplace and service highlights | Browser-local prototype |
| Discover | Search people, products, stores and service providers | Sample-data search |
| Connect | Conversation list, message requests, accept/decline, local text messages, mute, block and report | Browser-local demo; no live delivery or E2EE |
| Marketplace | Product discovery, category/location filters, details, saved listings, report listing, create product draft, message seller | Sample data + local drafts |
| Local Services | Provider/service discovery, category/location filters, detail view, report service, create service draft, message provider | Sample data + local drafts |
| Business & Trust | Seller business profile draft, provider profile draft, product/service draft workspace, verification policy explainer | Browser-local prototype; no actual verification |
| Identity | Editable display profile and username-format validation | Browser-local profile only; no account or username registry |
| Security | Passkey, recovery, device and privacy requirements overview | Explanatory UI only; no authentication/security service |
| Notifications | Sample activity and local notification preferences | Browser-local demo; no push service |
| Operations | Verification/moderation queue preview and local reports | Demo-only preview; no privileged admin backend |
| Mail | Future module preview | P1; not implemented |
| Communities | Future module preview | P1/P2; not implemented |
| Wallet & Web3 | Future module preview | P1/P2; no wallet connection |

The former Ekota marketplace and local-services model is treated as part of TwinCercle, not as a separate brand or product. Marketplace and Local Services contact actions open native TwinCercle Connect conversations. There is no default WhatsApp redirect.

## 2. Open the prototype

The prototype is plain HTML, CSS and JavaScript and needs no package installation.

```bash
python -m http.server 8000
```

Open `http://localhost:8000` from the directory containing `index.html`.

Keep the `assets/` directory beside `index.html`; it contains the TwinCercle mark used by the app and favicon.

You can also open `index.html` directly in a modern browser. Serving it locally is recommended for consistent browser behavior.

## 3. Try the main journeys

1. Open **Marketplace**, inspect a listing, save it, and choose **Message seller**. The app opens a native Connect conversation with the listing context.
2. Open **Local Services**, inspect a service, and choose **Message provider**. The app opens a native Connect conversation with the service context.
3. In **Connect**, accept the sample message request, open a conversation, send a demo message, and try mute/block/report controls.
4. In **Business & Trust**, create a seller profile, provider profile, product draft or service draft.
5. Open **Identity** to update the local demo profile; open **Security** to review the passkey, recovery and device-management implementation gates.
6. Switch light/dark mode from the top bar. On mobile, use the bottom navigation and **More** sheet to reach secondary modules.
7. Use **Security → Reset demo** to clear browser-local prototype data and return to the initial examples.

## 4. Demo data and privacy boundary

The prototype uses illustrative people, products, businesses, providers, prices, locations, availability and delivery estimates. These are not real offers, verified businesses, actual user accounts or measured location results.

User-created demo profiles, drafts, saved listings, reports, preferences and conversation text are stored in the current browser's `localStorage` under `twincercle-ultra-mvp-v1`. They are not synchronized to a server. Do not enter real identity documents, passwords, recovery secrets, wallet keys, private data or sensitive message content.

The prototype does **not** provide:

- Real registration, login, OAuth, passkey/WebAuthn, session issuance or device revocation.
- XMTP, Waku, MLS, realtime delivery, push notifications or end-to-end encrypted messaging.
- Encrypted attachment upload, secure object storage, encrypted backup or message key management.
- A production identity/username registry, DID issuance or interoperable credential verification.
- Seller/provider KYC, face/liveness checks, document collection, moderation staffing or admin authorization.
- Production database persistence, server-side validation, API authorization, audit logging or rate limiting.
- SMTP mail, external email interoperability or a working Mail module.
- Public communities, group messaging, wallet connection, blockchain transactions or smart contracts.
- Checkout, payments, escrow, subscriptions, commissions, partner payouts or delivery logistics.

A verification badge is not a guarantee. Delivery times are estimates. TwinCercle is represented as a discovery and communication layer; the buyer and seller/provider must agree on availability, final price, delivery and payment directly unless a later approved product/legal decision changes this model.

## 5. Technical notes

This is a standalone frontend interaction prototype, not a production framework selection or backend architecture decision. The Master Context's open decisions remain open. The repository's actual package files, framework, hosting, database and CI configuration must be inspected before implementing or migrating the production application.

No third-party JavaScript library or remote image dependency is required by this prototype. Styling, interaction code and sample data are contained in `index.html`; the brand mark is in `assets/twincercle-mark.svg`.

## 6. Suggested next implementation sequence

1. Inspect the actual GitHub repository, package manifests, deployment files and current branch; reconcile the prototype with the real project structure.
2. Record architecture decisions for frontend/backend framework, database, authentication provider and hosting before production migration.
3. Implement identity, secure authentication, username ownership, sessions and recovery.
4. Run a messaging proof of concept (XMTP first candidate; evaluate Waku separately) and verify key, local-storage, multi-device and recovery behavior.
5. Build server-backed business ownership, seller/provider onboarding, verification, listing CRUD and policy enforcement.
6. Integrate Marketplace/Local Services native Connect entry points with the selected messaging implementation.
7. Add admin/moderation authorization, reporting, audit events, privacy-safe notifications, tests and operational safeguards.
8. Implement P1/P2 modules only after their product, security and legal gates are approved.

Read `CONTEXT.md` before changing scope. `ULTRA_MVP_HANDOFF.md` contains the implementation handoff and non-negotiable constraints. `docs/PHASE_STATE.md` records exactly what was checked for this prototype.

---

**TwinCercle is a work in progress.** This is an interactive UI prototype and product-flow baseline, not a production-ready MVP release.


## Runtime bootstrap fix (18 November 2026)

The standalone prototype had an initialization-order defect: `loadState()` could run before the `cloneData` helper was initialized, causing a `ReferenceError` and preventing the app from rendering. The helper is now declared before the initial state load. The inline JavaScript passes `node --check`; the HTML shell and required app containers were also checked.
# TwinCercle