# TwinCercle — Balanced MVP Roadmap

This roadmap follows the supplied Master Context. A feature may appear in the prototype before implementation; the status table in `PHASE_STATE.md` is the source of truth for this package's actual implementation status.

## P0 — Balanced MVP

### Identity foundation
- Account registration/login with an approved secure authentication plan.
- Username/profile basics, normalization, protected names and enumeration controls.
- Device/session listing and revocation.
- Account security and recovery UX, with no hidden support bypass.
- Localization foundation and feature flags.

### Connect
- One-to-one conversations and message requests.
- Text messaging using the selected protocol or a clearly labelled development adapter.
- Attachments only after client-side encryption and upload design are approved.
- Block, mute, report and abuse controls.
- Native seller/provider contact entry points.

### Marketplace
- Seller/business onboarding and ownership.
- Verification submission and authorized review.
- Storefront and product/category listing CRUD.
- Local/national discovery with privacy-aware location filters.
- Listing details, estimated delivery, saved items and native seller messaging.

### Local Services
- Provider profile and verification.
- Approved service categories, service coverage, availability and rate guidance.
- Local provider discovery and native provider messaging.
- Reporting and moderation.

### Business & Operations
- Server-enforced admin roles and audit events.
- Verification review, user/business/provider reports, suspend/restore and feature-flag controls.
- Privacy-conscious notifications and operational error handling.

## P1 — Next expansion

- Small group messaging.
- Internal Mail module (not assumed to be SMTP).
- Business inbox and team seats.
- QR profile/store/provider pages.
- Partner-assisted onboarding with revocable delegated permissions.
- Referral/promoter tools only after commercial policy approval.
- Verified reviews and saved searches.
- Encrypted backup proof of concept.
- Richer storefront/business analytics and Communities beta.

## P2 — Later and gated

- SMTP interoperability.
- Voice/video.
- Large public communities and channels.
- On-chain username registry or identity proofs.
- Wallet payments, escrow or financial services after legal/security review.
- Premium usernames, custom domains and multiple identities.
- International marketplace and cross-border shipping.
- Native mobile applications, AI messaging agents and regulated service categories.

## Acceptance rule

A phase is complete only when the acceptance criteria in the Master Context pass, test/build evidence is recorded, known risks are listed, required human approvals exist and `docs/PHASE_STATE.md` is updated. Rendering a screen or generating a demo state is not production completion.