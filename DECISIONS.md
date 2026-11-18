# TwinCercle — Architecture Decision Register

**Status:** No new production architecture decisions are accepted by the Ultra Super MVP frontend prototype.

This register deliberately preserves the open decisions in the root `CONTEXT.md`. A frontend demo, generated file or AI recommendation does not approve a production framework, service provider, protocol, financial model or compliance policy.

## Pending decisions requiring founder review

| ID | Decision | Status | Evidence/next action |
|---|---|---|---|
| ADR-001 | Production frontend/backend framework and whether to retain the repository's current Vite-based setup | Proposed / unresolved | Audit actual repository files, package scripts and deployment configuration first |
| ADR-002 | Database and ORM | Proposed / unresolved | Compare ownership, geospatial needs, privacy, backups, migration and operational cost |
| ADR-003 | Authentication provider and passkey/OAuth combination | Proposed / unresolved | Threat model username, passkey, sessions, recovery and account deletion |
| ADR-004 | Messaging protocol selection | Proposed / unresolved | Run XMTP browser proof of concept; assess Waku separately; verify current security and recovery constraints |
| ADR-005 | Mail launch semantics and SMTP scope | Proposed / unresolved | Decide internal-only Mail scope; SMTP requires separate operational/abuse controls |
| ADR-006 | Seller subscription and monetization launch scope | Proposed / unresolved | Approve pricing, currency, tax, refund, chargeback and payment provider rules before money movement |
| ADR-007 | Partner margin and promoter/referral policy | Proposed / unresolved | Approve attribution, fraud controls, holding period, reversals, payout and legal/tax treatment |
| ADR-008 | Verification provider, document policy, retention and launch jurisdictions | Proposed / unresolved | Legal/privacy review and provider due diligence before collecting sensitive evidence |
| ADR-009 | Maps/location provider and precise geospatial behavior | Proposed / unresolved | Decide consent, location precision, radius semantics, retention and lazy-loading strategy |
| ADR-010 | PWA push and offline guarantees | Proposed / unresolved | Verify target browser/platform support before user-facing guarantees |
| ADR-011 | First-release wallet/blockchain scope | Proposed / unresolved | Confirm user value, custody model, chain, SIWE, fees, legal and security review |
| ADR-012 | Default language/localization policy | Proposed / unresolved | Confirm launch languages and localization ownership |
| ADR-013 | Legal entity, terms, privacy policy, dispute and takedown process | Proposed / unresolved | Obtain jurisdiction-specific legal review |

## Change control

For each accepted ADR, add date, context, options, decision, consequences/trade-offs, status and approver. Do not rewrite history; mark old decisions superseded when the founder approves a replacement. Keep implementation status in `docs/PHASE_STATE.md` separate from decision status.
