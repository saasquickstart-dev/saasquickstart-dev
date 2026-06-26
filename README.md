# SaaSQuickStart

<!-- Update the badge URLs below to point to your own repository -->
[![CI](https://github.com/your-org/your-repo/actions/workflows/ci.yml/badge.svg)](https://github.com/your-org/your-repo/actions/workflows/ci.yml)
[![Go Report Card](https://goreportcard.com/badge/github.com/your-org/your-repo)](https://goreportcard.com/report/github.com/your-org/your-repo)

**A complete, production-ready SaaS foundation — fork it and ship your product.**

SaaSQuickStart is a complete, production-ready SaaS foundation built entirely through conversation with [Claude Code](https://claude.ai/claude-code). It gives you multi-tenant account management, authentication, role-based access control, white-label branding, Stripe billing, API keys, outgoing webhooks, a full admin interface, system health monitoring, credit-based usage tracking, and product analytics with telemetry — everything you need to launch a SaaS business, ready to customize for your specific product.

The bottleneck for building software isn't engineering capacity anymore — it's imagination. SaaSQuickStart proves it: a single person with a clear vision and an AI agent can stand up what used to require a team and months of work. And because it was built with [Claude Code](https://claude.ai/claude-code), the codebase is fork-ready for agentic engineering — point an AI agent at it and keep building your product through conversation.

**[Project Page](https://saasquickstart.dev/saasquickstart)**

---

## Why SaaSQuickStart Exists

Every SaaS product needs the same boring foundation: user accounts, teams, roles, authentication, admin dashboards, billing, usage limits, branding, webhooks, API keys. Historically, building that foundation meant weeks of plumbing before you could write a single line of your actual product.

SaaSQuickStart eliminates that. Fork it, point an AI agent at it, and start building your product on top of a foundation that already handles:

- Multi-tenant isolation with role-based access
- JWT authentication with refresh token rotation
- Google, GitHub, and Microsoft OAuth integration
- Magic link passwordless authentication
- Email OTP — 6-digit sign-in codes delivered via email (no password, no magic link click required)
- MFA/TOTP with recovery codes
- Passkeys (WebAuthn) — biometric and hardware key authentication
- Email verification and password resets
- Team invitations and member management
- Provider-agnostic billing (Stripe or LemonSqueezy) with subscriptions, per-seat pricing, trials, and credit bundles
- Plan entitlements and billing enforcement middleware
- White-label branding with custom themes, logos, landing pages, and custom pages
- API key authentication (admin and user scopes) with expiry dates and per-key call tracking
- Outgoing webhooks with 19 event types and HMAC-SHA256 signing
- Inbound webhook endpoints — receive events from third-party services (GitHub, Stripe, etc.) with HMAC-SHA256 signature verification and a full event log
- Per-tenant branding overrides — tenants customize their own app name, logo, colors, and support email on top of the global white-label theme
- Guest tokens — generate short-lived, unauthenticated links scoped to a specific resource for secure external sharing; wired to document sharing out of the box
- OAuth2 connected apps — tenants register OAuth2 client credentials (client\_id/secret) to allow third-party integrations to authenticate against the platform
- Document approval workflow — submit, approve, and reject tenant documents with role-gated state transitions
- Generic comment threads — attach a comment thread to any resource type using a single collection; ships with a ready-made React component
- Per-user notification preferences — in-app and email channel toggles per event type, with sensible defaults and a settings UI
- Per-tenant feature flags — admin toggles named boolean flags per customer without a redeploy; readable in frontend via a React Query hook
- Credit-based usage tracking (subscription + purchased buckets)
- Promotion codes and coupon management via Stripe
- Product analytics dashboard (conversion funnel, KPIs, retention cohorts, engagement metrics)
- Telemetry event system with Go SDK and REST API for custom event tracking
- Public waitlist with admin management, CSV export, and anonymous traffic analytics (no external services)
- Public pricing page (`/pricing`) with live plan data, annual discount callout, and no-auth access
- 50+ free SEO tool pages at `/tools/*` (calculators, converters, generators) to drive organic search traffic — add new ones by registering a single entry in `registry.ts`
- Fully mobile-responsive — all admin, customer, and auth pages adapt to mobile viewports with Sheet-based navigation drawers
- Cookie consent banner (GDPR-ready, configurable message, `localStorage` persistence)
- Google Analytics 4 integration (configurable Measurement ID via branding admin, no redeploy needed)
- Legal page routing (`/terms`, `/privacy`) that resolves to external URLs or custom page slugs
- ToS acceptance tracking at signup (version-stamped on the user record, config-driven gate)
- Avatar upload with object storage (R2/S3/MongoDB fallback)
- Email marketing preferences opt-in/out per user
- Cancellation survey modal with reason capture before subscription cancellation
- Payment failed transactional email triggered automatically by Stripe/LemonSqueezy webhook
- In-app notification center — Bell icon dropdown with real-time unread count, mark-as-read, and relative timestamp
- Support chat widget — Intercom, Crisp, or Tawk.to embed with user identity pre-fill, configured from the admin branding panel
- A full admin interface for managing everything
- Built-in API documentation (HTML and Markdown)
- Real-time system health monitoring
- Financial metrics dashboard (revenue, ARR, DAU, MAU)
- Multi-provider object storage (Cloudflare R2, AWS S3, or MongoDB fallback) for public CDN assets and private per-tenant documents
- Durable background job queue (MongoDB-backed, no Redis) with worker pool, exponential backoff, and REST API
- Recurring cron schedules (5-field cron expressions, per-timezone) that re-enqueue jobs automatically
- Server-Sent Events (SSE) for real-time job status push to connected clients
- MCP (Model Context Protocol) server for AI-powered admin access
- CLI tools for server administration
- Auto-versioning with database migrations
- Production deployment on Fly.io

This is open-source infrastructure for the agentic era of software — where the person with the idea is also the person who ships it. The codebase follows consistent patterns that AI agents navigate fluently, so you can keep evolving it the same way it was built.

---

## How It Compares

If you're evaluating SaaS boilerplates, you've probably looked at ShipFast, Supastarter, MakerKit, SaaS Pegasus, and Gravity. Here's why technical founders choose SaaSQuickStart instead.

**Free and open-source.** ShipFast costs $169, MakerKit runs $199–599, Supastarter starts at $299, SaaS Pegasus charges $249/year, and Gravity is under $1K. SaaSQuickStart is MIT-licensed — fork it, ship it, never pay a license fee. You own the code completely.

**Go backend, not another Next.js project.** ShipFast, Supastarter, MakerKit, and Gravity are all JavaScript/TypeScript stacks. SaaS Pegasus uses Django. SaaSQuickStart pairs a Go backend with a React + TypeScript frontend — giving you compiled-binary deployment, low memory footprint (a 14MB Alpine container), and the concurrency model that Go is known for. If your SaaS will handle real traffic or you want a backend that isn't a Node.js monolith, this matters.

**Genuine multi-tenancy.** ShipFast has no multi-tenancy at all. SaaS Pegasus and Gravity offer basic team features but not true tenant isolation. SaaSQuickStart gives you full multi-tenant architecture: tenant-scoped data isolation, three-tier RBAC (owner/admin/user), team invitations, ownership transfer, per-tenant activity logs, and per-tenant billing. This is the difference between "users can collaborate" and "each customer gets their own isolated workspace."

**White-label branding built in.** Most boilerplates give you a theme toggle at best. SaaSQuickStart includes a full white-label system: custom app name, logo, colors, fonts, landing page, custom pages, CSS injection, favicon, configurable navigation with entitlement gating, and auth page customization. If you're building a platform where customers see your brand (not yours-plus-a-framework), this saves weeks.

**Outgoing webhooks, not just Stripe webhooks.** None of the alternatives — ShipFast, Supastarter, MakerKit, SaaS Pegasus, or Gravity — include an outgoing webhook system. SaaSQuickStart ships with 19 event types across billing, team lifecycle, user lifecycle, credits, and security events, with HMAC-SHA256 signing, delivery tracking, and test events. Your customers can integrate with your platform from day one.

**API keys with scoped access.** ShipFast, Supastarter, and MakerKit don't include API key management. SaaSQuickStart provides `lsk_`-prefixed API keys with admin and user authority scopes, SHA-256 hashed storage, and last-used tracking — ready for your customers to build integrations.

**Health monitoring and financial dashboards.** No competing boilerplate includes system health monitoring. SaaSQuickStart collects CPU, memory, disk, HTTP, and MongoDB metrics every 60 seconds across all nodes, with 8 real-time charts, threshold alerting, and 30-day retention. The financial dashboard gives you revenue, ARR, DAU, and MAU time-series out of the box.

**Product analytics with telemetry.** No competing boilerplate includes product analytics. SaaSQuickStart auto-instruments the customer journey — visitor → signup → plan page → checkout → paid conversion → upgrade — and visualizes it as a conversion funnel. The PM dashboard includes SaaS KPIs (MRR, ARR, ARPU, LTV, churn rate, trial conversion), retention cohort analysis, engagement metrics (DAU/WAU/MAU for paying subscribers), and a custom event explorer. A Go SDK and REST API let you track your own events with zero configuration.

**MCP server for AI-native operations.** This is unique to SaaSQuickStart. A built-in Model Context Protocol server with 33 read-only tools lets you connect Claude (or any MCP-compatible AI) directly to your running application. Query your ARR trend, investigate error spikes, audit API keys, or review system health — all in natural language. No other SaaS boilerplate offers agentic admin access.

**Built for AI-assisted development.** SaaSQuickStart was built entirely through conversation with Claude Code, and the codebase is designed to keep being built that way. Consistent patterns, clear naming, and a structure AI agents navigate fluently. Fork it, point an agent at it, describe your product, and keep going. The competing boilerplates were built for manual development — SaaSQuickStart is built for the way software is made now.

| | SaaSQuickStart | ShipFast | Supastarter | MakerKit | Pegasus | Gravity |
|---|---|---|---|---|---|---|
| **Price** | **Free (MIT)** | $169 | $299+ | $199–599 | $249/yr | <$1K |
| **Stack** | Go + React | Next.js | Next.js / Nuxt | Next.js | Django | Node + React |
| **Multi-Tenancy** | Full RBAC + custom roles | — | ✓ | ✓ | Teams only | Teams only |
| **Custom Domains** | Per-tenant routing | — | — | — | — | — |
| **White-Label** | Full | — | Partial | Partial | — | — |
| **Webhooks** | Outgoing (19 events) + Inbound | — | — | — | — | — |
| **API Keys** | Scoped + expiry + call tracking | — | — | — | Basic | — |
| **Health Monitoring** | 8 charts | — | — | — | — | — |
| **Product Analytics** | 5-tab PM dashboard | — | — | — | — | — |
| **Credit System** | Dual buckets | — | — | Basic | — | — |
| **Job Queue** | Durable, no Redis | — | — | — | — | — |
| **Object Storage** | R2/S3/DB fallback | — | — | — | — | — |
| **MCP Server** | 33 tools | — | — | — | — | — |
| **Free SEO Tools** | 50+ pages | — | — | — | — | — |
| **Mobile Responsive** | Full | Partial | Partial | Partial | Partial | Partial |
| **Admin Dashboard** | Full | — | ✓ | ✓ | ✓ | Basic |
| **Stripe Billing** | Full | ✓ | ✓ | ✓ | ✓ | ✓ |

---

## Features

### Authentication & Identity
- Email/password registration with bcrypt hashing
- Email verification via [Resend](https://resend.com) + welcome email sent automatically on first verification
- Google, GitHub, and Microsoft OAuth with automatic account linking
- **Google One Tap** — browser-native sign-in prompt (FedCM); auto-prompts on login/signup pages when Google OAuth is configured; same `GOOGLE_CLIENT_ID`, no extra setup; JWT credential verified server-side via JWKS with 1-hour in-process cache; MFA-enabled users are redirected to the MFA form seamlessly
- Magic link passwordless login via email
- **Email OTP** — 6-digit sign-in codes sent via Resend; single-use, 10-minute expiry, invalidates prior unused codes; enabled per-tenant via `auth.email_otp.enabled` config key
- MFA/TOTP two-factor authentication with setup wizard
- Recovery codes for MFA backup access
- **Passkeys (WebAuthn)** — register device biometrics or hardware keys; authenticate without passwords; full registration/login/delete lifecycle using the W3C WebAuthn spec (`go-webauthn/webauthn`)
- JWT access tokens (30min) + refresh tokens (7 days) with rotation
- Account lockout after failed login attempts
- Password reset flow with secure tokens
- Password strength enforcement with real-time visual indicator on signup and password change
- **ToS acceptance tracking** — when `legal.tos_version` configstore key is set, signup requires checkbox consent; version and timestamp stamped on the user record
- Session management — list active sessions, revoke individual or all sessions
- Session revocation on password change

### Multi-Tenancy
- Root tenant (system admin) + customer tenants
- Users belong to tenants via memberships
- Roles: **owner**, **admin**, **user** with hierarchical permissions
- Team invitations with email notifications
- Ownership transfer between members
- Per-tenant activity log
- Tenant settings self-service

### Billing & Credits (Stripe or LemonSqueezy)

Billing is abstracted behind a provider interface — switch between Stripe and LemonSqueezy with a single config key (`BILLING_PROVIDER=stripe|lemonsqueezy`). Stripe is the default; LemonSqueezy requires no external SDK (stdlib HTTP only).

- **Subscription plans** with monthly and annual billing (configurable annual discount %)
- **Pricing models**: flat-rate, per-seat (with included seats, min/max seat limits), or **one-time/lifetime** (pay once, permanent access via Stripe `mode=payment`); per-seat plans enforce `maxSeats` at invite time and return `SEAT_LIMIT_REACHED` (403); lifetime holders are blocked from switching to recurring plans (`LIFETIME_PLAN_LOCKED` 409)
- **Free trials** with configurable trial days per plan and trial abuse prevention
- **Credit bundles** for one-time purchases
- **Dual credit buckets**: subscription credits (reset or accrue) + purchased credits
- **Checkout** (redirect-based) for payment collection — Stripe Checkout or LemonSqueezy checkout
- **Customer portal** for self-service (payment methods, invoices) — Stripe Billing Portal or LemonSqueezy
- **Multi-currency support** with configurable default currency
- **Stripe Tax** automatic tax calculation (Stripe only)
- **Promotion codes and coupons** — create and manage via admin UI, linked to Stripe
- **Invoice generation** — sequential invoice numbers, PDF download, tax breakdown
- **Transaction history** — per-tenant and admin-wide with search and filtering
- **Financial metrics** — revenue, ARR, DAU, MAU time-series with charting
- **Billing enforcement middleware** — blocks `past_due` and `canceled` subscriptions from paid features; `canceling` (cancel-at-period-end) and `none` (free) pass through; configurable dunning grace window (`billing.dunning_grace_days`) lets `past_due` tenants retain access for N days before being blocked
- **Five-state billing lifecycle** — `none` → `active` → `canceling` (grace period, full access retained) → `canceled`; `past_due` on payment failure with `pastDueSince` timestamp for accurate dunning; each state surfaces distinctly in the billing UI
- **Subscription reactivation** — owners can reverse a scheduled cancellation (`canceling` → `active`) from Settings → Billing before the period ends; Stripe-only (LemonSqueezy surfaces via customer portal)
- **Proration preview** — before an active subscriber switches plans, a modal shows the prorated charge or credit for the remainder of the billing period; falls back to direct checkout for providers that don't support preview
- **Cancellation survey** — modal on the billing settings page prompts subscribers for a cancellation reason before confirming; reason stored on the tenant record
- **Payment failed email** — automatic transactional email sent via Resend when a webhook `payment.failed` event is received, with a direct link to the customer portal
- **Entitlement middleware** — gate features based on plan (boolean and numeric entitlements)
- **Billing waiver** for special accounts (root tenant, demo accounts)
- **Admin subscription management** — cancel, modify, reassign plans
- **Refund and dispute handling** — webhook handlers for `charge.refunded`, `charge.dispute.created`, `charge.dispute.closed` (Stripe); order refunds (LemonSqueezy)

### White-Label Branding

> **Scope:** White-label means your app looks and feels like your brand — name, logo, colors, fonts, custom pages. Custom domain routing (e.g. `app.clientA.com` per tenant) is also supported — see the Custom Domains section below.

- Custom app name, tagline, and logo (text, image, or both modes)
- Theme colors (primary, accent, background, surface, text) with auto-generated shade palettes
- Custom fonts (body and heading)
- Custom landing page with configurable HTML
- Custom pages served at `/p/{slug}` with SEO metadata
- Custom CSS injection
- Custom head HTML injection (analytics, meta tags)
- Favicon upload
- Media library for image/asset management
- Configurable navigation sidebar with entitlement-gated items
- Auth page customization (login/signup headings and subtext)
- Dashboard HTML customization
- Open Graph image support
- **Legal page routing** — set `termsUrl` and `privacyUrl` in branding; `/terms` and `/privacy` routes auto-redirect to external URLs, internal custom pages, or a slug-based fallback
- **Cookie consent banner** — GDPR-ready banner enabled via `cookieConsentEnabled` branding flag; configurable message; consent persisted in `localStorage`; shows "Learn more" link when `privacyUrl` is set
- **Public pricing page** — `/pricing` renders live plan data (no auth required); responsive grid, "Most popular" badge, feature list, annual discount callout, and footer legal links
- **Support chat widget** — Intercom, Crisp, or Tawk.to embed configured from the Branding editor; script injected for all authenticated pages; pre-fills user name, email, and ID for identity verification
- **Google Analytics 4** — paste a `G-XXXXXXXXXX` Measurement ID in Admin → Branding → Analytics; gtag.js loads automatically on all pages (public + authenticated) with no redeploy; pair with the cookie consent banner for GDPR compliance

### API Keys
- Create API keys with `lsk_` prefix
- Two authority levels: **admin** (auto-resolves root tenant) and **user** (requires X-Tenant-ID)
- SHA-256 hashed storage — raw key shown only at creation
- Optional expiry date — keys automatically stop working after expiration
- Per-key call counter — tracks total API calls made with each key
- Last-used timestamp tracking
- Admin UI for key management
- Supports both JWT and API key authentication on all endpoints

### Outgoing Webhooks
- 19 event types across 5 tiers:
  - **Billing**: subscription.activated, subscription.canceled, payment.received, payment.failed
  - **Team lifecycle**: member.invited, member.joined, member.removed, member.role_changed, ownership.transferred
  - **User lifecycle**: user.registered, user.verified, user.deactivated
  - **Credits & billing**: credits.purchased, plan.changed, tenant.created, tenant.deactivated
  - **Audit & security**: user.deleted, tenant.deleted, api_key.created, api_key.revoked
- HMAC-SHA256 payload signing with `whsec_`-prefixed secrets
- Delivery tracking with response codes, response bodies, and duration
- Test event delivery
- Secret regeneration
- Event type filtering per webhook
- **Durable retry queue** — failed deliveries are persisted to MongoDB and retried with exponential backoff; state survives server restarts

### Inbound Webhooks
- Tenant-owned endpoints that receive events from third-party services (GitHub, Stripe, Slack, etc.)
- HMAC-SHA256 signature verification with a per-endpoint secret — invalid signatures are rejected before processing
- Full event log with payload, headers, status, and timestamp — 90-day TTL auto-cleans old events
- Status tracking: `received`, `processed`, `failed`, `ignored`
- Full REST API: create/list/update/delete endpoints, list/get/retry individual events
- Endpoint token in the URL path (e.g. `/api/inbound/webhooks/{token}`) — no auth required, security comes from the HMAC secret

### Guest Tokens
- Generate short-lived, unauthenticated access links scoped to a specific resource (document, record, etc.)
- Configurable TTL: 1–720 hours; tokens expire automatically via MongoDB TTL index
- SHA-256 hashed storage — raw token shown only at creation
- Scope and resource ID metadata let your handlers validate what the token grants access to
- Full REST API: create, list, revoke (`/api/tenant/guest-tokens/*`)
- **Wired to Documents** — the Share button on Documents creates a guest token and generates a `/share/document/:token` link; `GET /api/public/documents/:token` and `/download` serve the file without auth

### Comments
- Generic per-resource comment thread — attach a comment thread to any entity (documents, jobs, or any future resource type) using a `resourceType` + `resourceId` composite key
- No separate setup per resource — one collection, any model
- Author or admin/owner can delete; owners of other comments get 403
- Full REST API: list (with optional search), create, delete (`/api/tenant/comments`)
- Frontend `<CommentThread resourceType="document" resourceId={id} />` component with relative timestamps, avatar initials, and Ctrl+Enter submit

### Notification Preferences
- Per-(user, tenant) preferences for each event type across two channels: in-app and email
- 7 built-in event types: `document.approved`, `document.rejected`, `member.invited`, `job.completed`, `job.failed`, `billing.payment_failed`, `announcement.new`
- New event types auto-appear on GET via default merge — existing stored prefs are never lost
- Upserted atomically — safe to PATCH partial updates
- Settings tab at `/settings?tab=notifications` with a Switch grid (event × channel)

### Feature Flags (Per-Tenant)
- Admin can toggle named boolean flags per customer tenant without a code deploy
- Flag names validated to `^[a-zA-Z0-9_]{1,60}$`; stored as `featureFlags map[string]bool` on the Tenant document
- Root admin endpoints: `GET /api/admin/tenants/:id/feature-flags` (read) + `PUT` (write)
- Frontend `useAdminFlag(tenantId, flagName)` hook — React Query backed, reads from the admin endpoint

### Custom Domains

- Tenants can map any bare hostname (e.g. `app.clientA.com`) to their workspace
- **DNS TXT verification** — set the domain, add a `_saasqs-verify.` TXT record returned by the API, then call verify; the domain only goes live after the TXT lookup passes
- Unique sparse index prevents two tenants from claiming the same domain
- **Public bootstrap endpoint** (`GET /api/tenant-by-domain`) — resolves tenantId from the HTTP Host header; SPAs served from a custom domain call this on first load to discover their tenant without any hardcoded IDs
- Verified domains are cached in the tenant middleware (30-second TTL) with immediate invalidation on removal
- Owner-only management (`POST /tenant/settings/domains`, `POST /tenant/settings/domains/verify`, `DELETE /tenant/settings/domains`)

### Custom RBAC (Tenant-Defined Roles)

- Tenants can define named roles beyond the built-in owner/admin/user hierarchy
- 12 permissions available: `billing`, `manage_members`, `manage_api_keys`, `manage_webhooks`, `manage_settings`, `view_audit_log`, `manage_documents`, `manage_schedules`, `manage_connected_apps`, `manage_guest_tokens`, `manage_jobs`, `manage_branding`
- **Strict mode**: user-level members without a custom role are blocked from gated routes by default; owners and admins always pass through
- Roles are tenant-scoped — no role leaks across tenants; `tenantId` is enforced in every query
- Delete is blocked (409) when members are assigned; unassign first
- `RequirePermission(perm)` middleware enforces RBAC on all gated tenant routes: api-keys, webhooks, inbound webhooks, jobs, documents, cron schedules, guest tokens, connected apps, and audit log — 8 subrouters in total
- **PermissionGate** frontend component (`<PermissionGate permission="key">`) wraps page content and shows a clear "Access restricted" message when a member lacks the permission — distinct from the plan-tier `<EntitlementGate>` which shows an upgrade prompt; always wrap PermissionGate outside EntitlementGate so permission denial takes precedence
- Auto-migration creates an "All Access" role per tenant and assigns it to all existing user-level members to preserve existing access on upgrade
- Full REST API: `GET/POST /tenant/roles`, `PUT/DELETE /tenant/roles/{roleId}`, `PATCH /tenant/members/{userId}/custom-role`

### OAuth2 Connected Apps
- Tenants register OAuth2 client credentials so third-party integrations can authenticate against your platform
- Auto-generated `oa_`-prefixed client IDs and `oas_`-prefixed secrets; secrets are SHA-256 hashed, raw value shown only at creation
- Secret preview (first 8 chars + `...`) for identification without exposing the full secret
- Secret regeneration — invalidates the old secret and returns a new one
- Full REST API: create, list, get, update, delete, regenerate secret (`/api/tenant/oauth-apps/*`)
- Permission-gated via `manage_connected_apps` — owners and admins always pass through; user-level members need the permission in their custom role

### Object Storage
- Provider-agnostic `Store` interface — swap between Cloudflare R2, AWS S3, and MongoDB fallback with a single config change, no code changes
- **Public assets** (logos, favicons, media library) — served via CDN URL with 301 redirect; legacy MongoDB blobs still served for backward compatibility
- **Private tenant documents** — per-tenant namespace (`documents/{tenantId}/{docId}`), download via 15-minute presigned GET (302 redirect)
- **Visibility control** — `tenant` (all members) or `owner` (uploader only)
- **Document approval workflow** — documents can be submitted for review; admins approve or reject with role-gated state transitions (`draft → pending_review → approved / rejected`)
- Full REST API: upload, list, get metadata, download (presigned), delete, submit/approve/reject
- Health check wired into the integration dashboard — misconfigured credentials surface at startup
- MongoDB fallback for zero-config local development; no object store credentials required

### Background Job Queue
- Durable MongoDB-backed job queue — no Redis, no extra infrastructure
- Atomic `findOneAndUpdate` claim prevents double-execution across concurrent workers
- N-worker pool (default 5) with per-job 4-minute execution timeout
- Exponential backoff on retry: 30s base → 1h ceiling
- Stale lock reclaim on startup and every 5 minutes (crash recovery)
- `Handler` interface (`Type() string`, `Execute(ctx, job) error`) — register product job types at startup
- **Job chaining** — set `ChainNext` on a job to automatically enqueue the next job when the current one completes successfully
- Full REST API: list, enqueue, get, cancel, retry (`/api/tenant/jobs/*`)
- 30-day TTL auto-cleans completed and cancelled jobs

### Recurring Scheduled Tasks (Cron)
- Recurring schedules backed by the job queue — no Redis, no separate scheduler infrastructure
- Standard 5-field cron expressions with per-schedule timezone support
- Distributed atomic claim — multiple nodes compete safely, each schedule fires exactly once per tick
- Stale lock reclaim every 5 minutes for crash recovery
- Full REST API: list, create, update, delete, pause, resume
- Paused schedules recompute `nextRunAt` on resume (no missed-fire backlog)

### Server-Sent Events (SSE)
- Real-time push channel for background job status — no polling required
- In-memory tenant-scoped pub/sub hub; non-blocking publish skips slow clients
- MongoDB change stream watcher on the jobs collection — cross-node delivery regardless of which node ran the job
- Graceful fallback when change streams are unavailable (standalone local MongoDB)
- 30-second heartbeat keeps connections alive through reverse proxies
- Events: `job.completed`, `job.failed`, `job.dead` with full payload
- No pre-built frontend consumer — wire `EventSource` in your product code (see [Use SSE](#fork-it-and-keep-building-with-ai) in the Fork guide)

### Admin Interface
- **Dashboard** with user/tenant counts, health overview, and business metrics
- **User management** — list, search, view profiles, edit, suspend, impersonate, delete with ownership preflight
- **Tenant management** — list, view, edit, plan assignment, status control, subscription management
- **Financial overview** — transaction history across all tenants, revenue/ARR/DAU/MAU charts
- **Product analytics** — conversion funnel, SaaS KPIs, retention cohorts, engagement metrics, custom event explorer
- **Plan management** — create, edit, archive, entitlements, per-seat configuration, trial days
- **Credit bundle management** — create, edit, sort, activate/deactivate
- **Promotions** — create and manage Stripe promotion codes and coupons
- **Branding editor** — theme colors, logos, fonts, landing page, custom pages, CSS, navigation, legal URLs (terms/privacy), cookie consent banner, and support chat widget (Intercom/Crisp/Tawk.to)
- **Per-tenant branding overrides** — individual tenants can customize their own app name, logo, colors, and support email on top of the global white-label theme
- **API key management** — create, view, revoke
- **Webhook management** — create, edit, delete, test, view delivery history
- **Announcements** — publish system-wide announcements
- **System log viewer** with severity filtering, search, and user filtering
- **Error log API** (`GET /api/admin/errors`) — queryable by source (frontend/backend), level, date range, user, and tenant; 7-day hot window before nightly R2 archival
- **Configuration variable editor** (strings, numbers, enums, templates)
- **In-app messaging** — send messages to individual users
- **Root members** — manage the admin team with invitations and role changes
- **CSV export** for users and tenants
- **Admin impersonation** — log in as any user for debugging
- **System health monitoring** (see below)
- **Integration health checks** — MongoDB, Stripe, Resend, Google OAuth status
- Three-tier admin access: **user** (read-only), **admin** (read-write), **owner** (destructive operations)

### System Health Monitoring
- Automatic node registration with heartbeat (30s interval)
- Metrics collection every 60s: CPU, memory, disk, network, HTTP request stats, MongoDB stats, Go runtime
- HTTP metrics middleware with percentile latency tracking (p50/p95/p99)
- Threshold-based alerting (configurable warning/critical levels)
- 30-day automatic data retention via MongoDB TTL indexes
- Real-time dashboard with 8 time-series charts (Recharts)
- Aggregate, all-nodes overlay, and single-node filter modes
- Time range selection: 1h, 6h, 24h, 7d, 30d
- Integration health panel (MongoDB, Stripe, Resend, Google OAuth connectivity)

### In-House Error Logging
- Captures all application errors in MongoDB — both backend 5xx responses and frontend exceptions
- **Backend capture**: `apierror` hook records every 5xx with method, path, error code, user, and tenant automatically
- **Frontend capture**: `ErrorBoundary` and the `getErrorMessage` utility report caught errors (network failures, JS exceptions, React render crashes) via `POST /api/errors`
- **7-day hot window**: errors stay queryable in MongoDB — `GET /api/admin/errors` supports filtering by source, level, date range, user, and tenant
- **Nightly archival**: a cron job at 2 AM UTC exports logs older than 7 days to Cloudflare R2 / S3 as gzipped JSONL (`error-logs/YYYY-MM-DD/archive-*.jsonl.gz`), then deletes them from MongoDB
- Works alongside Sentry — Sentry gets stack traces and grouping; MongoDB gets searchable structured records tied to your user and tenant data
- No extra infrastructure — uses the existing job queue and object storage provider; on local dev (`provider: db`) old logs are simply deleted without uploading

### Product Analytics & Telemetry
- **Conversion funnel** — Visitors → Signups → Plan Page Views → Checkouts → Paid Conversions → Upgrades, with conversion rates at each step
- **SaaS KPIs** — MRR, ARR, ARPU, LTV, churn rate, trial-to-paid conversion rate, median time to first purchase, active subscriber count
- **Retention cohorts** — weekly or monthly cohort retention table with color-coded heatmap (tracks `lastLoginAt` over time)
- **Engagement metrics** — DAU/WAU/MAU for paying subscribers, average sessions per user, top features by usage, credit consumption trend
- **Custom event explorer** — browse all event types, view trend charts, filter by name and time range
- **Telemetry Go SDK** — `telemetry.Track()` / `TrackBatch()` / `TrackPageView()` / `TrackCheckoutStarted()` / `TrackLogin()` for direct in-process event recording (no HTTP overhead)
- **Telemetry REST API** — `POST /telemetry/track` (anonymous, rate-limited) for page views; `POST /telemetry/events` and `/telemetry/events/batch` (authenticated) for custom events
- **Auto-instrumentation** — registration, email verification, login, checkout, subscription activation/cancellation, and plan changes are tracked automatically
- **365-day retention** — telemetry events auto-expire via MongoDB TTL index
- **Rate limiting** — 60 req/min per IP for anonymous tracking, 120 req/min per user for authenticated events

### Waitlist & Public Traffic Analytics

- **Public waitlist** — visitors submit their email (+ optional name) from the landing page; stored with source tag and IP; admin can browse, delete, and export as CSV
- **Anonymous page-view tracking** — `usePublicTracking()` fires a `page.view` telemetry event on every public page load (landing, docs) using a session ID stored in `sessionStorage`; no cookies, no external services
- **Public traffic dashboard** — admin UI at `/admin/traffic` shows total views, daily bar chart, and top-pages table for any lookback window (7–90 days), powered by MongoDB aggregation on the existing telemetry collection

### Free SEO Tool Pages

50+ client-side tools at `/tools/*` designed to rank on Google and drive organic traffic to your product. Each tool is a standalone React page wrapped in a shared `<ToolLayout>` that injects `SoftwareApplication` JSON-LD structured data, canonical URLs, and meta descriptions automatically.

- **Categories:** Developer (Base64, Diff Checker, Cron Builder, Curl Builder, UUID Generator, Color Contrast), Business (Churn Calculator, A/B Test Calculator, ARR/MRR calculators), AI/LLM tools, and more
- **Adding a new tool:** add one entry to `frontend/src/pages/tools/registry.ts` — no route registration needed, no `App.tsx` edits; the route and the tools index card are generated automatically
- **Internal linking:** every tool page links to `/pricing` and the signup page via `<ToolLayout>`, driving conversion from organic visitors
- **SEO utilities:** `injectJsonLd()`, `setMetaDescription()`, `setCanonical()` from `@/utils/seo.ts` handle metadata lifecycle with React cleanup

### User Self-Service
- Profile editing (display name, email)
- **Avatar upload** — profile picture upload from the Settings profile tab; stored in object storage (R2/S3/MongoDB fallback); displayed across the app
- **Email preferences** — marketing email opt-in/out toggle on the profile tab; preference stored on the user record
- **In-app notification center** — Bell icon in the nav bar opens an inline dropdown showing recent messages with unread indicator, body preview, and relative timestamp; mark individual or all messages as read without leaving the page
- **Workspace rename** — tenant owners can rename their workspace from the Settings profile tab; change propagates immediately across the app header and nav
- Theme preference (light/dark)
- Password management
- MFA setup and management
- Passkey management (register, list, delete)
- Session viewer with remote revocation
- Account deletion with data cleanup
- Data export (GDPR-friendly)
- Billing management (plan selection, credit purchases, invoice history, PDF download)
- Onboarding flow

### Built-in API Documentation
- Interactive HTML API reference at `/api/docs` with expandable endpoint details
- Markdown API reference at `/api/docs/markdown` for integration in external docs
- Comprehensive webhook event reference with payload descriptions
- Auto-versioned from the VERSION file

### CLI Administration
- `saasquickstart setup` — Initialize the system (create root tenant + owner)
- `saasquickstart start` / `stop` / `restart` — Server process management
- `saasquickstart change-password` — Reset any user's password
- `saasquickstart send-message` — Send system messages to users
- `saasquickstart transfer-root-owner` — Transfer root tenant ownership
- `saasquickstart config list|get|set` — Manage configuration variables
- `saasquickstart stripe register-webhook` — Register or update the Stripe webhook endpoint with all required events (prints signing secret on first run)
- `saasquickstart version` — Show binary and database versions
- `saasquickstart status` — Check system health
- `saasquickstart mcp` — Start the MCP server (see [MCP Server](#mcp-server-ai-admin-access) below)

### MCP Server (AI Admin Access)

A built-in [Model Context Protocol](https://modelcontextprotocol.io) server gives AI assistants like Claude read-only access to your admin data — dashboards, users, tenants, financials, logs, health, and more. Useful for asking questions like "what's our ARR trend?" or "show me critical logs from the last hour" in natural language.

- **33 read-only tools** across 14 categories — no write operations, safe by design
- **2 resources** — `saasquickstart://dashboard` and `saasquickstart://health` for automatic context
- **API key authentication** — requires a root-tenant API key, same auth as the admin API
- **Stdio transport** — runs locally, compatible with Claude Desktop and Claude Code

**Tool categories:**
- **About** — software version and environment
- **Dashboard** — user/tenant counts, health overview
- **Tenants** — list with filtering, detailed view with members
- **Users** — list with search, detailed view with auth methods and memberships
- **Financial** — transaction history, revenue/ARR/DAU/MAU time-series metrics
- **Logs** — full-text search with severity/category/date filters, severity counts
- **Health** — current system metrics, time-series health data, node list, integration status
- **Config** — list and inspect runtime configuration variables
- **Plans** — plan details, entitlement keys, credit bundles
- **Announcements** — list published and draft announcements
- **Promotions** — Stripe promotion codes with coupon details
- **Security** — API key inventory (previews only), root tenant members
- **Webhooks** — webhook configs, event type reference, delivery history
- **Product analytics** — conversion funnel, SaaS KPIs, retention cohorts, engagement metrics, custom event explorer

### Security
- Security headers (CSP, HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)
- Rate limiting on authentication endpoints
- Request body size limits
- NoSQL injection protection (regex input escaping)
- XSS protection via DOMPurify for injected HTML
- Trusted proxy IP resolution (Fly-Client-IP)
- Webhook signature verification (Stripe inbound, HMAC-SHA256 outbound)
- Idempotent webhook processing via unique event ID index
- System log injection detection with automatic critical alerts
- Refresh token rotation with family-based revocation
- SSRF protection on all outgoing webhook URLs (RFC-1918 + metadata endpoint block)
- MFA brute-force lockout (5 failed attempts locks the challenge)
- OTP brute-force lockout (5 failed attempts locks the one-time code)
- Atomic password reset token upsert (only one active token per user at any time)
- Checkout race-condition guard (duplicate concurrent sessions cancel the losing subscription)
- Per-tenant billing status state machine with explicit canceling/canceled distinction
- Webhook dead-letter replay with re-signing and delivery audit trail
- Custom role updates written to audit log with actor attribution
- CompleteOnboarding is idempotent (duplicate calls return 409, never double-mark)

### Production Ready
- Dockerized multi-stage build (Go + Node + Alpine)
- Fly.io deployment with auto-stop/auto-start machines
- SPA serving from the Go binary (no separate web server needed)
- CORS, security headers, rate limiting
- Graceful shutdown with connection draining
- Auto-versioning with database migration on startup
- Version notification messages to admin users after upgrades

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Go 1.25, gorilla/mux |
| Frontend | React 19, TypeScript, Vite 7, Tailwind CSS 4 |
| Database | MongoDB (Atlas or local) |
| Auth | JWT (access + refresh), bcrypt, Google/GitHub/Microsoft OAuth, Magic Links, Email OTP, TOTP MFA, Passkeys (WebAuthn) |
| Billing | Stripe (stripe-go v82) or LemonSqueezy (stdlib HTTP) — Checkout, Portal, Webhooks, Tax |
| Email | Resend |
| Object Storage | Cloudflare R2, AWS S3 (aws-sdk-go-v2), or MongoDB fallback |
| Job Scheduling | robfig/cron v3 (cron expression parsing) |
| Charts | Recharts |
| Metrics | gopsutil v4 |
| PDF | gofpdf (invoice generation) |
| Security | DOMPurify (frontend), HMAC-SHA256 (webhooks) |
| Deployment | Docker, Fly.io |

---

## Prerequisites

- **Go 1.25+** — [install](https://go.dev/doc/install)
- **Node.js 22+** — [install](https://nodejs.org)
- **MongoDB** — either:
  - [MongoDB Atlas](https://www.mongodb.com/atlas) (free M0 tier works fine)
  - Local MongoDB Community Edition
- **Git**

### Optional
- [Resend](https://resend.com) API key — for email verification, password resets, and invitations
- Google OAuth credentials — for Google sign-in
- GitHub OAuth credentials — for GitHub sign-in
- Microsoft OAuth credentials — for Microsoft sign-in
- [Stripe](https://stripe.com) account — for billing (subscriptions, credit purchases, invoices)
- [Fly.io](https://fly.io) account — for production deployment

---

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/your-org/your-repo.git
cd your-repo
```

### 2. Set up environment

Run the interactive setup script to write a `.env` file and copy the config template:

**macOS / Linux:**
```bash
./scripts/setup.sh
```

**Windows (PowerShell):**
```powershell
.\scripts\setup.ps1
```

Both scripts prompt for your MongoDB URI and optional credentials (Google OAuth, Resend, app name) and auto-generate JWT secrets.

**Manual setup** — skip the script and configure directly:

```bash
# macOS / Linux
cp .env.example .env
cp backend/config/dev.example.yaml backend/config/dev.yaml
```

```powershell
# Windows (PowerShell)
Copy-Item .env.example .env
Copy-Item backend\config\dev.example.yaml backend\config\dev.yaml
```

Open `.env` and fill in at minimum:
```env
DATABASE_NAME=saasquickstart-dev
MONGODB_URI=mongodb://localhost:27017
JWT_ACCESS_SECRET=<any-64-char-random-string>
JWT_REFRESH_SECRET=<a-different-64-char-random-string>
```

### 3. Start everything

The backend auto-loads `.env` from the project root — no manual env export needed.

**Start everything at once (recommended):**

```bash
cd frontend
npm install
npm run dev:all
```

This starts the Go backend (`http://localhost:4290`), the Vite frontend (`http://localhost:4280`), and the Stripe webhook tunnel in parallel. The Stripe tunnel requires the [Stripe CLI](https://stripe.com/docs/stripe-cli) — backend and frontend start normally without it.

**Backend only:**

```bash
cd backend
go run ./cmd/server
```

**Frontend only** (if backend is already running):

```bash
cd frontend
npm run dev
```

### 4. Initialize the system

In a new terminal, create the root tenant and admin account:

```bash
cd backend
go run ./cmd/cli setup
```

The CLI prompts for your organization name, your name, email, and password. Open `http://localhost:4280` and log in with the credentials you just created.

---

## Setting Up Billing

Billing is optional but required for paid subscriptions, credit bundle purchases, and invoice generation. If you skip this section, SaaSQuickStart works as a free-tier-only platform.

Set `BILLING_PROVIDER=stripe` (default) or `BILLING_PROVIDER=lemonsqueezy` in your `.env` file to select the active provider.

### Setting Up Stripe Billing

### 1. Create a Stripe account

Sign up at [stripe.com](https://stripe.com) and complete onboarding. You can use **test mode** during development.

### 2. Get your API keys

Go to **Stripe Dashboard → Developers → API keys** and copy:
- **Publishable key** (starts with `pk_test_` or `pk_live_`)
- **Secret key** (starts with `sk_test_` or `sk_live_`)

### 3. Register the webhook endpoint

**Option A — CLI (recommended):** Once your Stripe secret key and `frontend.url` are configured, run:

```bash
cd backend && go run ./cmd/cli stripe register-webhook
```

This automatically creates the endpoint in your Stripe account with all 8 required events and prints the signing secret. Copy it to `STRIPE_WEBHOOK_SECRET` in your `.env`. Re-running the command is safe — it updates the existing endpoint rather than creating a duplicate.

**Option B — Manual (Stripe Dashboard):** Go to **Stripe Dashboard → Developers → Webhooks → Add endpoint**:

- **Endpoint URL**: `https://your-domain.com/api/billing/webhook`
- **Events to subscribe to** — select these 8 events:
  - `checkout.session.completed`
  - `invoice.paid`
  - `invoice.payment_failed`
  - `customer.subscription.updated`
  - `customer.subscription.deleted`
  - `charge.refunded`
  - `charge.dispute.created`
  - `charge.dispute.closed`

After creating the endpoint, copy the **Signing secret** (starts with `whsec_`).

**For local development:** Use the Stripe CLI to tunnel events to your machine instead of registering a public endpoint:

```bash
stripe listen --forward-to localhost:4290/api/billing/webhook
```

The Stripe CLI prints its own webhook secret — use that as `STRIPE_WEBHOOK_SECRET` while running locally. `npm run dev:all` starts this tunnel automatically if the Stripe CLI is installed.

### 4. Set environment variables

Add these to your `.env` file:

```bash
STRIPE_SECRET_KEY=sk_test_...
STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
```

### 5. Create plans in the admin UI

Once the backend is running with Stripe configured:
1. Log in as the root tenant owner
2. Go to **Admin → Plans** and create your subscription plans
3. Set pricing, billing intervals, trial days, entitlements, and credit allocations
4. Optionally create **credit bundles** under Admin → Credit Bundles
5. Optionally create **promotion codes** under Admin → Promotions

Stripe Products and Prices are created automatically when customers check out — you don't need to configure anything in the Stripe Dashboard beyond the API keys and webhook.

### 6. Go live

When you're ready for production:

**Admin setup (one-time, in the UI):**

1. Log in as root admin, go to **Admin → Branding** and configure:
   - **App Identity** — App Name (replaces "SaaSQuickStart" everywhere), Support Email, Logo, Favicon
   - **Legal & Compliance** — Terms URL, Privacy URL, Cookie Consent (enable + message for GDPR), and `legal.tos_version` in **Admin → Config** to gate signup on ToS acceptance
   - **Support Chat** — choose Intercom, Crisp, or Tawk.to and enter your Widget/App ID
   - **Analytics** — paste your GA4 Measurement ID (`G-XXXXXXXXXX`) to enable Google Analytics on all pages
2. Go to **Admin → Plans** and verify your plan lineup looks correct before customers can see it

**Stripe (switch to live mode):**

1. Switch to **live mode** in the Stripe Dashboard
2. Run `go run ./cmd/cli stripe register-webhook` against your production URL to create the live webhook endpoint and get its signing secret
3. Update your production environment variables with the live Stripe keys and webhook secret

> **Note:** The seed command (`go run ./cmd/cli seed`) is for development and staging only — never run `--reset` against a production database.

---

## Onboarding Customers

### How tenants are created (PLG model)

There is no "Create Tenant" button in the admin UI — by design. All tenants are created exclusively through the public `/signup` page. This enforces a single source of truth for account creation and keeps the PLG funnel intact.

To manually onboard a client: log out of your admin account, go to `/signup`, and create the account on their behalf using the client's email. Then log back in as root admin, go to **Admin → Tenants**, find their tenant, and assign a plan.

### Multi-tenant vs dedicated deployment

| Approach | When to use |
| --- | --- |
| **Multi-tenant** (recommended) | One instance; all clients are isolated organizations with separate data, teams, and billing |
| **Dedicated deployment** | Client requires absolute data isolation or a custom installation with no shared infrastructure |

For a dedicated deployment: run a second instance with a different `DATABASE_NAME`, run `go run ./cmd/cli setup` to create its root admin, then customize via **Admin → Branding**.

### Stripe lazy provisioning

Plans created in **Admin → Plans** do **not** sync to Stripe immediately. Stripe Products and Prices are created the moment the first customer clicks "Checkout" for that plan — no manual Stripe dashboard configuration needed.

### Setting Up LemonSqueezy Billing

LemonSqueezy is an alternative to Stripe — use it instead of Stripe, not alongside it.

#### 1. Create a LemonSqueezy account and store

Sign up at [lemonsqueezy.com](https://www.lemonsqueezy.com) and create a store. Note your **Store ID** from the store settings URL.

#### 2. Get your API key

Go to **LemonSqueezy → Settings → API** and create a new API key.

#### 3. Create your variants in the LemonSqueezy dashboard

Unlike Stripe (where products are created automatically on first checkout), LemonSqueezy requires you to pre-create products and variants manually in the dashboard. Note the **Variant ID** for each plan interval (monthly/annual).

#### 4. Configure environment variables

```bash
BILLING_PROVIDER=lemonsqueezy
LEMONSQUEEZY_API_KEY=eyJ...
LEMONSQUEEZY_STORE_ID=12345
LEMONSQUEEZY_WEBHOOK_SECRET=your-webhook-secret
```

#### 5. Set variant IDs on plans

After creating plans in **Admin → Plans**, set the LemonSqueezy variant IDs on each plan's `providerIds` field via the API:

```json
{
  "providerIds": {
    "lemonsqueezy_plan_month": "123456",
    "lemonsqueezy_plan_year": "123457"
  }
}
```

#### 6. Register the LemonSqueezy webhook

In the LemonSqueezy dashboard go to **Settings → Webhooks** and add an endpoint:

- **URL**: `https://your-domain.com/api/billing/webhook`
- **Events**: `order_created`, `subscription_created`, `subscription_updated`, `subscription_cancelled`, `subscription_payment_success`, `subscription_payment_failed`
- Copy the **Signing secret** to `LEMONSQUEEZY_WEBHOOK_SECRET`.

### ⚠️ LemonSqueezy Integration Status — Pending Full Review

The LemonSqueezy billing path is **partially implemented**. The provider interface, checkout flow, and webhook event normalization are wired up, but the integration has not been end-to-end tested and contains known gaps that must be resolved before using it in production.

#### Known Gaps

**Webhook signature verification (Critical)**
The webhook handler reads the `Stripe-Signature` header regardless of which provider is active. LemonSqueezy sends its signature in `X-Signature`. Until this is fixed, all LemonSqueezy webhooks fail with "invalid signature" — meaning checkout completions, payment failures, and subscription updates are never processed.

**`billingCustomerID` never stamped after checkout**
LemonSqueezy's `GetOrCreateCustomer` returns the user's email as a placeholder (not a real customer ID). After checkout, the tenant's `billingCustomerID` field is left empty. Subsequent refund and dispute lookups (which search tenants by `billingCustomerID`) will silently miss all LS customers. The real customer ID must be extracted from the `order_created` webhook and written to the tenant.

**Credit bundle purchases return 500**
Bundle checkout calls `GetOrCreatePrice` directly, which returns `ErrNotSupported` for LemonSqueezy. Any LS user clicking "Buy Credits" receives a generic 500 error. The bundle purchase path needs to be routed through `resolvePriceID` (which checks `plan.ProviderIDs` first) or gated with a provider capability check returning a clear 422.

**Duplicate financial transaction on first subscription payment**
LemonSqueezy's webhook normalizer does not populate `BillingReason` on the `subscription_payment_success` event. The deduplication guard in `handleInvoicePaid` (which skips `billing_reason == "subscription_create"`) never fires for LS, causing the first payment to be recorded twice: once via `handleCheckoutCompleted` and again via `handleInvoicePaid`.

**Seat reconciliation silently skipped**
The `seat_reconciliation` job takes a raw Stripe service reference and returns `nil` immediately when `h.stripe == nil` (i.e. when LS is active). Seat drift on per-seat LS plans accumulates with no log output and no reconciliation.

**Subscription reactivation not supported**
`POST /api/billing/reactivate` returns `ErrNotSupported` for LemonSqueezy. The frontend falls through to the customer portal URL. The frontend handles this gracefully, but users cannot reactivate a canceling subscription without leaving the app.

**Proration preview not supported**
`POST /api/billing/proration-preview` returns `ErrNotSupported` for LemonSqueezy. The frontend falls through to a new checkout session. This means LS subscribers see no charge preview before confirming a plan change.

**Promotions / coupons admin UI is Stripe-only**
The `/admin/promotions` page and all related API endpoints call Stripe coupon/promotion-code APIs directly. There is no LemonSqueezy equivalent wired.

**Cross-tenant checkout security check bypassed on guest orders**
If a LemonSqueezy order does not include a `customer_id` (guest checkout), `be.CustomerID` is empty and the cross-tenant customer verification check is skipped. Forged `tenantId` metadata on a guest order could activate a plan on an arbitrary tenant. Require `customer_id` to be present on all plan checkout events, or disable guest checkout on the LS variant.

#### What Does Work (Stripe-Equivalent)

- Checkout session creation (redirect to LS checkout page)
- `order_created` → subscription activation (plan assigned, credits set)
- `subscription_updated` → plan/interval sync
- `subscription_cancelled` → downgrade to free plan
- `subscription_payment_failed` → `past_due` status + in-app message
- Customer portal redirect (LS customer portal)
- Variant ID mapping via `plan.providerIds`

#### Resolution Checklist

Before using LemonSqueezy in production, address the following in order:

- [ ] Fix webhook signature header: add `SignatureHeader() string` to `billing.Provider`, return `"X-Signature"` for LS
- [ ] Stamp `billingCustomerID` from `order_created` webhook payload
- [ ] Route bundle checkout through `resolvePriceID` or return a 422 with a clear "not supported" message
- [ ] Populate `BillingReason` on LS `subscription_payment_success` normalizer to prevent duplicate transactions
- [ ] Log a warning (not silent nil) when seat reconciliation is skipped due to missing Stripe client
- [ ] Add E2E tests covering the complete LS checkout → subscription → payment-failure → cancellation lifecycle

---

## Configuration

Config files live in `backend/config/`:

- `dev.example.yaml` / `prod.example.yaml` — committed templates
- `dev.yaml` / `prod.yaml` — your actual configs (gitignored)

Set `APP_ENV=dev` or `APP_ENV=prod` to select which config to load. Defaults to `dev`.

Secrets are referenced as `${ENV_VAR}` in YAML and expanded from environment variables at load time. Default values use `${VAR:default}` syntax.

### Environment Variables

| Variable | Required | Description |
|----------|----------|------------|
| `DATABASE_NAME` | Yes | Project identity — shared name = shared user base |
| `MONGODB_URI` | Yes | MongoDB connection string |
| `JWT_ACCESS_SECRET` | Yes | Secret for signing access tokens |
| `JWT_REFRESH_SECRET` | Yes | Secret for signing refresh tokens |
| `FRONTEND_URL` | Yes | Frontend URL for CORS and email links |
| `APP_NAME` | Yes | Your application name (used in emails, UI) |
| `BILLING_PROVIDER` | No | Billing provider: `stripe` (default) or `lemonsqueezy` |
| `STRIPE_SECRET_KEY` | No | Stripe secret API key |
| `STRIPE_PUBLISHABLE_KEY` | No | Stripe publishable key (sent to frontend) |
| `STRIPE_WEBHOOK_SECRET` | No | Stripe webhook signing secret |
| `LEMONSQUEEZY_API_KEY` | No | LemonSqueezy API key (required when `BILLING_PROVIDER=lemonsqueezy`) |
| `LEMONSQUEEZY_STORE_ID` | No | LemonSqueezy store ID |
| `LEMONSQUEEZY_WEBHOOK_SECRET` | No | LemonSqueezy webhook signing secret |
| `GOOGLE_CLIENT_ID` | No | Google OAuth client ID |
| `GOOGLE_CLIENT_SECRET` | No | Google OAuth secret |
| `GOOGLE_REDIRECT_URL` | No | Google OAuth redirect URL |
| `RESEND_API_KEY` | No | Resend email service API key |
| `FROM_EMAIL` | No | Sender email address (default: noreply@yourdomain.com) |
| `FROM_NAME` | No | Sender name (default: SaaSQuickStart) |
| `OBJECTSTORE_PROVIDER` | No | Object store provider: `r2`, `s3`, or `db` (default: `db` — stores in MongoDB) |
| `OBJECTSTORE_ACCESS_KEY` | No | R2/S3 access key ID |
| `OBJECTSTORE_SECRET_KEY` | No | R2/S3 secret access key |
| `OBJECTSTORE_BUCKET` | No | R2/S3 bucket name |
| `OBJECTSTORE_PUBLIC_URL` | No | Public CDN URL for the bucket (e.g. `https://cdn.yourdomain.com`) |
| `OBJECTSTORE_ACCOUNT_ID` | No | Cloudflare account ID (R2 only) |
| `OBJECTSTORE_REGION` | No | AWS region (S3 only, e.g. `us-east-1`) |
| `SENTRY_DSN` | No | Sentry DSN for backend error tracking |
| `VITE_SENTRY_DSN` | No | Sentry DSN exposed to the React frontend bundle |

### Email Template Customization

All transactional email subjects and HTML bodies are overridable at runtime via the admin config panel (`/admin/config`) without a redeploy. The configstore keys follow the pattern `email.<type>.subject` and `email.<type>.body`. Templates use Go's `html/template` syntax with double-brace variables.

| Template key | Variables available |
|---|---|
| `email.verification.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.VerifyURL}}` |
| `email.password_reset.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.ResetURL}}` |
| `email.magic_link.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.MagicLinkURL}}` |
| `email.otp.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.OTPCode}}` |
| `email.invitation.subject` / `.body` | `{{.AppName}}`, `{{.InviterName}}`, `{{.TenantName}}`, `{{.InviteURL}}` |
| `email.welcome.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.DashboardURL}}` |
| `email.payment_failed.subject` / `.body` | `{{.AppName}}`, `{{.DisplayName}}`, `{{.PortalURL}}` |

If a config value is empty or contains an invalid template, the hardcoded fallback HTML is used — so the system degrades gracefully, never silently failing to send.

---

## Project Structure

```
saasquickstart/
  backend/
    cmd/
      server/main.go              Entry point (HTTP server, route wiring)
      saasquickstart/main.go            CLI administration tool + MCP server
    config/                       YAML config files
    internal/
      api/handlers/               HTTP handlers (auth, admin, tenant, billing, branding, webhooks, etc.)
      apicounter/                  API call counters for integration health
      auth/                       JWT, password hashing, Google/GitHub/Microsoft OAuth, TOTP MFA
      config/                     Config loader with env variable expansion
      cache/                      Generic in-memory TTL cache (used by tenant middleware hot path)
      configstore/                Runtime configuration (DB-backed, in-memory cache, change stream sync)
      cron/                       Recurring schedule scheduler (atomic claim, robfig/cron expressions)
      db/                         MongoDB connection, collections, indexes, JSON Schema validation
      email/                      Resend email service with templates
      errorlog/                   In-house error log service (capture, list, archive to R2)
      events/                     Internal event emitter (drives webhook deliveries)
      health/                     System health monitoring service
      jobs/                       Durable background job queue (MongoDB-backed, worker pool)
      middleware/                  Auth, tenant, RBAC, rate limiting, metrics, security, billing enforcement
      models/                     All data models
      objectstore/                Provider-agnostic object storage (R2, S3, MongoDB fallback)
      planstore/                  Plan seeding
      sse/                        Server-Sent Events hub and MongoDB change stream watcher
      stripe/                     Stripe service (Checkout, Billing Portal, Customers, Prices, Subscriptions)
      syslog/                     System logging service with injection detection
      telemetry/                  Telemetry event collection, Go SDK, and PM analytics queries
      version/                    Version management and auto-migration
  frontend/
    src/
      api/client.ts               Axios API client with token refresh
      components/                 Layout (with notification center), AdminLayout, BrandingThemeInjector, CookieConsentBanner, PasswordStrength, SupportChatWidget, shared components
      contexts/                   Auth, Tenant, Branding, and Theme React contexts
      pages/
        admin/                    Admin interface (dashboard, users, tenants, plans, billing, branding, etc.)
        admin/health/             Health monitoring components and charts
        app/                      Customer-facing pages (dashboard, billing, team, settings, activity)
        app/settings/             User settings tabs (profile, security, MFA, sessions, billing, API keys, webhooks)
        auth/                     Login, signup, MFA challenge, magic link, verification, password reset
        public/                   Landing page, pricing page, legal pages (/terms, /privacy), custom pages
      types/index.ts              TypeScript type definitions
  scripts/
    setup.sh                      Interactive setup script (macOS / Linux)
    setup.ps1                     Interactive setup script (Windows PowerShell)
  Dockerfile                      Multi-stage production build
  fly.toml                        Fly.io deployment config
  VERSION                         Current version number
```

---

## API Documentation

SaaSQuickStart includes built-in, self-hosted API documentation:

- **Interactive HTML reference**: `GET /api/docs` — expandable endpoint cards with request/response examples
- **Markdown reference**: `GET /api/docs/markdown` — for embedding in external documentation

The documentation is generated from code and always matches the running version. It covers all endpoints, parameters, request/response formats, and all 19 webhook event types with payload descriptions.

---

## MCP Server Setup

The MCP server lets AI assistants query your admin data in natural language. It proxies read-only requests to the SaaSQuickStart admin API using an API key.

### Prerequisites

1. A running SaaSQuickStart instance (local or deployed)
2. A root-tenant API key — create one in **Admin → API Keys** with **admin** authority

### Usage with Claude Desktop

Add to your Claude Desktop config file:

- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`
- **Linux**: `~/.config/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "saasquickstart": {
      "command": "/path/to/saasquickstart",
      "args": ["mcp"],
      "env": {
        "SQS_URL": "https://your-app.fly.dev",
        "SQS_API_KEY": "lsk_your_api_key_here"
      }
    }
  }
}
```

### Usage with Claude Code

Add to your project's `.mcp.json`:

```json
{
  "mcpServers": {
    "saasquickstart": {
      "command": "/path/to/saasquickstart",
      "args": ["mcp"],
      "env": {
        "SQS_URL": "https://your-app.fly.dev",
        "SQS_API_KEY": "lsk_your_api_key_here"
      }
    }
  }
}
```

### Build the CLI binary

```bash
cd backend
go build -o saasquickstart ./cmd/cli
```

### Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SQS_URL` | Yes | Base URL of the SaaSQuickStart instance (e.g. `http://localhost:4290` or `https://your-app.fly.dev`) |
| `SQS_API_KEY` | Yes | Root-tenant API key with admin authority (starts with `lsk_`) |

### Available Tools (33)

| Tool | Description |
|------|-------------|
| `get_about` | Software version and environment |
| `dashboard_stats` | User/tenant counts and health overview |
| `list_tenants` | Paginated tenant list with search and filters |
| `get_tenant` | Detailed tenant with plan, billing, and members |
| `list_users` | Paginated user list with search and filters |
| `get_user` | Detailed user with auth methods and memberships |
| `list_transactions` | Financial transactions with search and filters |
| `get_financial_metrics` | Revenue, ARR, DAU, MAU time-series |
| `search_logs` | Full-text log search with severity/category/date filters |
| `get_log_severity_counts` | Log counts by severity level |
| `get_system_health` | Current CPU, memory, disk, HTTP stats |
| `get_health_metrics` | Time-series health data (per-node or aggregate) |
| `list_nodes` | Server nodes with status and version |
| `get_integrations` | Third-party integration health |
| `list_config` | All runtime configuration variables |
| `get_config` | Single config variable details |
| `list_plans` | Subscription plans with pricing and entitlements |
| `get_plan` | Detailed plan info |
| `list_entitlement_keys` | Entitlement key catalog |
| `list_credit_bundles` | Credit bundle pricing |
| `list_announcements` | Published and draft announcements |
| `list_promotions` | Stripe promotion codes and coupons |
| `list_api_keys` | API key inventory (previews only) |
| `list_root_members` | Admin team and pending invitations |
| `list_webhooks` | Outbound webhook configurations |
| `list_webhook_event_types` | Available webhook event types |
| `get_webhook` | Webhook detail with delivery history |
| `get_funnel` | Conversion funnel (visitors → paid) with step rates |
| `get_kpis` | SaaS KPIs: MRR, ARR, ARPU, LTV, churn rate, trial conversion |
| `get_retention` | Weekly or monthly cohort retention table |
| `get_engagement` | DAU/WAU/MAU for paying subscribers, top features |
| `get_custom_events` | Custom event trend by event name and time range |
| `list_event_types` | All tracked telemetry event types |

### MCP Examples

These examples show how the MCP tools work in practice. Each example lists the user prompt and the exact tool calls that execute behind the scenes.

#### Example 1: Check Business Overview

**Prompt:** "How's my SaaS doing today?"

**Tool calls:**
1. `dashboard_stats` — returns a snapshot:
   ```
   Users: 1,284 (12 new today)
   Tenants: 89 (3 new this week)
   Health: All systems healthy
   Active alerts: 0
   ```

#### Example 2: Investigate Revenue Trend

**Prompt:** "Show me our revenue trend for the last 30 days"

**Tool calls:**
1. `get_financial_metrics` — queries time-series data:
   ```json
   { "range": "30d", "metric": "revenue" }
   ```
   Returns daily revenue data points (values in cents) for charting, e.g.:
   ```
   2026-01-27: $1,250.00
   2026-01-28: $890.00
   ...
   2026-02-25: $2,100.00
   ```
2. `get_financial_metrics` — follow up with ARR:
   ```json
   { "range": "30d", "metric": "arr" }
   ```

#### Example 3: Find a Specific Tenant

**Prompt:** "Look up the Acme Corp tenant and show me their details"

**Tool calls:**
1. `list_tenants` — searches by name:
   ```json
   { "search": "Acme Corp" }
   ```
   Returns matching tenants with IDs, plan names, and billing status.
2. `get_tenant` — fetches full details using the tenant ID:
   ```json
   { "id": "6789abc..." }
   ```
   Returns plan info, billing status, credit balances, subscription dates, and a full member list with roles.

#### Example 4: Search for Critical Errors

**Prompt:** "Were there any critical errors in the last hour?"

**Tool calls:**
1. `search_logs` — filters by severity and time:
   ```json
   {
     "severity": "critical",
     "fromDate": "2026-02-26T14:00:00Z",
     "perPage": "50"
   }
   ```
   Returns log entries with timestamps, categories, messages, and metadata. For example:
   ```
   [critical] 14:23:05 billing — Stripe webhook signature verification failed
   [critical] 14:31:12 security — Log injection pattern detected in user input
   ```
2. `get_log_severity_counts` — provides overall distribution:
   ```
   critical: 2, high: 15, medium: 89, low: 342, debug: 1,204
   ```

#### Example 5: Monitor System Health

**Prompt:** "How's the system health? Are all integrations working?"

**Tool calls:**
1. `get_system_health` — returns current metrics:
   ```
   CPU: 12.3%
   Memory: 245 MB / 512 MB (47.8%)
   Disk: 1.2 GB / 8 GB (15.0%)
   HTTP: 1,234 requests (p95 latency: 45ms)
   MongoDB: 12 active connections
   ```
2. `get_integrations` — checks third-party connectivity:
   ```
   MongoDB: healthy (3ms response)
   Stripe: healthy (120ms response, 89 calls/24h)
   Resend: healthy (95ms response, 12 calls/24h)
   Google OAuth: healthy
   ```

#### Example 6: Audit API Key Usage

**Prompt:** "Show me all active API keys and when they were last used"

**Tool calls:**
1. `list_api_keys` — returns inventory (full keys are never exposed):
   ```
   "Production Automation" (admin) — lsk_...a3f2 — last used: 2 hours ago
   "CI/CD Pipeline" (admin) — lsk_...b7e1 — last used: 15 minutes ago
   "Customer Integration" (user) — lsk_...c9d4 — last used: 3 days ago
   "Old Test Key" (admin) — lsk_...d1e5 — last used: never
   ```

#### Example 7: Review Subscription Plans

**Prompt:** "What plans do we offer and how many subscribers does each have?"

**Tool calls:**
1. `list_plans` — returns all plans with pricing and subscriber counts:
   ```
   Starter: $9/mo ($86/yr) — 45 subscribers — 5 seat limit
   Pro: $29/mo ($278/yr) — 31 subscribers — 25 seat limit, per-seat pricing
   Enterprise: $99/mo ($950/yr) — 8 subscribers — unlimited seats
   ```
2. `list_credit_bundles` — shows available credit purchases:
   ```
   Small Pack: 100 credits — $5.00 — active
   Medium Pack: 500 credits — $20.00 — active
   Large Pack: 2000 credits — $60.00 — active
   ```

#### Example 8: Check Webhook Delivery

**Prompt:** "Are our webhooks delivering successfully? Show me the recent history for the production webhook"

**Tool calls:**
1. `list_webhooks` — shows all configured webhooks:
   ```
   "Production" — https://api.example.com/webhooks — 12 events — active
   "Staging" — https://staging.example.com/hooks — 5 events — active
   ```
2. `get_webhook` — fetches delivery history for the production webhook:
   ```json
   { "id": "abc123..." }
   ```
   Returns recent delivery attempts with status codes, response times, and any failures:
   ```
   2026-02-26 14:30:01 — subscription.activated — 200 OK (120ms)
   2026-02-26 14:15:22 — payment.received — 200 OK (95ms)
   2026-02-26 13:45:10 — member.joined — 500 Error (340ms)
   ```

#### Example 9: User Lookup and Membership

**Prompt:** "Find the user with email alice@example.com and show me their tenant memberships"

**Tool calls:**
1. `list_users` — searches by email:
   ```json
   { "search": "alice@example.com" }
   ```
   Returns the matching user with ID, verification status, and last login.
2. `get_user` — fetches full details:
   ```json
   { "id": "def456..." }
   ```
   Returns:
   ```
   Email: alice@example.com (verified)
   Auth: password + Google OAuth
   MFA: TOTP enabled
   Memberships:
     — Acme Corp (owner) — joined 2026-01-15
     — Side Project Inc (admin) — joined 2026-02-10
   Last login: 2 hours ago
   ```

#### Example 10: Health Metrics Deep Dive

**Prompt:** "Show me the CPU and memory trends across all nodes for the last 24 hours"

**Tool calls:**
1. `list_nodes` — identifies all server nodes:
   ```
   node-1 (v1.0.0) — healthy — last seen: 30s ago
   node-2 (v1.0.0) — healthy — last seen: 28s ago
   ```
2. `get_health_metrics` — fetches aggregate time-series data:
   ```json
   { "range": "24h" }
   ```
   Returns data points every 60 seconds with CPU %, memory %, disk %, HTTP request counts, and latency percentiles — ready for charting.
3. `get_health_metrics` — optionally drill into a specific node:
   ```json
   { "node": "node-1", "range": "24h" }
   ```

---

## Deployment

### Fly.io

SaaSQuickStart includes a Dockerfile and Fly.io configuration for production deployment.

**Install flyctl:**

```bash
# macOS / Linux
curl -L https://fly.io/install.sh | sh
```

```powershell
# Windows (PowerShell)
iwr https://fly.io/install.ps1 -useb | iex
```

```bash
# Create the app (first time only)
flyctl apps create your-app-name --org your-org
```

**Set production secrets:**

```bash
# macOS / Linux
flyctl secrets set \
  DATABASE_NAME="your-db-name" \
  MONGODB_URI="mongodb+srv://..." \
  JWT_ACCESS_SECRET="$(openssl rand -hex 32)" \
  JWT_REFRESH_SECRET="$(openssl rand -hex 32)" \
  FRONTEND_URL="https://your-app-name.fly.dev" \
  APP_NAME="YourApp" \
  STRIPE_SECRET_KEY="sk_live_..." \
  STRIPE_PUBLISHABLE_KEY="pk_live_..." \
  STRIPE_WEBHOOK_SECRET="whsec_..." \
  OBJECTSTORE_PROVIDER="db" \
  SENTRY_DSN="https://..." \
  VITE_SENTRY_DSN="https://..."
```

```powershell
# Windows (PowerShell) — generate secrets with built-in crypto
$jwtAccess  = [BitConverter]::ToString([Security.Cryptography.RandomNumberGenerator]::GetBytes(32)) -replace '-',''
$jwtRefresh = [BitConverter]::ToString([Security.Cryptography.RandomNumberGenerator]::GetBytes(32)) -replace '-',''
flyctl secrets set `
  DATABASE_NAME="your-db-name" `
  MONGODB_URI="mongodb+srv://..." `
  JWT_ACCESS_SECRET="$jwtAccess" `
  JWT_REFRESH_SECRET="$jwtRefresh" `
  FRONTEND_URL="https://your-app-name.fly.dev" `
  APP_NAME="YourApp" `
  STRIPE_SECRET_KEY="sk_live_..." `
  STRIPE_PUBLISHABLE_KEY="pk_live_..." `
  STRIPE_WEBHOOK_SECRET="whsec_..." `
  OBJECTSTORE_PROVIDER="db" `
  SENTRY_DSN="https://..." `
  VITE_SENTRY_DSN="https://..."
```

```bash
# Deploy
flyctl deploy
```

The Dockerfile builds both the Go backend and React frontend into a single ~14MB Alpine container. The Go binary serves the frontend SPA directly — no nginx or separate web server required.

### Render

Full guide including environment variable reference, custom domains, and Render vs Fly comparison: [docs/RENDER_DEPLOY.md](docs/RENDER_DEPLOY.md)

### Other Platforms

The Docker image works anywhere containers run. The only external dependency is MongoDB. Set the environment variables listed above and expose port 8080.

---

## Known Limitations

These are real gaps to know before committing to SaaSQuickStart for a product. None are insurmountable, but each requires product work if you need it.

| Limitation | Detail |
| --- | --- |
| **No SSO / SAML / SCIM** | Enterprise clients requiring Okta/Azure AD single sign-on or automated user provisioning are not supported. OAuth social login (Google, GitHub, Microsoft) is not a substitute for SAML IdP federation. |
| **SSE events limited to job status** | The built-in SSE consumer in `TenantContext` forwards `job.completed`, `job.failed`, and `job.dead` events. Adding custom event types requires extending the backend hub and the frontend context. |
| **No Stripe Metered Billing** | Credits are pre-purchased integers. There is no Stripe usage-based billing that charges after the fact per API call or compute unit. |
| **No native mobile billing** | App Store / Play Store in-app purchase is not covered. Works fine for web-only or React Native apps using Stripe Checkout via browser. |
| **No net-30 / invoice billing** | All payments go through Stripe Checkout (card). B2B enterprise deals requiring purchase orders and manual invoicing are outside scope. |
| **No email drip campaigns** | Only transactional emails are wired (verification, password reset, invitation, welcome, payment failed). Automated sequences — trial expiry reminders, win-back campaigns, onboarding drips — require either building on top of the existing cron + Resend stack, or integrating an external tool like Loops.so or Customer.io. |
| **No referral / affiliate system** | No built-in referral codes, attribution tracking, or reward logic. |

---

## Fork It and Keep Building with AI

SaaSQuickStart was built entirely through conversation with [Claude Code](https://claude.ai/claude-code) — every feature, every handler, every component was described in natural language and implemented by an AI agent. But the real point isn't that it *was* built this way — it's that it's designed to *keep* being built this way.

The codebase follows consistent patterns, uses clear naming, and maintains a structure that AI agents navigate fluently. Fork it, point Claude Code at it, and start describing your product. The agent already understands the patterns — authentication, tenancy, billing, middleware, events — and builds on top of them naturally. You're not starting from scratch; you're continuing a conversation.

Here's what's already wired up for you:

1. **Add your product's data models** in `backend/internal/models/`
2. **Add API handlers** in `backend/internal/api/handlers/`
3. **Wire routes** in `backend/cmd/server/main.go`
4. **Add frontend pages** in `frontend/src/pages/`
5. **Use the tenant context** — every authenticated request carries the user's tenant, so your product logic gets multi-tenancy for free
6. **Use the credit system** — check and deduct credits for usage-based features
7. **Use entitlements and RBAC** — gate backend routes with both `tenantMiddleware.RequireEntitlement("feature_name")` and `tenantMiddleware.RequirePermission(models.PermManageXxx)`; wrap frontend pages with `<PermissionGate permission="key"><EntitlementGate entitlement="key">` (permission is always the outer wrapper); add the feature to `featureRegistry.ts` so nav items and settings tabs are filtered automatically
8. **Use the config store** — add runtime-configurable settings without redeployment
9. **Use the event emitter** — emit events from your handlers and they'll automatically be delivered to configured webhooks
10. **Use API keys** — your endpoints automatically support both JWT and API key authentication
11. **Use the branding system** — your UI inherits the white-label theme automatically via the BrandingContext
12. **Use the telemetry system** — track custom events with `telemetry.Track()` in Go or `POST /telemetry/events` from external clients, and they'll automatically appear in the PM dashboard
13. **Use the job queue** — enqueue background work with `jobQueue.Enqueue(ctx, &models.Job{Type: "your_job", TenantID: tenant.ID, Payload: ...})` and implement a `Handler` interface to process it
14. **Use cron schedules** — create recurring jobs via `POST /api/tenant/cron-schedules` with a cron expression, timezone, and job type; the scheduler re-enqueues them automatically
15. **Use SSE** — `TenantContext` already opens a `GET /api/tenant/events/stream` connection when authenticated and forwards `job.completed`, `job.failed`, and `job.dead` events as DOM custom events. Use the `useSSEEvent(eventName, handler)` hook in any component to react to job completions without polling
16. **Use object storage** — upload files via `POST /api/tenant/documents` and download via presigned redirect; configure `OBJECTSTORE_PROVIDER=r2` or `s3` in production, `db` for local dev with no extra setup
17. **Use inbound webhooks** — create endpoints via `POST /api/tenant/inbound-webhook-endpoints`; receive events at `/api/inbound/webhooks/{token}` and process them in your handlers with HMAC-SHA256 signature verification already handled
18. **Use guest tokens** — issue short-lived resource links via `POST /api/tenant/guest-tokens`; validate the token in your handler by checking scope, resource ID, and expiry
19. **Use OAuth2 connected apps** — tenants register client credentials via `POST /api/tenant/oauth-apps`; validate `client_id` / `client_secret` pairs in your OAuth2 token endpoint by looking up the app and comparing the SHA-256 hash of the presented secret

### AI Development Slash Commands

The repository ships 17 Claude Code slash commands in `.claude/commands/`. They are invoked by typing `/command-name` in the Claude Code chat and load a structured, codebase-specific checklist as context for that task. Every command is grounded in real bugs, production incidents, and architecture rules from this codebase — not generic advice.

**Invoke any command by typing its name in the Claude Code chat.**

| Command | When to use |
|---|---|
| `/new-feature` | Starting any new feature — full 13-step checklist covering R1–R8 architecture rules, entitlement + permission gates, route mirroring in `testhelpers_test.go`, `featureRegistry.ts` for nav/settings, build gates |
| `/frontend-component` | Building any React component — shadcn primitives, `data-testid` format, `aria-label`, `Label`+`htmlFor` pairing, hooks-before-returns, `getErrorMessage`, `toast` not `alert()`, `TableSkeleton`, `EmptyState`, `Dialog` not `ConfirmModal` |
| `/frontend-page` | Adding a new page/route — correct layout per page type (admin/app/public/settings/tool), `lazyWithRetry` vs bare `lazy()`, `PermissionGate` + `EntitlementGate` wrapping, `featureRegistry.ts`, public dark-mode pattern, sitemap entry |
| `/frontend-api` | Connecting frontend to backend APIs — `api/client.ts` only (never `fetch()`), `/api` baseURL (never prefix), React Query `useQuery`/`useMutation`, `useListFilters` for paginated lists, `getErrorMessage` in all catch blocks, `useNavigation()` ban |
| `/e2e-test` | Writing Playwright tests — `loginAs` not UI login (rate limiter), `waitForResponse` before `page.goto` (the networkidle race), `getByTestId` not `getByRole('tab')` for `<Button>`, seed account billing states, `canceling` ≠ `canceled` |
| `/code-review` | Reviewing a diff — `apierror.InternalWithError` grep, goroutine context detachment, tenant isolation queries, MongoDB index upgrade pattern, TypeScript `as any` bans, shadcn table enforcement, `lazyWithRetry` requirement |
| `/security-review` | Security audit before release — tenant isolation filter audit, middleware chain verification, input validation, error leakage, webhook HMAC, rate limit coverage, secrets in config |
| `/migration` | Writing a DB migration — VERSION bump (silent failure mode), idempotency requirement, `DropOne` before unique index upgrades (the `verification_tokens` deploy incident), expand-contract pattern |
| `/qa` | Verifying a feature before marking done — all user roles × all billing states, empty states, pagination rollback, concurrent actions, E2E timing patterns, pre-deploy checklist |
| `/billing` | Any billing change — 3-file Stripe event sync (`provider.go` + `stripe/service.go` + `webhook.go`), entitlements in ALL 4 plans, billing status state machine, `ErrNotSupported` graceful degradation |
| `/job-handler` | Adding a background job — idempotency contract (`job.Result` for external IDs), register before `jobQueue.Start()`, use `ctx` not `context.Background()`, `NilObjectID` for system-level cron schedules |
| `/webhook` | Adding an outgoing webhook event — 3-file pattern: `EventType` in `emitter.go`, `WebhookEventType` + `AllWebhookEventTypes` + `ValidWebhookEventType` in `models/webhook.go`, case in `dispatcher.go` |
| `/seed` | Adding test seed accounts — `SeedTag` on every inserted doc, manifest struct types, TypeScript getters in `fixtures/seed.ts`, what can't be seeded (real Stripe subs, OAuth accounts) |
| `/deploy` | Before every production deployment — Stripe `sk_live_` vs `sk_test_` check, VERSION file guard, Docker build verification, Render PORT conflict note, Fly.io `-c fly.saas.toml` requirement, rollback procedures |
| `/debug` | Something is broken in production — `/admin/error-logs` first, `/admin/health`, `go run ./cmd/cli doctor`, Sentry stack traces, MongoDB Atlas monitoring, Stripe webhook delivery log |
| `/hotfix` | Emergency production fix — which corners are safe to cut (skip E2E suite), which are never safe (`go build`, `tsc --noEmit`), commit message template with root-cause and follow-up fields |
| `/onboarding` | New developer or new machine setup — ordered sequence: `setup.ps1` → MongoDB replica set (not standalone) → `npm install` → `dev:all` → `cli setup` → `seed`, common error messages with fixes |

Commands are committed to `.claude/commands/` and available to everyone on the team without any setup beyond having Claude Code installed.

---

## Privacy Policy

SaaSQuickStart is self-hosted software — you control your database, your hosting, and your data. The MCP server connects to your SaaSQuickStart instance via the HTTP API using read-only tools — no data is transmitted to SaaSQuickStart.dev or any third party.

For the full privacy policy, see: https://www.saasquickstart.dev/saasquickstart-privacy-policy

---

## License

[MIT](LICENSE) - Copyright 2026 SaaSQuickStart
