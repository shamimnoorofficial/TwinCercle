# TwinCercle — Master Context & Unified Ecosystem Development Blueprint

> **Document type:** Product Constitution · Architecture Blueprint · AI Vibe-Coding Operating Manual  
> **Product:** TwinCercle  
> **Canonical domain:** `twincercle.com`  
> **Current product direction:** Unified Digital Ecosystem  
> **MVP strategy:** Balanced  
> **Document status:** Master working specification — implementation status must be verified against the repository  
> **Last consolidated:** 18 November 2026

---

## 0. Document Authority, Scope & Change Control

This document is the primary product and engineering context for TwinCercle. Any AI coding agent, developer, designer, reviewer, or contributor must read it before proposing or implementing a material change.

### 0.1 Current controlling decisions

The following decisions represent the current product direction and take precedence over older project notes where they conflict:

1. The product name is **TwinCercle** and the canonical domain is **twincercle.com**.
2. TwinCercle is a **Unified Digital Ecosystem**, not only a Web3 wallet, email product, chat app, or marketplace.
3. The MVP follows a **Balanced** strategy: deliver a coherent, usable core across identity, native communication, marketplace, and local services without trying to ship every future module at once.
4. The former Ekota marketplace and local-services business model is absorbed into TwinCercle as first-class product modules. **Ekota is not a separate product, sub-brand, or website in this project.**
5. Marketplace and Local Services must use **native TwinCercle messaging** for buyer–seller and customer–provider communication. Do not redirect users to WhatsApp as the default contact action.
6. TwinCercle retains its privacy-first identity and communication foundations: passkey-capable authentication, user-controlled identity, end-to-end encryption as a target for private messaging, optional external wallet connection, and a hybrid rather than falsely “fully decentralized” architecture.
7. The uploaded Ekota `SCRIPT.md` and former `CLAUDE.md` are **business-model and workflow references only**. Ekota-specific domain, branding, WhatsApp contact flow, exact technical stack, deployment assumptions, phase numbering, and locked settings do not automatically become TwinCercle decisions.
8. The existing repository and its prototype must be inspected before implementation. Documentation or a UI mock-up is not proof that a backend feature exists.

### 0.2 Precedence rules

When instructions conflict, apply this order:

1. Latest explicit founder decision in the current project conversation.
2. This `CONTEXT.md`.
3. Approved records in `docs/DECISIONS.md` (once the file exists).
4. Verified current implementation and tests.
5. Existing repository documentation and comments.
6. Source reference documents, including the former Ekota `CLAUDE.md` and `SCRIPT.md`.
7. AI assumptions or generic best practices.

If a conflict cannot be resolved using this order, stop and ask one precise question. Do not silently invent a decision.

### 0.3 Decision ledger

Create `docs/DECISIONS.md` for short Architecture Decision Records (ADRs). Each entry must include:
- ID and date
- Context / problem
- Options considered
- Decision
- Consequences and trade-offs
- Status: proposed, accepted, superseded

Do not label a proposal as accepted without founder approval. Do not rewrite historical decisions; supersede them with a new ADR.

### 0.4 Project state

Create `docs/PHASE_STATE.md` and update it after each completed development phase. Record:
- Current phase and sub-step
- What was actually implemented
- Files created or changed
- Commands and tests run, with real results
- Known defects and security limitations
- Human inputs or credentials still required
- Next single recommended step

Never claim a phase is complete unless its acceptance criteria pass. Never claim production readiness based on a static prototype.

---

# PART I — PRODUCT CONSTITUTION

## 1. Product Identity

### TWINCERCLE
**A Unified Digital Ecosystem**

**Brand promise:** Your Identity. Your Privacy. Your Communication. Your World.

TwinCercle connects a person’s digital identity, private communication, marketplace activity, local services, communities, and optional Web3 capabilities through one coherent account and product experience.

The product should feel like one ecosystem with connected modules—not a collection of unrelated mini-apps.

### 1.1 Core product idea

A user should be able to:
- Create and manage one durable TwinCercle identity.
- Discover people, businesses, products, and services.
- Start a private conversation with a person, seller, or service provider.
- Communicate through TwinCercle’s own messaging experience.
- Manage a personal profile and, where eligible, business or provider profiles.
- Use an email-like internal communication experience under the TwinCercle namespace.
- Join communities when that module is enabled.
- Connect an external crypto wallet optionally.
- Control devices, sessions, privacy, security, and recovery settings.

### 1.2 Product principles

1. **One identity, connected experiences** — a single account should connect the modules without duplicating profiles.
2. **Privacy by design** — collect the minimum data required and explain why it is needed.
3. **User control** — users should understand and control their identity, devices, linked wallets, and recovery options.
4. **Secure by default** — authentication, authorization, encryption, rate limits, and abuse controls are architecture requirements.
5. **Honest decentralization** — describe the system as hybrid unless the implementation proves otherwise.
6. **Modular architecture** — modules have explicit boundaries and can evolve independently.
7. **Trust with clear limits** — verification badges communicate what was checked; they do not guarantee honesty, product quality, delivery, or safety.
8. **Local-first usability** — mobile-first, accessible, resilient on slower connections and lower-end Android devices.
9. **No fake functionality** — demos, simulations, planned features, and production features must be clearly distinguished.
10. **Sustainable growth** — business models and referral economics must be transparent, configurable, and legally reviewed.

## 2. Unified Ecosystem Map

TwinCercle is organized around one account and a set of connected modules.

| Module | Purpose | MVP position |
|---|---|---|
| Identity | Username, profile, authentication, devices, recovery, privacy | P0 — foundational |
| Connect | Native one-to-one messaging, message requests, attachments, safety controls | P0 — foundational |
| Marketplace | Discover local/national sellers, stores, products, availability and estimated delivery | P0 — balanced MVP |
| Local Services | Discover verified service providers, service areas, rates and availability | P0 — balanced MVP |
| Mail | Internal email-like communication, inbox, subject, archive and attachments | P1 — staged after messaging foundation |
| Business & Trust | Seller/provider onboarding, verification, storefront, moderation and reviews | P0 essentials; advanced tools P1 |
| Communities | Groups, channels, community discovery and moderation | P1/P2, feature-flagged |
| Wallet & Web3 | Optional wallet linking, signing, identity proofs and future on-chain services | P1/P2; no custody in MVP |
| Notifications | Privacy-conscious alerts and delivery status | P0 essentials |
| Admin & Operations | Verification review, reports, abuse handling, feature flags and audit trails | P0 internal |

### 2.1 Navigation model

A recommended primary navigation:
- Home / Discover
- Connect
- Marketplace
- Local Services
- Mail (feature-flagged until functional)
- Communities (feature-flagged)
- Profile / Identity
- Notifications
- Settings & Security

On mobile, use a compact navigation pattern with clear labels and no more than five primary destinations at a time. Secondary modules may live in a “More” or app-switcher area.

### 2.2 Unified user journeys

**Buyer**
1. Create an account and claim a username.
2. Search for a product or store by keyword, category, location, and radius.
3. Review store information, seller verification status, price, stock status, and estimated delivery details.
4. Start a native TwinCercle conversation.
5. Discuss availability, price, delivery, and payment directly with the seller.
6. Save a store or listing and optionally leave a review after a qualifying interaction.

**Seller**
1. Create or claim a business profile.
2. Complete identity/business verification as required by the approved policy.
3. Create a storefront and add product listings.
4. Set location, service area, opening hours, stock and delivery options.
5. Receive customer inquiries in the native TwinCercle inbox.
6. Manage listings, conversations, profile visibility, and subscription status if subscriptions are approved.

**Service provider**
1. Create an individual or business provider profile.
2. Submit the required verification information.
3. Add service categories, descriptions, service area, rate guidance, and availability.
4. Receive customer inquiries through native TwinCercle messaging.
5. Manage requests, reviews, and profile visibility.

**Partner-assisted onboarding**
1. An approved partner helps a seller create a draft business profile.
2. The seller remains the business owner and completes their own verification.
3. Partner permissions are limited, auditable, and revocable.
4. The partner cannot take ownership of the seller’s identity, payout account, or business data.
5. Partner fees, margins, and renewal rules remain configurable and subject to founder/legal approval.

**Promoter/referral**
1. An eligible promoter receives a referral code.
2. Attribution is recorded transparently and protected against self-referral and abuse.
3. Any commission is calculated from an approved configuration and immutable ledger.
4. Earnings are not guaranteed; eligibility, holding periods, approval, reversals, tax and payout conditions must be disclosed.

## 3. Marketplace & Local Services — Integrated Ekota Model

This section preserves the useful business mechanics from the former Ekota source material while adapting the product to TwinCercle.

### 3.1 Marketplace positioning

TwinCercle Marketplace is a discovery, listing, and communication platform. At launch, it should not imply that TwinCercle:
- Owns or stores sellers’ inventory.
- Is the seller of record.
- Guarantees product authenticity or quality.
- Provides delivery itself.
- Holds buyer funds or provides escrow.
- Mediates or guarantees buyer–seller payment.
- Guarantees estimated delivery times.

Unless a later approved product/legal decision changes this model, buyer and seller agree directly on availability, final price, delivery arrangement, and payment. TwinCercle provides discovery, identity context, messaging, and platform safety tools.

### 3.2 Local and national discovery

The search model should support:
- Local discovery using a chosen location and radius.
- National discovery within a selected country.
- Future international discovery only after legal, shipping, currency, and operational readiness.
- Product, store, and service-provider search.
- Bengali and English search terms, including transliteration support where practical.
- Filters for category, price range, open status, availability, verification state, rating, and delivery/service coverage.
- List and map presentation, with map libraries loaded only when needed.

Local delivery times must always be labeled **estimated**. The seller/provider confirms the actual arrangement in the conversation.

### 3.3 Local Services

Provider categories may include:
- Shopping assistance and errands
- Local delivery arranged by the provider or seller
- Repair and maintenance
- Electrician and plumbing work
- Home and personal services
- Other approved non-regulated services

Medical, financial, legal, childcare, transport, and other regulated/high-risk categories require a separate compliance review and approval workflow before publication. Do not automatically publish sensitive service categories.

### 3.4 Native communication rule

Every “Contact seller”, “Ask about product”, “Hire provider”, or equivalent action must:
- Open or create a TwinCercle conversation.
- Include a safe contextual reference to the store/listing/provider.
- Respect message requests, privacy settings, blocks, and abuse prevention.
- Avoid exposing private phone numbers or email addresses unnecessarily.
- Never silently redirect to WhatsApp.

A future optional external contact method may be considered only through an explicit user-facing choice and a separate approved ADR. It must not replace native messaging as the default.

### 3.5 Verification and trust

The platform may support:
- Email/phone verification.
- Individual identity verification.
- Business/legal document review.
- Face/liveness verification only if legally justified, consented to, securely handled, and supported by an approved provider.
- Manual admin review in an early release.

Verification statuses should be explicit: `NOT_STARTED`, `PENDING`, `IN_REVIEW`, `VERIFIED`, `REJECTED`, `EXPIRED` (final enum subject to schema review).

A “Verified” badge must state what has been verified. It is not a warranty, endorsement, guarantee of service, or proof that a listing is safe.

### 3.6 Commercial model — inherited assumptions, not approved TwinCercle prices

The former Ekota materials contain the following commercial assumptions:
- Seller annual subscription in a range of USD 10–20 depending on plan/scope.
- Partner discount or margin in a range of 40–50%.
- Promoter commission assumption of 10%, subject to a holding period, approval, and monthly payout.
- Service providers were described as free at initial launch.
- One detailed former implementation draft used 25% seller discount for promoter codes, 45% default partner discount, a 30-day commission hold, a USD 20 payout threshold, and a 7-day subscription grace period.

**These values are not automatically approved TwinCercle policy.** Treat them as inherited reference assumptions only. Do not hardcode them, advertise them, or implement money movement until the founder approves the commercial model and the legal/accounting requirements.

If subscriptions or referral earnings are introduced:
- Store amounts as integer minor units (e.g., cents), never floating-point money.
- Keep prices, discounts, commissions, hold periods, thresholds, currencies and grace periods in server-controlled configuration.
- Centralize calculations in tested domain services.
- Use an append-only or auditable ledger for commissions and payouts.
- Make webhook processing idempotent.
- Never claim guaranteed income.
- Define refunds, cancellations, chargebacks, tax, currency conversion, fraud controls and payout restrictions.
- Obtain legal and payment-provider review before launch.

## 4. Identity & Account Architecture

### 4.1 TwinCercle identity namespace

A user may have a public identity such as:

`username@twincercle.com`

This is a TwinCercle namespace/identifier. It is **not automatically a conventional SMTP mailbox** and must not be advertised as ordinary interoperable email unless SMTP delivery, sending, receiving, abuse controls, and domain operations are actually implemented.

Identity components:
- Internal immutable user ID.
- Unique username/handle.
- Public profile.
- Optional DID or interoperable identity credential.
- Messaging protocol identity/inbox identifier.
- Registered devices/installations.
- Recovery methods.
- Optional linked external wallets.
- Security and privacy preferences.

### 4.2 Username policy

Before public username launch, define:
- Case-insensitive uniqueness.
- Normalization and allowed characters.
- Reserved and protected names.
- Impersonation and squatting controls.
- Rename rules and cooldowns.
- Deactivation and deletion behavior.
- Dispute and recovery process.
- Username transfer policy, if any.
- Search privacy and enumeration protection.

A username registry should not expose a bulk account-enumeration endpoint.

### 4.3 Authentication

Recommended direction:
- Passkey/WebAuthn-first authentication where browser/device support permits.
- Email verification and/or carefully selected recovery channel as appropriate.
- Optional Google OAuth only as a convenience provider, not as the only identity anchor.
- Optional external wallet signature for wallet ownership linking.
- Step-up authentication for high-risk actions.

WebAuthn is an authentication standard; it is not a wallet, messaging protocol, or encryption system. The platform must not collect raw biometric data. Device biometrics are handled by the operating system authenticator.

### 4.4 Wallet linking

External wallet connection is optional and must not be required to use core marketplace or messaging features.

Rules:
- Use WalletConnect/Reown or a reviewed wallet provider; do not request seed phrases.
- Never transmit or store a user’s seed phrase or private key.
- Distinguish a login/ownership signature from a transaction signature.
- Do not request a transaction merely to log in.
- For SIWE/EIP-4361, validate nonce, domain, URI, chain ID, issued-at and expiration.
- Clearly display what the user is signing.
- Store only the minimum wallet-link metadata needed.
- Wallet linking must not silently grant spending permissions.

### 4.5 Recovery and device management

Account recovery must be designed before production:
- At least two independent recovery options should be encouraged where practical.
- Recovery secrets should be generated and stored client-side where applicable.
- The server must not have a hidden recovery bypass.
- Recovery actions should trigger notifications, audit events, and cooling-off/step-up controls for sensitive changes.
- Device list, session revocation, and wallet unlinking must be available.
- Support staff must not be able to read encrypted messages or impersonate the user.

Loss of all recovery material may make encrypted history unrecoverable. This limitation must be explained before users rely on encrypted backup.

## 5. Messaging & Cryptographic Architecture

### 5.1 Messaging requirements

MVP messaging should support:
- One-to-one conversations.
- Message requests and acceptance.
- Text messages.
- Safe attachment sharing.
- Delivery/read state where the chosen protocol supports it.
- Conversation list and search over locally available metadata.
- Block, mute, report, and spam controls.
- Multi-device behavior with a documented trust model.
- Native contact entry points from Marketplace and Local Services.

Group messaging, public channels, voice/video and large communities are later phases.

### 5.2 End-to-end encryption

E2EE is a security property that must be implemented and independently tested—not a marketing label.

Requirements:
- Message content is encrypted on the sender’s device and decrypted only by authorized recipient devices.
- The platform backend must not store plaintext message bodies or private encryption keys.
- Message metadata (participants, timing, delivery events, IP/network information) may still be observable; do not claim metadata anonymity.
- Attachments must be encrypted client-side before upload.
- Push notifications must not contain message bodies or sensitive sender details by default.
- Key changes and device additions/removals must be visible to users.
- Provide a safety-number/fingerprint verification mechanism if supported by the selected protocol.
- Security review must cover identity binding, key rotation, replay, forward secrecy, multi-device, backups, and recovery.

### 5.3 Protocol selection

Candidate protocols:
- **XMTP** — first candidate for a messaging proof of concept.
- **Waku** — alternative protocol family to evaluate separately.
- **MLS** — relevant for group messaging security.
- Web Crypto API and audited cryptographic libraries for browser-side primitives where appropriate.

Do not implement XMTP and Waku together in the MVP simply to appear more decentralized. Run a proof of concept and compare:
- Browser support and SDK maturity.
- Identity and passkey compatibility.
- Multi-device behavior.
- Message delivery and offline behavior.
- Local database protection.
- Recovery and key export/import.
- Relay/network dependency.
- Abuse prevention and moderation hooks.
- Cost, latency and operational complexity.

A prior XMTP technical review raised questions about browser-local database encryption, identity association, installation limits, recovery, and passkey support. Re-verify these against current official documentation and SDK versions before implementation; do not assume an old review is still current.

### 5.4 Local storage and backup

- Use IndexedDB only with a documented protection model.
- Do not assume browser storage is encrypted at rest.
- Evaluate WebAuthn PRF availability and platform compatibility before depending on it.
- Encrypted backup must be end-to-end encrypted and user-recoverable.
- Do not upload plaintext key material.
- Document browser storage eviction and iOS PWA limitations.
- Never claim “zero knowledge” without a concrete threat model and independent review.

## 6. Mail Module

Mail is an email-like internal communication experience, not automatically a public SMTP service.

Potential capabilities:
- Inbox, sent, drafts, archive, trash.
- Subject-based messages.
- Attachments encrypted at client side when appropriate.
- Search, labels and filters.
- Internal delivery to TwinCercle identities.
- Spam/report/block controls.
- Clear distinction between internal messages and external email.

SMTP interoperability, external domain sending/receiving, DKIM, SPF, DMARC, bounce processing, abuse operations, and mailbox quotas are separate future work. Do not display “send email anywhere” until implemented and tested.

## 7. Web3 & Blockchain Strategy

Web3 should add user ownership or verifiability where it genuinely improves the product. Do not add a blockchain merely for branding.

Candidate components:
- viem for EVM interactions.
- Reown AppKit / WalletConnect for optional wallet connection.
- SIWE for wallet-based authentication.
- W3C DID/Verifiable Credentials where interoperability is justified.
- Base or another EVM L2 as a candidate network.
- Solidity/OpenZeppelin only if a smart contract is genuinely required.

Rules:
- No private messages, personal data, KYC documents, phone numbers, or sensitive metadata on-chain.
- Keep the initial product usable without a wallet.
- Evaluate transaction fees, account abstraction, chain reliability, recovery, and regulatory implications.
- Smart contracts require threat modeling, tests, independent audit, upgrade/governance plan, and incident response before mainnet use.
- Avoid tokenomics, speculative promises, or “earn guaranteed crypto” language.

## 8. Technical Architecture

### 8.1 Architecture style

Use a **modular monolith** for the initial product. Keep clear boundaries between domains. Do not start with microservices.

High-level layers:
1. Presentation and design system
2. Identity and authentication
3. Authorization and policy
4. Messaging and cryptographic client
5. Marketplace
6. Local Services
7. Business and verification
8. Mail and Communities (feature-flagged)
9. Wallet/Web3 adapter
10. Notifications and background jobs
11. Data/storage and observability
12. Admin and trust operations

### 8.2 Stack direction

The previous TwinCercle context proposed:
- Frontend: React + TypeScript + Vite.
- Styling: Tailwind CSS and a reusable component system.
- Backend: Node.js + TypeScript modular API.
- Database: PostgreSQL.
- Local client data: IndexedDB.
- Optional cache/rate-limit service: Redis.
- Object storage: S3-compatible private/public buckets.
- Web3: viem and WalletConnect/Reown as needed.
- Hosting/CDN: Vercel, Cloudflare, or another selected provider.
- CI: GitHub Actions.

The former Ekota implementation document separately used Next.js 14.2.5, Prisma 5, Supabase/PostGIS, Auth.js, Lemon Squeezy and Netlify. That stack is **not automatically the TwinCercle stack**. Before changing the existing repository’s framework or deployment provider, inspect the actual package files, build scripts, hosting configuration and current working prototype. Record any migration decision in an ADR.

### 8.3 Backend boundaries

Suggested domain modules:
- `identity`
- `auth`
- `authorization`
- `messaging`
- `marketplace`
- `services`
- `business`
- `verification`
- `mail`
- `communities`
- `wallet`
- `notifications`
- `moderation`
- `billing`
- `referrals`
- `admin`
- `audit`

Each module should expose a small public API. Avoid cross-module database access that bypasses ownership and validation rules.

### 8.4 Data ownership principles

- User identity records belong to the identity domain.
- Message plaintext and cryptographic private keys remain client/protocol controlled.
- Server stores only the minimum messaging metadata required for routing, safety, and delivery.
- Marketplace listings and store data are owned by the seller/business.
- Partner access is delegated, limited, revocable and audited.
- Provider data is owned by the provider.
- Verification documents are stored in private encrypted storage with strict access.
- Referral and payout records use an auditable ledger.
- Admin actions are recorded without copying sensitive content into logs.

## 9. Data Model Blueprint

This is a logical blueprint, not a migration-ready schema. Final fields, constraints, indexes, retention and relations must be reviewed against the selected database and actual implementation.

### 9.1 Identity and access

- `users`
- `user_profiles`
- `username_claims`
- `authenticators`
- `user_sessions`
- `registered_devices`
- `recovery_methods` (metadata only; never store plaintext recovery secrets)
- `linked_wallets`
- `user_preferences`
- `user_blocks`
- `user_reports`

### 9.2 Messaging metadata

- `conversations`
- `conversation_members`
- `conversation_requests`
- `message_delivery_events`
- `message_attachments` (encrypted object references and safe metadata)
- `device_messaging_installations`
- `conversation_safety_events`

Do not create a plaintext server-side shadow copy of encrypted message content. If the selected protocol owns message persistence, avoid duplicating message bodies in the application database.

### 9.3 Marketplace

- `businesses`
- `business_members`
- `business_locations`
- `seller_verifications`
- `categories`
- `products`
- `product_media`
- `product_locations` if multiple locations are supported
- `saved_items`
- `listing_reports`
- `seller_reviews`
- `business_subscriptions` only after billing is approved

### 9.4 Local Services

- `service_providers`
- `service_provider_members`
- `service_provider_verifications`
- `service_categories`
- `service_listings`
- `provider_service_areas`
- `service_availability`
- `service_reviews`
- `service_requests` only if a structured request workflow is approved

### 9.5 Mail and Communities

- `mail_threads`
- `mail_participants`
- `mail_message_metadata`
- `mail_attachments`
- `community_spaces`
- `community_memberships`
- `community_roles`
- `community_moderation_events`

Mail message body storage must follow the selected encryption model. Do not add a table that silently stores plaintext if the product promises E2EE.

### 9.6 Business, trust and operations

- `verification_events`
- `moderation_cases`
- `audit_events`
- `notifications`
- `notification_preferences`
- `feature_flags`
- `support_cases`
- `assets`
- `subscription_plans`
- `subscription_events`
- `referral_codes`
- `referral_attributions`
- `commission_ledger`
- `payout_batches`

Use idempotency keys for payment/referral/webhook operations. Money values use integer minor units and an explicit currency.

## 10. API & Authorization Principles

All mutating operations must:
- Validate input server-side.
- Authenticate the caller.
- Authorize the action against the specific resource and owner.
- Enforce rate limits and abuse controls.
- Use transactions where multiple records must change together.
- Be idempotent where retries are possible.
- Emit sanitized audit events.
- Return stable error codes and localized user-facing messages.

Suggested API domains:
- `/api/v1/auth`
- `/api/v1/identity`
- `/api/v1/usernames`
- `/api/v1/devices`
- `/api/v1/messaging`
- `/api/v1/marketplace`
- `/api/v1/services`
- `/api/v1/business`
- `/api/v1/verification`
- `/api/v1/mail`
- `/api/v1/communities`
- `/api/v1/wallet`
- `/api/v1/notifications`
- `/api/v1/admin`

Use a centralized authorization policy such as `can(user, action, resource)` or an equivalent policy layer. Do not scatter ad-hoc role checks throughout UI components. Enforce ownership checks on every server action/API route; client-side hiding is not authorization.

## 11. Security, Privacy & Trust Requirements

### 11.1 Baseline

- Threat model identity, messaging, marketplace, provider onboarding, admin, billing, and recovery separately.
- Use secure, HttpOnly, SameSite cookies where cookie sessions are used.
- Apply CSRF protection where relevant.
- Use a strict Content Security Policy.
- Validate uploads by content, size, type and malware scanning strategy.
- Use private buckets and short-lived signed URLs for sensitive files.
- Keep secrets in environment/secret management, never in Git.
- Apply least-privilege database and service credentials.
- Require MFA/step-up authentication for sensitive admin actions.
- Rate-limit OTP, username lookup, search, message requests, reports and referral redemption.
- Avoid account/username enumeration.
- Keep dependencies pinned and review supply-chain risks.
- Maintain backups, restore tests, incident response and key rotation procedures.

### 11.2 Logging and analytics

Never log:
- Passwords, OTP values, access tokens, private keys, seed phrases or recovery secrets.
- Plaintext message bodies or attachment contents.
- Raw identity documents or biometric samples.
- Full payout/bank details.
- Sensitive location history unless strictly necessary and consented.

Analytics should collect only what is needed. Do not use message content for analytics. Push payloads should not reveal private message content by default.

### 11.3 Verification and biometric data

If identity documents, selfies or face/liveness checks are used:
- Obtain explicit informed consent.
- Explain purpose, provider, storage location, retention and deletion.
- Use a reviewed KYC provider or controlled manual review process.
- Encrypt at rest and restrict access.
- Keep raw files only as long as necessary.
- Retain verification outcome and minimal evidence only where lawful.
- Provide a correction/appeal path.
- Complete legal review for each launch jurisdiction.

### 11.4 Marketplace safety

- Prohibited-item policy and reporting workflow.
- Seller/provider verification before public activation where required.
- Moderation queue and audit history.
- Clear statement that platform verification is not a guarantee.
- Review eligibility tied to a meaningful interaction, not arbitrary self-posting.
- Abuse, fraud, impersonation, spam and repeat-offender controls.
- Clear takedown and appeal process.

### 11.5 Legal and compliance gates

Before launch, obtain jurisdiction-specific legal advice on:
- Privacy and personal data processing.
- Biometric/identity verification.
- Consumer protection and marketplace intermediary responsibilities.
- Seller subscriptions, tax and refunds.
- Referral commissions and payout rules.
- Cross-border payments, FX and money transmission.
- Regulated service categories.
- Digital asset and wallet features.
- Data retention, deletion and law-enforcement requests.

Do not launch regulated or high-risk categories merely because a UI can display them.

## 12. UX, Design System & Accessibility

### 12.1 Brand direction

The preferred TwinCercle symbol is the **Twin Infinity Connection**: two white circular forms connected at the center with a smooth inward/curved meeting shape, on a blue-to-cyan/neon-blue background. Keep the symbol simple, recognizable at small sizes, and consistent across favicon, app icon, loading state and product UI.

Do not replace the preferred mark with an unrelated generic infinity or letter-W symbol without approval.

### 12.2 Visual product direction

- Premium, modern, calm, trustworthy.
- Blue/cyan brand foundation; use semantic colors consistently.
- Clean surfaces, subtle glass effects only where they improve hierarchy.
- Strong typography and readable content density.
- Clear distinction between primary and secondary actions.
- Consistent cards, spacing, icon sizes, radii and shadows.
- Dark and light themes where implemented.
- No decorative animation that harms performance or accessibility.

### 12.3 Responsive behavior

Design mobile-first:
- Test narrow Android screens, tablets and desktop.
- Touch targets at least 44×44 CSS pixels where practical.
- Avoid horizontal overflow.
- Search and filters must remain usable on mobile.
- Dialogs and menus must fit viewport and safe areas.
- Forms need visible labels, validation and keyboard support.
- Bottom navigation must not cover page content.
- Respect reduced-motion preference.

### 12.4 Accessibility

Target WCAG 2.2 AA:
- Semantic landmarks and headings.
- Keyboard navigation and visible focus.
- Sufficient contrast.
- Accessible names for icon buttons.
- Form labels and understandable errors.
- Screen-reader status announcements.
- Reduced motion support.
- Captions/transcripts for media where relevant.

### 12.5 Localization

Initial language direction: English and Bengali. Confirm the default language with the founder before implementation. Use a localization system rather than scattering hardcoded strings. Support Bengali font rendering and mixed-language content. Search normalization should account for Bengali text and transliteration where feasible.

## 13. Performance, PWA & Reliability

- Lazy-load maps and heavy modules.
- Compress and resize uploaded images.
- Use responsive images and modern formats.
- Cache only data that is safe to cache.
- Avoid shipping all module code on the initial route.
- Provide loading, empty, error and offline states.
- Monitor Core Web Vitals and mobile performance.
- Test on slower networks and lower-end Android hardware.
- PWA installation and push notifications are staged features; browser/platform support must be verified.
- Do not promise background delivery or offline messaging until the chosen protocol and platform support it.

Suggested initial performance goals (targets, not measured results):
- Lighthouse mobile Performance ≥ 90 for non-map public pages where feasible.
- Avoid loading map SDK on initial page load.
- Keep route-specific bundles small.
- Track real-user performance before making claims.

## 14. MVP Scope — Balanced Delivery

### P0 — Balanced MVP

**Platform foundation**
- Responsive application shell and design system.
- Identity registration/login flow with a secure authentication plan.
- Username/profile basics.
- Session/device list and revoke controls.
- Account security and recovery UX.
- Localization foundation.
- Feature flags and error handling.

**Native Connect**
- One-to-one conversation.
- Message request/acceptance.
- Text messaging through the selected protocol or a clearly labeled development adapter.
- Attachment flow only after encryption and upload design is approved.
- Block, mute, report and abuse controls.
- Conversation entry from Marketplace and Local Services.

**Marketplace**
- Seller/business onboarding.
- Verification submission and admin review.
- Storefront profile.
- Product/category listing CRUD.
- Local and national search foundation.
- Location/radius filters and map as a lazy-loaded enhancement.
- Listing details, estimated delivery note and saved items.
- “Message seller” opens native TwinCercle conversation.

**Local Services**
- Provider onboarding and verification.
- Provider profile and service categories.
- Service area, availability and rate guidance.
- Local provider discovery.
- “Message provider” opens native TwinCercle conversation.
- Reporting and moderation.

**Admin/trust**
- Admin access control.
- Verification review queue.
- User/business/provider reports.
- Suspend/restore actions.
- Audit trail for sensitive operations.
- Feature-flag management.

### P1 — Next expansion

- Small group messaging.
- Internal mail module.
- Business inbox and team seats.
- QR profile/store/provider pages.
- Partner-assisted onboarding.
- Referral/promoter tools after approved commercial model.
- Verified reviews and saved searches.
- Encrypted backup proof of concept.
- Richer storefront and business analytics.
- Communities beta.

### P2 — Later / gated

- SMTP interoperability.
- Voice/video.
- Large public communities and channels.
- On-chain username registry or identity proofs.
- Wallet payments, escrow or financial services (legal/security review required).
- Premium usernames/custom domains/multiple identities.
- International marketplace and cross-border shipping.
- Native mobile apps.
- AI agents/bots in messaging.
- Regulated service categories.

## 15. Development Roadmap & Phase Gates

Phases should be adapted to the repository’s actual state. Do not assume a phase is complete because a prototype screen exists.

### Phase 0 — Repository and architecture audit
- Inspect all files, package scripts, framework, deployment config and current branch.
- Identify current UI prototype boundaries.
- Record existing working features and demo-only behaviors.
- Consolidate documentation and ADRs.
- Define environment and secret requirements.
- Produce implementation plan.

**Exit criteria:** verified repo map, no conflicting master documents, current status report, approved architecture decisions.

### Phase 1 — Design system and application shell
- Brand tokens, logo asset integration, typography, navigation.
- Responsive app shell and route structure.
- Accessible components and theme support.
- Loading, empty, error and offline states.

**Exit criteria:** responsive visual QA across target breakpoints; keyboard and accessibility checks.

### Phase 2 — Identity and authentication foundation
- Account model and username rules.
- Passkey/WebAuthn proof of concept.
- Optional OAuth integration if approved.
- Sessions, device registration, revocation.
- Recovery model and threat review.

**Exit criteria:** tested authentication and session security; recovery limitations documented.

### Phase 3 — Native messaging proof of concept
- Evaluate XMTP first and Waku separately.
- Validate identity binding, browser support, persistence, multi-device and recovery.
- Implement one-to-one messaging with safety controls.
- Test encryption properties and metadata exposure.

**Exit criteria:** protocol decision recorded; security claims match tested implementation.

### Phase 4 — Marketplace core
- Business onboarding and ownership.
- Verification workflow.
- Storefront and listing CRUD.
- Search and discovery.
- Native message-seller flow.

**Exit criteria:** buyer and seller journeys pass end-to-end tests; no WhatsApp default redirect.

### Phase 5 — Local Services
- Provider profile and verification.
- Service listing, coverage and availability.
- Provider discovery and native message-provider flow.
- Reporting and review eligibility.

**Exit criteria:** provider journey and safety/moderation checks pass.

### Phase 6 — Mail and notification foundation
- Internal mail metadata and UI.
- Notification preferences and privacy-safe push strategy.
- Clarify SMTP/non-SMTP behavior in UI.

**Exit criteria:** internal mail semantics are accurate; no unsupported SMTP claims.

### Phase 7 — Business, referrals and monetization
- Confirm commercial model and jurisdictions.
- Subscription plan configuration.
- Partner/promoter flows.
- Idempotent billing webhooks.
- Commission ledger and payout controls.

**Exit criteria:** approved legal/business rules, tested idempotency, audited money calculations, secure payout handling.

### Phase 8 — Communities and Web3 expansion
- Community spaces and moderation.
- Optional wallet connection.
- SIWE validation and wallet unlinking.
- Smart contract proof of concept only if justified.

**Exit criteria:** module-level threat reviews and user value validated.

### Phase 9 — Production hardening and launch
- Independent security review.
- Load/performance tests.
- Backup and restore tests.
- Incident response and monitoring.
- Legal sign-off.
- Accessibility and mobile QA.
- Release/rollback process.

**Exit criteria:** all launch blockers signed off; no false production claims.

## 16. AI Vibe-Coding Operating Instructions

Every AI coding session must follow this workflow.

### 16.1 Before coding

1. Read `CONTEXT.md`, `README.md`, `docs/DECISIONS.md` and `docs/PHASE_STATE.md` if present.
2. Inspect the current repository and relevant files; do not assume file paths or framework.
3. Identify the exact user-requested scope.
4. Restate the task and list files expected to change.
5. Separate confirmed requirements from assumptions.
6. Ask one precise question if a decision is genuinely blocking.
7. Do not begin unrelated refactoring.

### 16.2 During coding

- Work in small, reviewable increments.
- Preserve existing working behavior unless the task requires changing it.
- Follow the current repository’s established framework and conventions.
- Do not silently migrate framework, database, hosting provider or authentication.
- Keep domain logic out of UI components.
- Validate all inputs on the server.
- Enforce ownership and authorization server-side.
- Add tests for business logic and security-sensitive paths.
- Use environment variables for secrets and deployment-specific values.
- Do not invent API keys, OAuth credentials, provider IDs or production configuration.
- Do not add fake success states for backend actions.
- Use mock/demo adapters only when clearly labeled and isolated from production code.
- Do not claim E2EE, decentralization, wallet custody, verification, payment, or delivery unless implemented and verified.

### 16.3 After coding

Provide:
1. Summary of implemented changes.
2. Exact file tree or changed-file list.
3. Commands executed.
4. Test/build results, including failures.
5. Screenshots or visual QA notes where relevant.
6. Known gaps and security limitations.
7. Human inputs still required.
8. Suggested next step.
9. A concise `PHASE_STATE.md` update.

Never say “done” if tests were not run or if critical checks failed. Distinguish “implemented”, “prototype”, “mocked”, “planned”, and “blocked”.

### 16.4 Git workflow

- Use descriptive branch names.
- Prefer small conventional commits.
- Do not force-push or rewrite shared history without explicit approval.
- Review diffs before commit.
- Do not commit secrets, local databases, KYC files, recovery keys, or user message content.
- Use pull requests for material architectural changes.

## 17. Quality & Acceptance Checklist

### Product
- [ ] One account connects all enabled modules.
- [ ] Marketplace and Local Services are TwinCercle modules, not separate Ekota branding.
- [ ] Seller/provider contact opens native TwinCercle messaging.
- [ ] Pricing and earning statements are approved and not misleading.
- [ ] Delivery is labeled estimated and responsibility is clear.

### Identity & security
- [ ] Authentication and recovery threat model reviewed.
- [ ] Session/device revocation works.
- [ ] Wallet connection is optional and non-custodial.
- [ ] No seed phrases/private keys in backend.
- [ ] Sensitive admin actions require step-up/MFA and are audited.

### Messaging
- [ ] Encryption claims verified by tests/review.
- [ ] No plaintext message shadow copy on server.
- [ ] Attachments encrypted before upload if promised.
- [ ] Push notifications do not reveal message content by default.
- [ ] Block/report/message-request controls work.

### Marketplace & Services
- [ ] Seller/provider ownership and delegated access enforced.
- [ ] Verification status is accurate and explained.
- [ ] Moderation/reporting flow exists.
- [ ] Map and search are performant and privacy-aware.
- [ ] Native messaging handoff includes safe contextual details.

### Engineering
- [ ] Type checking and lint pass.
- [ ] Unit/integration/E2E tests run for the changed scope.
- [ ] Build succeeds.
- [ ] Secrets are absent from repository.
- [ ] Database migrations are reviewed and reversible where possible.
- [ ] Logs are sanitized.
- [ ] Documentation and phase state updated.

## 18. Open Founder Decisions

These items must remain open until explicitly approved:
1. Final frontend/backend framework and whether to retain the current Vite-based repository or migrate.
2. Database provider and ORM choice.
3. Authentication provider and exact passkey/OAuth combination.
4. XMTP vs another messaging protocol after proof of concept.
5. Exact meaning and launch scope of the Mail module.
6. Whether Marketplace seller subscriptions launch in MVP.
7. Seller pricing, currency, taxes, refunds and payment provider.
8. Partner discount/margin and promoter commission rules.
9. Verification provider, accepted documents, retention and launch jurisdictions.
10. Whether maps use Google Maps or an alternative.
11. PWA push and offline support guarantees.
12. Whether any wallet or blockchain functionality is included in the first public release.
13. Default language and localization policy.
14. Legal entity, terms, privacy policy and dispute process.

## 19. Explicit Non-Goals for the Initial MVP

- Do not build a custodial wallet.
- Do not store seed phrases or private keys.
- Do not put private messages or personal data on-chain.
- Do not claim the entire platform is fully decentralized.
- Do not claim the internal TwinCercle namespace is ordinary SMTP email.
- Do not implement escrow or buyer payment custody without a separate legal/product decision.
- Do not operate delivery logistics as if TwinCercle itself were the carrier.
- Do not guarantee seller/provider income, product quality, or delivery.
- Do not make WhatsApp the default contact path.
- Do not launch regulated service categories without approval.
- Do not build microservices prematurely.
- Do not treat a static HTML prototype as a production application.

---

## APPENDIX A — Former Ekota Source Material: What Was Retained

The former Ekota `SCRIPT.md` and `CLAUDE.md` described a local/national marketplace connecting buyers, local shops, service providers, partners and promoters. The useful product mechanics retained here are:
- Local and national discovery.
- Seller storefronts and product listings.
- Service-provider profiles, categories, distance and availability.
- Estimated—not guaranteed—delivery times.
- Seller/provider verification and moderation.
- Partner-assisted onboarding with seller ownership retained.
- Referral attribution and commission ledger as a possible future business model.
- Platform as a discovery/connection layer rather than inventory owner or payment custodian.

The following Ekota-specific assumptions are deliberately **not** carried forward as TwinCercle decisions:
- `ekota.store` domain and branding.
- WhatsApp deep links as the main communication flow.
- Next.js 14.2.5 / Prisma 5 / Supabase / Netlify / Lemon Squeezy as mandatory stack.
- Exact BD-only scope, fixed seed locations, exact subscription prices, discounts, commission rates and payout thresholds.
- Ekota’s original phase plan and its locked-decision list.

Any of these may be reconsidered only through a TwinCercle-specific decision.

## APPENDIX B — Security Language Guide

Use:
- “Designed to support end-to-end encrypted messaging” only while implementation is incomplete.
- “End-to-end encrypted” only after the actual protocol, key lifecycle and client behavior are verified.
- “Hybrid architecture” when platform servers still provide identity, discovery, relay, notification or metadata services.
- “Wallet connection is optional” if core product access does not require a wallet.
- “Estimated delivery” rather than “guaranteed delivery”.
- “Identity checked” or a precise verification label rather than “trusted seller” as an absolute guarantee.
- “Internal TwinCercle message” rather than “email” when SMTP interoperability is absent.

Avoid:
- “100% private”, “unhackable”, “fully decentralized” or “zero knowledge” without evidence.
- “Guaranteed earnings”.
- “Guaranteed delivery”.
- “Verified means safe”.
- “Your @twincercle.com address works with every email provider” unless SMTP interoperability exists.

---

**End of TwinCercle Master Context.**  
This document defines intended product and engineering direction. It does not certify that any listed feature is already implemented.