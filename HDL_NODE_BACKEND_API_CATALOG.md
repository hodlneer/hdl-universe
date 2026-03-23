# HDL Node Backend API Catalog

## Workspace Summary

This repository is not a single-service codebase. It is an HDL ecosystem workspace centered on the live HDL.fun platform, with the active system split across:

- [`hdl_react`](/Users/hodlneer/hdl_world/hdl_react): the main frontend
- [`hdl-node-backend-api`](/Users/hodlneer/hdl_world/hdl-node-backend-api): the main backend API
- [`hdl-terraform`](/Users/hodlneer/hdl_world/hdl-terraform): infrastructure and deployment

Around those, the repo also contains:

- product and implementation docs
- backlog and feature planning material
- migration records
- AI/MCP workflow configuration
- archived and legacy projects kept for reference

At a product level, HDL.fun appears to be a crypto-social platform built around the idea of handle-based identity and wallet-linked user experiences. The platform combines:

- social posting and feeds
- user profiles and onboarding
- messaging and notifications
- crypto project discovery and recommendations
- blog/content surfaces
- media upload and asset delivery
- wallet-oriented login and crypto-facing UX

## Workspace Tree

```text
hdl_world/
├── hdl_react/                 # Main HDL frontend, Next.js 15 + React 19
│   ├── src/app/               # App Router pages: wallet, feed, chat, onboarding, news, profile
│   ├── src/components/        # UI, wallet, feed, social, profile, onboarding components
│   ├── public/                # Static assets, videos, images
│   ├── tests/ e2e/            # Test suites
│   └── scripts/               # Asset generation and support scripts
├── hdl-node-backend-api/      # Main HDL backend, NestJS + TypeORM + PostgreSQL
│   ├── src/auth*/             # JWT + Google/Facebook/Twitter/Apple auth
│   ├── src/posts/             # Posts, comments, reactions
│   ├── src/messages/          # Messaging
│   ├── src/conversations/     # Conversations
│   ├── src/notification/      # Notifications
│   ├── src/users/             # Users and profiles
│   ├── src/discover/          # Discovery/recommendations
│   ├── src/assets/ src/files/ src/s3/  # Media/storage
│   ├── src/database/          # Migrations and seeds
│   └── test/ tests/           # Backend tests
├── hdl-terraform/             # HDL infrastructure
│   ├── environments/hdl-production/
│   └── modules/{frontend,backend,shared,discovery,hdl_assets_cdn}/
├── docs/                      # Wallet specs, implementation and testing docs
├── backlog/                   # Pending features and onboarding specs
├── mcp/                       # MCP configs/docs for AI-assisted workflows
├── development_tools/         # Autonomous agent framework and related tooling
├── DO_Migration/              # DigitalOcean migration records and deployment history
├── assets/ marketing/ nft/    # Design/media/content assets
├── archive/ archived_projects/
│   └── legacy and deprecated projects, experiments, backups
├── legacy_projects/           # Older hodlneer frontends/backends/terraform
├── scripts/                   # Cross-project scripts
└── hdl wallet ui/             # Screenshot/reference folder, not app code
```

## Frontend Summary

The live frontend is [`hdl_react`](/Users/hodlneer/hdl_world/hdl_react), a Next.js 15 + React 19 application using the App Router. It appears to be both:

- a consumer-facing marketing/landing experience
- the primary authenticated product UI

Key frontend responsibilities:

- rendering public pages and app routes
- onboarding and authentication flows
- feed, profile, chat, wallet, notifications, and discovery UI
- media-heavy homepage and brand presentation
- integration with the HDL backend API
- frontend-side crypto and wallet UX

The important frontend structure is:

- `src/app`: route-level pages such as wallet, feed, chat, onboarding, news, and profile
- `src/components`: reusable UI and feature components
- `src/services`: frontend API/service wrappers
- `public`: static images, media, and assets
- `tests` and `e2e`: automated coverage

Operationally, this is the main application shell an end user interacts with.

## Backend Summary

The live backend is [`hdl-node-backend-api`](/Users/hodlneer/hdl_world/hdl-node-backend-api), a NestJS + TypeORM + PostgreSQL API that serves as the main product backend for HDL.fun.

Key backend responsibilities:

- authentication and user/session identity
- user profiles and onboarding persistence
- posts, comments, reactions, likes, and feed behavior
- messaging and conversations
- notification persistence and realtime delivery
- recommendations and crypto preference tracking
- crypto project metadata and market-data-related endpoints
- file upload, asset access, and media pipeline support
- blog/content integration

It is both a REST API and a Socket.IO backend.

## Infrastructure Summary

The infrastructure layer is [`hdl-terraform`](/Users/hodlneer/hdl_world/hdl-terraform). It defines the HDL deployment stack separately from older Hodlneer infrastructure and includes:

- production environment definitions
- frontend and backend hosting modules
- shared networking and persistence modules
- discovery-related infrastructure
- HDL asset CDN support

This is the deployment and environment-management side of the live app.

## Whole-App Summary

The easiest way to think about the full system is:

- `hdl_react` is the product surface
- `hdl-node-backend-api` is the product brain and data layer
- `hdl-terraform` is the runtime/deployment layer

The platform itself is not just a wallet application. It is better described as a crypto-social application with wallet-oriented identity and crypto ecosystem features layered into:

- account onboarding
- social posting
- messaging
- content discovery
- notification systems
- media handling
- crypto project tracking

There is also visible historical drift in the workspace:

- older Hodlneer naming still appears in places
- some legacy or archived projects are preserved for reference
- migration and deployment history spans AWS-era and later DigitalOcean work

For engineering purposes, the current “live app” center of gravity is:

- frontend: [`hdl_react`](/Users/hodlneer/hdl_world/hdl_react)
- backend: [`hdl-node-backend-api`](/Users/hodlneer/hdl_world/hdl-node-backend-api)
- infra: [`hdl-terraform`](/Users/hodlneer/hdl_world/hdl-terraform)

## HDL Backend Integration Plan (Node / NestJS)

### Purpose

This section outlines the changes required to integrate the existing `hdl-node-backend-api` codebase with the new HDL canon architecture.

The goal is to support:

- handle-based identities
- proof and badge systems
- multi-wallet routing
- identity anchor migration

without immediately modifying the live repository.

The recommended path is a set of database schema additions and API endpoints that bring the current HDL platform into alignment with the broader world-engine vision.

### Architectural Additions

#### 1. Identity Anchor And Handle Mapping

Recommended new entities:

- `UserHandle`
  - stores the canonical `hdl.fun` handle and an optional legacy alias for each user
  - the legacy domain should exist only for backward compatibility during migration
  - forward brand direction should be HDL
  - suggested fields:
    - `id`
    - `userId` (FK)
    - `username`
    - `legacyDomain`
    - `canonicalDomain`
    - `migrated`
    - timestamps

- `UserWallet`
  - stores multiple blockchain addresses tied to a user
  - decouples wallet data from the `User` entity
  - supports expansion beyond EVM and Solana
  - suggested fields:
    - `id`
    - `userId` (FK)
    - `evmAddress`
    - `solanaAddress`
    - `otherAddresses` (JSON)
    - `isProvisioned`
    - `createdAt`
    - `updatedAt`

Recommended `User` entity changes:

- add wallet and handle relations using `@OneToOne()`
- use eager loading where appropriate so user queries expose handle and wallet directly

Recommended migration plan:

- backfill `UserHandle` rows from existing `userName` values
- for users created before the HDL rebrand, mark `legacyDomain = hodlneer.com`
- provision an empty `UserWallet` row for each user
- initialize `isProvisioned = false` until wallet addresses are attached

#### 2. Proof / Badge System

Recommended new entities:

- `ProofBadge`
  - definition table for badge types such as Claimed, Social, or On-Chain
  - suggested fields:
    - `id`
    - `title`
    - `description`
    - `level`
    - `icon`
    - `createdAt`
    - `updatedAt`

- `UserProof`
  - join table linking users to badges
  - suggested fields:
    - `id`
    - `userId`
    - `proofBadgeId`
    - `dateAwarded`
    - `status`
    - `metadata` (JSON for transaction hashes or social proof links)

Recommended service:

- `ProofService`
  - awards badges
  - validates criteria such as wallet age or social proof
  - upgrades proof levels

Recommended endpoints:

- `GET /proof-badges`
  - list all badge definitions

- `POST /proof-badges`
  - create a new badge definition
  - admin only

- `GET /users/:handle/proofs`
  - list a user’s current proofs

- `POST /users/:handle/proofs`
  - award or upgrade a proof for a user

#### 3. Routing Engine

Recommended service:

- `RoutingService`
  - resolves a handle such as `hdl.fun/@username`
  - resolves a legacy alias such as `hodlneer.com/@username` during transition
  - consults `UserHandle` and `UserWallet`
  - determines the correct chain and address for outgoing transfers

Recommended endpoints:

- `GET /wallets/:handle`
  - returns wallet addresses for a given user handle
  - optional query param `chain` to filter by `evm` or `solana`

- `POST /wallets/send`
  - sends a token from the authenticated user to a recipient handle
  - body:
    - `recipientHandle`
    - `amount`
    - `asset`
    - `chain`
  - the service resolves the recipient’s wallet address and performs the transfer through existing blockchain integrations

#### 4. Migration Support

Recommended endpoints:

- `GET /user/migration-status`
  - returns whether a user has migrated to `hdl.fun` as canonical domain

- `POST /user/migrate-to-hdl`
  - triggers migration
  - issues a new canonical handle
  - sets `migrated = true`
  - updates login and notification preferences
  - retires `hodlneer.com` references on the user profile

#### 5. Admin And Monitoring

Recommended internal admin endpoints protected by role guards:

- `GET /admin/users/:id/wallets`
  - show all wallets tied to a user

- `PUT /admin/proof-badges/:id`
  - edit badge definitions

Recommended operational behavior:

- log all handle resolutions
- log all proof awards
- log all routing events
- add DB indices on:
  - `UserHandle.username`
  - `UserWallet.evmAddress`

### Security Considerations

- Authentication
  - all new endpoints except list-only routes should use JWT authentication
  - use role guards such as `RoleEnum.user` and `RoleEnum.admin` for protected admin flows

- Rate limiting
  - add a NestJS rate-limit guard on wallet send endpoints
  - use this specifically to reduce spam and abuse risk

- Signature verification
  - when awarding on-chain proofs, validate signatures with the existing wallet signature helpers such as:
    - `verifyEvmSignature`
    - `verifyPhantomSignature`

- Migration flags
  - use the `migrated` flag to ensure handle-based routing applies only to users that have completed migration

### Suggested Implementation Phases

#### Immediate (0-2 months)

- implement `UserHandle` and `UserWallet` entities with migrations
- add handle mapping to user creation and update flows
- add read-only `GET /wallets/:handle` for wallet resolution

#### Short Term (2-4 months)

- implement `ProofBadge` and `UserProof` tables and CRUD endpoints
- build `RoutingService` and `POST /wallets/send`
- update auth flows to provision blank wallets and handles on signup

#### Medium Term (4-6 months)

- implement migration endpoints and admin tooling
- add analytics and logging around proof awards and wallet sends
- begin integration testing with frontend updates

#### Long Term (6+ months)

- extend wallet service for multi-sig and broader multi-chain support
- integrate proof upgrades triggered by on-chain activity
- finalize migration to `hdl.fun` as canonical domain
- deprecate `hodlneer.com` identity mapping

### Integration-Plan Summary

This plan does not require immediate replacement of the existing HDL backend shape. Instead, it layers a canon-compatible identity and wallet model onto the current social platform backend.

The practical sequence is:

- normalize user identity around handles
- normalize wallet ownership outside the `User` row
- add proof state as first-class data
- introduce a routing engine for handle-to-wallet resolution
- migrate legacy identity references behind explicit compatibility flags

Done well, this would move the backend from a social API with wallet-adjacent features toward a handle-native identity and routing backend without forcing a full rewrite.

## Overview

This document is a practical engineering reference for [`hdl-node-backend-api`](/Users/hodlneer/hdl_world/hdl-node-backend-api). It combines:

- API architecture and runtime shape
- authentication and authorization model
- serialization and response behavior
- domain model summary
- storage and realtime behavior
- operational caveats
- complete endpoint catalog with method, path, auth, request, and response notes

## API Shape

`hdl-node-backend-api` is a single NestJS application that exposes a versioned REST API plus Socket.IO gateways.

Boot happens in [`src/main.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/main.ts#L39), where it:

- enables global CORS
- sets the global prefix to `api`
- enables URI versioning
- mounts Swagger at `/docs`
- installs a global validation pipe
- registers a WebSocket auth adapter

In practice, most HTTP routes are under `/api/v1/...`, while the root `/` is explicitly excluded from the prefix and serves app info via [`src/home/home.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/home/home.controller.ts#L7).

Module composition is in [`src/app.module.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/app.module.ts#L60). The live API surface is built from:

- `Auth`
- `Users`
- `UserProfile`
- `Posts`
- `Files`
- `CryptoProjects`
- `FollowSystem`
- `Discover`
- `Messages`
- `Conversations`
- `Blogs`
- `Recommendations`
- `Settings`
- `Sms`
- `UserNotificaions`
- `Assets`
- the WebSocket-based `NotificationModule`

There is migration history for wallet tables, but `WalletsModule` is currently commented out in [`src/app.module.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/app.module.ts#L140), so wallet functionality is not presently a first-class Nest module.

## Auth And Security Model

JWT auth is standard bearer-token auth.

The JWT strategy in [`src/auth/strategies/jwt.strategy.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/auth/strategies/jwt.strategy.ts#L11) extracts the bearer token and trusts a payload containing `id` and `role`; it does not hydrate the full user on each HTTP request.

Role enforcement is a thin metadata check in [`src/roles/roles.guard.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/roles/roles.guard.ts#L8) against `request.user.role.id`, so any route using `@Roles(...)` and `AuthGuard('jwt')` is effectively role-gated.

The main auth entrypoints are in [`src/auth/auth.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/auth/auth.controller.ts#L33):

- `POST /api/v1/auth/email/login`
- `POST /api/v1/auth/admin/email/login`
- `POST /api/v1/auth/email/register`
- `POST /api/v1/auth/email/register-onboarding`
- `POST /api/v1/auth/onboarding/steps`
- `POST /api/v1/auth/email/confirm`
- `POST /api/v1/auth/forgot/password`
- `POST /api/v1/auth/reset/password`
- `GET /api/v1/auth/me`
- `PATCH /api/v1/auth/me`
- `DELETE /api/v1/auth/me`
- `GET /api/v1/auth/check-email/:email`
- `POST /api/v1/auth/resend-email-verification`
- `POST /api/v1/auth/google`
- `POST /api/v1/auth/facebook`
- `POST /api/v1/auth/twitter`
- `POST /api/v1/auth/callback`
- `POST /api/v1/auth/verify-wallet`

Behaviorally, the auth service mixes:

- email/password auth
- social auth
- onboarding registration
- wallet-signature login

Password login validates the user, verifies bcrypt, blocks inactive users until email verification, then signs a JWT. Wallet login verifies an EVM or Phantom signature and either finds or creates a user before issuing JWT.

WebSockets use a separate auth path in [`src/adapters/auth.adapter.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/adapters/auth.adapter.ts#L10): the token is expected in `socket.handshake.headers.authorization`, verified directly with `jsonwebtoken.verify`, and then the user entity is loaded from the DB and attached to `socket.user`.

## Serialization And Response Rules

There is a global serializer interceptor in [`src/utils/serializer.interceptor.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/utils/serializer.interceptor.ts#L14) that recursively strips `password`, `hash`, and `previousPassword` from any object tagged as a `User`, using [`src/users/user-response.serializer.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/users/user-response.serializer.ts#L3).

That is the main response sanitization mechanism. It does not appear to provide broader DTO-based response shaping, so many endpoints still return service/entity-shaped payloads.

Pagination is inconsistent but common.

- user lists and post feeds often use the custom `infinityPagination` helper
- comments, messages, and conversations use their own DTO-style pagination shapes

## Core Domain Model

The primary entity is [`User`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/users/entities/user.entity.ts#L39), which carries:

- identity
- auth provider
- role
- status
- handle (`userName`)
- profile
- settings
- favorite crypto projects
- personalities
- followers/following
- tags
- images
- recommendation behavior/cache relations

The rest of the API is built around this user graph.

Main persisted domains from the entities folder:

- Social graph: users, profiles, settings, followers, tags, user-tags
- Content: posts, media files, likes, reactions, comments, replies, comment revisions
- Messaging: conversations, conversation groups, messages, chat attachments
- Notifications: user notifications plus websocket eventing
- Crypto data: crypto projects, tags, categories, onboarding shortlist
- Recommendations: user behavior, user crypto preferences, recommendation cache, content-to-crypto mappings
- Publishing/content feed: saved blogs
- Compliance/content pages: settings table

Migration history in [`src/database/migrations`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/database/migrations) confirms the API grew over time from users/posts into comments, follows, notifications, messaging, recommendations, wallets, reserved usernames, and crypto-logo support.

## HTTP Surface By Area

High-value route families:

- Auth
  Source: [`src/auth/auth.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/auth/auth.controller.ts#L33)
  Covers login/register, onboarding, password reset, self-profile auth endpoints, social auth, wallet auth.

- Users
  Source: [`src/users/users.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/users/users.controller.ts#L37)
  Admin CRUD for users, public user fetch, auth-user feed helpers, theme mode, username validation, reserved username management.

- User Profile
  Source: [`src/user-profile/user-profile-controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/user-profile/user-profile-controller.ts#L35)
  Profile updates, profile/cover image upload and removal, personality CRUD, image filtering.

- Posts
  Source: [`src/posts/posts.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/posts/posts.controller.ts#L49)
  Feed listing, authenticated and public single-post views, create/update/delete post, media upload, comments, replies, likes, reactions, admin trash/revision endpoints.

- Files
  Source: [`src/files/files.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/files/files.controller.ts#L17)
  Generic upload, S3 asset browsing, S3 folder creation, upload-to-folder, and local file download fallback.

- Assets
  Source: [`src/assets/assets.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/assets/assets.controller.ts#L18)
  Media proxying from S3, thumbnail proxying, and assets health check.

- Crypto Projects
  Source: [`src/crypto-projects/crypto-projects.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/crypto-projects/crypto-projects.controller.ts#L24)
  Admin CRUD for projects/tags/categories, onboarding shortlist, market data pulls, CoinGecko update endpoints, logo download/cleanup, and icon-library endpoints for frontend onboarding.

- Discover
  Source: [`src/discover/discover.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/discover/discover.controller.ts#L9)
  Public-ish user discovery and search.

- Messages and Conversations
  Sources: [`src/messages/messages.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/messages/messages.controller.ts#L34), [`src/conversations/conversations.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/conversations/conversations.controller.ts#L25)
  Paginated messages, message create/edit/delete, attachment upload, conversation list/initiate/respond/mark-read/soft-delete.

- Blogs
  Source: [`src/blogs/controllers/blogs/blogs.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/blogs/controllers/blogs/blogs.controller.ts#L22)
  Blog feeds and blog metadata appear to be proxied from Strapi-like content, plus saved-blog functionality.

- Recommendations
  Source: [`src/recommendations/recommendations.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/recommendations/recommendations.controller.ts#L28)
  Authenticated recommendation retrieval, behavior tracking, crypto preference CRUD, user behavior stats, warmup, and article-to-crypto mapping management.

- Notifications
  HTTP source: [`src/user-notificaions/user-notificaions.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/user-notificaions/user-notificaions.controller.ts#L25)
  WebSocket source: [`src/notification/notification.module.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/notification/notification.module.ts#L31)
  HTTP side handles list/count/mark-seen; realtime side broadcasts social and universal notifications.

- Settings
  Source: [`src/settings/settings.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/settings/settings.controller.ts#L14)
  Terms/policy/about/accessibility/user-agreement/cookie-policy/copyright/brand/data-deletion get/set endpoints.

- SMS
  Source: [`src/sms/sms.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/sms/sms.controller.ts#L3)
  Verification-code send and verify only.

## Storage And Media

File storage is dual-mode. [`src/files/files.service.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/files/files.service.ts#L12) chooses between local URLs and S3 based on `FILE_DRIVER`.

The S3 abstraction in [`src/s3/s3.service.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/s3/s3.service.ts#L8) is more important than the generic files service now:

- it scopes asset browsing/uploads under `assets/`
- it can generate branded CDN URLs
- it supports streaming for the assets proxy endpoints

For clients, there are effectively three upload patterns:

- generic `POST /api/v1/files/upload`
- folder-aware asset upload `POST /api/v1/files/upload-to-folder`
- domain-specific multipart upload endpoints like post media, chat attachments, profile images, crypto tag/category/project images

## Realtime Layer

The backend is not HTTP-only.

`NotificationModule` wires both a legacy and enhanced notification gateway, and the enhanced path supports a large normalized notification taxonomy via [`src/notification/universal-notification.service.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/notification/universal-notification.service.ts#L54).

That means a frontend engineer integrating messaging, post interactions, or notifications should treat Socket.IO as part of the backend contract, not an optional extra.

## Operational Facts

The app reads `.env` globally via `ConfigModule`. DB config is assembled in [`src/database/typeorm-config.service.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/database/typeorm-config.service.ts#L8). The DB pool, SSL, entity discovery, and migrations are configured there.

The server also performs a manual raw `pg` connection test before Nest boot in [`src/main.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/main.ts#L13), so bad DB config fails early.

Swagger is mounted at `/docs`, not under `/api/v1/docs`: [`src/main.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/main.ts#L90).

## What An Engineer Should Watch Out For

This API is functional, but it is not consistently hardened.

- Hardcoded fallback secrets and external tokens exist in config: Twitter credentials, OpenAI API key, and Strapi token are embedded in [`src/config/app.config.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/config/app.config.ts#L13). That is a serious secret-management problem.
- CORS is globally open for HTTP and websockets: [`src/main.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/main.ts#L52), [`src/adapters/auth.adapter.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/adapters/auth.adapter.ts#L12).
- There is no visible rate limiting, throttling, helmet, or CSRF layer in boot.
- Several routes appear mislabeled as protected but are not actually guarded. `POST /api/v1/posts/add-uuids` has metadata but no `UseGuards(...)`: [`src/posts/posts.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/posts/posts.controller.ts#L102). The same file leaves `DELETE /api/v1/posts/admin/soft-delete/:id` and `GET /api/v1/posts/admin/trashed/list` unguarded: [`src/posts/posts.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/posts/posts.controller.ts#L385).
- Several write endpoints are public that probably should not be. All `POST /api/v1/settings/*` writes are unauthenticated: [`src/settings/settings.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/settings/settings.controller.ts#L32). The onboarding shortlist mutation endpoints under crypto projects are also public: [`src/crypto-projects/crypto-projects.controller.ts`](/Users/hodlneer/hdl_world/hdl-node-backend-api/src/crypto-projects/crypto-projects.controller.ts#L302).
- The codebase still carries old naming and drift. Swagger title says “Hodlneer Back-end API,” some social auth defaults point at `hodlneer.com`, and the wallet module is disabled while wallet-auth endpoints remain present.

## Bottom Line

An engineer should think of this backend as a broad social-platform API with crypto-specific extensions, not as a cleanly isolated wallet API.

The stable center of gravity is:

- auth
- users
- profiles
- posts
- comments/replies/reactions
- messaging
- notifications
- blogs
- crypto-project metadata
- file/media delivery

The main architectural risks are:

- inconsistent auth coverage
- config/secret hygiene
- drift between documented intent and current module state

## Endpoint Catalog

Base path is `/api/v1` for every controller that declares `version: '1'`.

Exceptions:

- `GET /`
- `GET|POST /mail/*`
- `GET /assets/*`
- `GET /docs`

### Platform / Infra

- `GET /`
  - Auth: none
  - Body: none
  - Response: app info / health-style metadata from home service

- `GET /docs`
  - Auth: none
  - Body: none
  - Response: Swagger UI

- `GET /assets/media/:filename`
  - Auth: none
  - Body: none
  - Response: streamed media file with cache/CORS/security headers

- `GET /assets/thumbnails/:filename`
  - Auth: none
  - Body: none
  - Response: thumbnail stream, falls back to original asset

- `GET /assets/health`
  - Auth: none
  - Body: none
  - Response: assets/S3 health object

### Auth

- `POST /api/v1/auth/email/login`
  - Auth: none
  - Body: `{ email, password }`
  - Response: `{ token, user }`

- `POST /api/v1/auth/admin/email/login`
  - Auth: none
  - Body: `{ email, password }`
  - Response: `{ token, user }` for admin login

- `POST /api/v1/auth/email/register`
  - Auth: none
  - Body: register DTO
  - Response: `{ token, user, message }`

- `POST /api/v1/auth/email/register-onboarding`
  - Auth: none
  - Body: onboarding register DTO
  - Response: `{ token, user }`

- `POST /api/v1/auth/onboarding/steps`
  - Auth: bearer user
  - Body: onboarding steps DTO
  - Response: updated onboarding state

- `POST /api/v1/auth/email/confirm`
  - Auth: none
  - Body: `{ hash }`
  - Response: email confirmation result

- `POST /api/v1/auth/forgot/password`
  - Auth: none
  - Body: `{ email }`
  - Response: password reset initiation result

- `POST /api/v1/auth/reset/password`
  - Auth: none
  - Body: `{ hash, password }`
  - Response: reset result

- `GET /api/v1/auth/me`
  - Auth: bearer
  - Body: none
  - Response: current authenticated user

- `PATCH /api/v1/auth/me`
  - Auth: bearer
  - Body: auth update DTO
  - Response: updated current user

- `DELETE /api/v1/auth/me`
  - Auth: bearer
  - Body: none
  - Response: soft-delete result for current user

- `GET /api/v1/auth/check-email/:email`
  - Auth: none
  - Body: none
  - Response: `{ exists, available }`

- `POST /api/v1/auth/resend-email-verification`
  - Auth: none
  - Body: `{ email }`
  - Response: resend result

- `POST /api/v1/auth/google`
  - Auth: none
  - Body: `{ token }`
  - Response: usually `{ token, user }`, but error handling is weak

- `POST /api/v1/auth/facebook`
  - Auth: none
  - Body: `{ accessToken }`
  - Response: usually `{ token, user }`

- `POST /api/v1/auth/twitter`
  - Auth: none
  - Body: `{ code, codeVerifier }`
  - Response: usually `{ token, user }`

- `POST /api/v1/auth/callback`
  - Auth: none
  - Body: `{ code, codeVerifier, state? }`
  - Response: twitter auth callback result

- `POST /api/v1/auth/verify-wallet`
  - Auth: none
  - Body: `{ walletType, message, signature, walletAddress }`
  - Response: `{ token, user }` after signature verification

- `POST /api/v1/auth/google/login`
  - Auth: none
  - Body: Google login DTO
  - Response: `{ token, user }`

- `POST /api/v1/auth/facebook/login`
  - Auth: none
  - Body: Facebook login DTO
  - Response: `{ token, user }`

- `POST /api/v1/auth/apple/login`
  - Auth: none
  - Body: Apple login DTO
  - Response: `{ token, user }`

- `GET /api/v1/auth/twitter`
  - Auth: passport redirect
  - Body: none
  - Response: redirects to Twitter auth

- `GET /api/v1/auth/twitter/callback`
  - Auth: passport redirect
  - Body: none
  - Response: redirects frontend with JWT in query string

### Users

- `POST /api/v1/users`
  - Auth: bearer admin
  - Body: create user DTO
  - Response: created user

- `POST /api/v1/users/create-user`
  - Auth: bearer admin
  - Body: custom create payload
  - Response: created user/result

- `GET /api/v1/users`
  - Auth: bearer admin
  - Query: `page, limit`
  - Response: paginated users

- `GET /api/v1/users/:id`
  - Auth: bearer admin
  - Body: none
  - Response: user by id

- `GET /api/v1/users/public/:id`
  - Auth: none
  - Body: none
  - Response: public user by id

- `PATCH /api/v1/users/:id`
  - Auth: bearer admin
  - Body: update user DTO
  - Response: updated user

- `DELETE /api/v1/users/:id`
  - Auth: bearer admin
  - Body: none
  - Response: soft-delete result

- `DELETE /api/v1/users/destory/:id`
  - Auth: bearer admin
  - Body: none
  - Response: hard-delete result

- `GET /api/v1/users/trashed/list`
  - Auth: bearer admin
  - Query: `page, limit`
  - Response: paginated soft-deleted users

- `POST /api/v1/users/setting/set-theme-mode`
  - Auth: bearer user
  - Body: theme mode DTO
  - Response: theme-setting result

- `GET /api/v1/users/auth/posts`
  - Auth: bearer user
  - Query: `page, limit`
  - Response: authenticated feed pagination

- `GET /api/v1/users/auth/comments`
  - Auth: bearer user
  - Query: `beforeId, afterId, limit, postId`
  - Response: comments for a post in auth context

- `GET /api/v1/users/auth/comments/replies`
  - Auth: bearer user
  - Query: `beforeId, afterId, limit, commentId`
  - Response: replies in auth context

- `GET /api/v1/users/auth/user/posts`
  - Auth: bearer user
  - Query: `page, limit, id`
  - Response: paginated posts for target user

- `POST /api/v1/users/check-username`
  - Auth: none
  - Body: `{ username }`
  - Response: username validation/availability result

- `GET /api/v1/users/reserved-usernames`
  - Auth: bearer admin
  - Query: `page, limit, category, isActive, search`
  - Response: paginated reserved usernames

- `GET /api/v1/users/reserved-usernames/:id`
  - Auth: bearer admin
  - Body: none
  - Response: reserved username record

- `POST /api/v1/users/reserved-usernames`
  - Auth: bearer admin
  - Body: create reserved username DTO
  - Response: created record

- `PATCH /api/v1/users/reserved-usernames/:id`
  - Auth: bearer admin
  - Body: update reserved username DTO
  - Response: updated record

- `DELETE /api/v1/users/reserved-usernames/:id`
  - Auth: bearer admin
  - Body: none
  - Response: no content

- `POST /api/v1/users/reserved-usernames/:id/release`
  - Auth: bearer admin
  - Body: none
  - Response: release result

- `POST /api/v1/users/reserved-usernames/bulk-import`
  - Auth: bearer admin
  - Body: bulk import DTO
  - Response: import result

### Follow System

- `GET /api/v1/users/followers/follow/:userId`
  - Auth: bearer user
  - Body: none
  - Response: follow result

- `GET /api/v1/users/followers/unfollow/:userId`
  - Auth: bearer user
  - Body: none
  - Response: unfollow result

- `GET /api/v1/users/followers/followers`
  - Auth: bearer user
  - Body: none
  - Response: current user followers

- `GET /api/v1/users/followers/followings`
  - Auth: bearer user
  - Body: none
  - Response: current user followings

### User Profile

- `POST /api/v1/user/profile/`
  - Auth: bearer user
  - Body: user profile DTO
  - Response: updated profile

- `POST /api/v1/user/profile/image/remove`
  - Auth: bearer user
  - Body: `{ type: 'profile'|'cover' }`
  - Response: success message

- `POST /api/v1/user/profile/image`
  - Auth: bearer user
  - Body: multipart `file`
  - Response: uploaded profile image result

- `GET /api/v1/user/profile/filter`
  - Auth: bearer user
  - Query: `type, page, limit`
  - Response: paginated user images by type

- `POST /api/v1/user/profile/cover-image`
  - Auth: bearer user
  - Body: multipart `file`
  - Response: uploaded cover image result

- `POST /api/v1/user/profile/personalities`
  - Auth: bearer admin
  - Body: multipart personality payload + `image`
  - Response: created personality

- `PUT /api/v1/user/profile/personalities`
  - Auth: bearer admin
  - Body: multipart update payload + optional `image`
  - Response: updated personality

- `DELETE /api/v1/user/profile/personalites/:id`
  - Auth: bearer admin
  - Body: none
  - Response: delete result

- `GET /api/v1/user/profile/personality/:id`
  - Auth: bearer admin
  - Body: none
  - Response: one personality

- `GET /api/v1/user/profile/personalites`
  - Auth: none
  - Body: none
  - Response: all personalities

### User Images

- `POST /api/v1/user/image`
  - Auth: none
  - Body: create user image DTO
  - Response: created image record

- `GET /api/v1/user/image`
  - Auth: none
  - Body: none
  - Response: all image records

- `GET /api/v1/user/image/:id`
  - Auth: none
  - Body: none
  - Response: image record

- `PATCH /api/v1/user/image/:id`
  - Auth: none
  - Body: update user image DTO
  - Response: updated record

- `DELETE /api/v1/user/image/:id`
  - Auth: none
  - Body: none
  - Response: delete result

### Posts

- `POST /api/v1/posts/`
  - Auth: bearer user
  - Body: post DTO
  - Response: created post

- `PUT /api/v1/posts/`
  - Auth: bearer user
  - Body: update post DTO
  - Response: updated post

- `GET /api/v1/posts/get/:postId`
  - Auth: bearer admin
  - Body: none
  - Response: single post

- `GET /api/v1/posts/view/:uuid`
  - Auth: bearer user
  - Body: none
  - Response: single post in auth context

- `GET /api/v1/posts/public/view/:uuid`
  - Auth: none
  - Body: none
  - Response: public single post

- `GET /api/v1/posts/add-uuids`
  - Auth: intended user, but controller lacks guard
  - Body: none
  - Response: backfill result

- `DELETE /api/v1/posts/:postId`
  - Auth: bearer user
  - Body: none
  - Response: delete result

- `GET /api/v1/posts/`
  - Auth: none
  - Query: `page, limit`
  - Response: guest feed pagination

- `GET /api/v1/posts/comments`
  - Auth: none
  - Query: `beforeId, afterId, limit, postId`
  - Response: paginated comments

- `GET /api/v1/posts/comments/replies`
  - Auth: none
  - Query: `beforeId, afterId, limit, commentId`
  - Response: paginated replies

- `POST /api/v1/posts/media-files/:type/:postId`
  - Auth: bearer user
  - Body: multipart `images[]`, `selected_thumbnail[]`, `thumbnails[]`
  - Response: uploaded media result

- `POST /api/v1/posts/like`
  - Auth: bearer user
  - Body: post like DTO
  - Response: like/unlike result

- `POST /api/v1/posts/comments`
  - Auth: bearer user
  - Body: post comment DTO
  - Response: created comment

- `POST /api/v1/posts/comments/replies`
  - Auth: bearer user
  - Body: reply DTO
  - Response: created reply

- `PUT /api/v1/posts/comments`
  - Auth: bearer user
  - Body: update comment DTO
  - Response: updated comment

- `DELETE /api/v1/posts/comments/remove/:commentId`
  - Auth: bearer user
  - Body: none
  - Response: delete result

- `PUT /api/v1/posts/comments/replies`
  - Auth: bearer user
  - Body: update comment DTO
  - Response: updated reply

- `DELETE /api/v1/posts/comments/replies/remove/:commentReplyId`
  - Auth: bearer user
  - Body: none
  - Response: delete result

- `POST /api/v1/posts/comments/like`
  - Auth: bearer user
  - Body: comment like DTO
  - Response: like result

- `POST /api/v1/posts/reactions`
  - Auth: bearer user
  - Body: post reaction DTO
  - Response: reaction result

- `POST /api/v1/posts/comments/replies/like`
  - Auth: bearer user
  - Body: reply-like DTO
  - Response: like result

- `DELETE /api/v1/posts/admin/soft-delete/:id`
  - Auth: none in controller, likely intended admin
  - Body: none
  - Response: soft-delete result

- `GET /api/v1/posts/admin/trashed/list`
  - Auth: none in controller, likely intended admin
  - Query: `page, limit`
  - Response: trashed posts pagination

- `GET /api/v1/posts/admin/comments/:commentId/revisions`
  - Auth: bearer admin
  - Body: none
  - Response: comment revision history

### Files

- `POST /api/v1/files/upload`
  - Auth: bearer
  - Body: multipart `file`
  - Response: uploaded file URL/path

- `GET /api/v1/files/assets`
  - Auth: none
  - Query: `folder?`
  - Response: `{ success, assets, total, currentFolder }`

- `GET /api/v1/files/folders`
  - Auth: none
  - Query: `prefix?`
  - Response: `{ success, folders, currentPrefix }`

- `POST /api/v1/files/folders`
  - Auth: bearer
  - Body: `{ folderPath }`
  - Response: folder creation result

- `POST /api/v1/files/upload-to-folder`
  - Auth: bearer
  - Body: multipart `file` + `folder`
  - Response: `{ success, url, location, key, folder, domain }`

- `GET /api/v1/files/:path`
  - Auth: none
  - Body: none
  - Response: local file download from `./files`

### Conversations / Messaging

- `GET /api/v1/conversations/`
  - Auth: bearer user
  - Query: conversations DTO fields
  - Response: `{ conversations, total, pagination }`

- `PATCH /api/v1/conversations/:id/delete`
  - Auth: bearer user
  - Body: none
  - Response: soft-delete result

- `POST /api/v1/conversations/initiate`
  - Auth: bearer user
  - Body: initiate conversation DTO
  - Response: new conversation

- `POST /api/v1/conversations/respond/:conversationId`
  - Auth: bearer user
  - Body: respond DTO
  - Response: response result

- `POST /api/v1/conversations/mark-as-read`
  - Auth: bearer user
  - Body: mark-as-read DTO
  - Response: `{ success: true }`

- `GET /api/v1/messages/`
  - Auth: bearer user
  - Query: get-messages DTO
  - Response: `{ messages, pagination }`

- `POST /api/v1/messages/store`
  - Auth: bearer user
  - Body: create message DTO
  - Response: created message

- `POST /api/v1/messages/chat-attachment-files/:messageId`
  - Auth: bearer user
  - Body: multipart `images[]`
  - Response: attachment upload result

- `DELETE /api/v1/messages/delete/:messageId`
  - Auth: bearer user
  - Body: none
  - Response: delete result

- `PUT /api/v1/messages/edit/:messageId`
  - Auth: bearer user
  - Body: `{ newMessage }`
  - Response: updated message

### Notifications

- `GET /api/v1/user-notificaions/`
  - Auth: bearer user
  - Query: `page, limit`
  - Response: paginated notifications

- `GET /api/v1/user-notificaions/un-seen-notifs-count`
  - Auth: bearer user
  - Body: none
  - Response: unseen count

- `POST /api/v1/user-notificaions/mark-notif-as-seen`
  - Auth: bearer user
  - Body: mark-seen DTO
  - Response: mark-seen result

- `GET /api/v1/user-notificaions/unseen-notifs`
  - Auth: bearer user
  - Query: `page, limit`
  - Response: paginated unseen notifications

### Discover

- `GET /api/v1/discover/all-hodlneers`
  - Auth: none
  - Query: `page, limit`
  - Response: user discovery list, optionally personalized if request has user

- `GET /api/v1/discover/search`
  - Auth: none
  - Query: `search, page, limit`
  - Response: matching users

### Recommendations

- `GET /api/v1/recommendations`
  - Auth: bearer
  - Query: recommendations DTO
  - Response: personalized recommendation payload

- `POST /api/v1/recommendations/behavior`
  - Auth: bearer
  - Body: track-behavior DTO
  - Response: `{ message }`

- `GET /api/v1/recommendations/crypto-preferences`
  - Auth: bearer
  - Body: none
  - Response: array of crypto preferences

- `PUT /api/v1/recommendations/crypto-preferences`
  - Auth: bearer
  - Body: `{ preferences: [...] }`
  - Response: updated preferences

- `GET /api/v1/recommendations/stats`
  - Auth: bearer
  - Body: none
  - Response: user behavior stats

- `POST /api/v1/recommendations/warmup`
  - Auth: bearer
  - Body: none
  - Response: `{ message }`

- `GET /api/v1/recommendations/articles/:articleId/mappings`
  - Auth: bearer
  - Body: none
  - Response: article-to-crypto mappings

- `POST /api/v1/recommendations/articles/:articleId/mappings`
  - Auth: bearer
  - Body: `{ cryptoProjectId, relevanceScore, source?, extractedKeywords? }`
  - Response: created mapping

- `PUT /api/v1/recommendations/articles/:articleId/mappings/:cryptoProjectId`
  - Auth: bearer
  - Body: `{ relevanceScore }`
  - Response: `{ message }`

- `DELETE /api/v1/recommendations/articles/:articleId/mappings/:cryptoProjectId`
  - Auth: bearer
  - Body: none
  - Response: `{ message }`

### Tags

- `GET /api/v1/tags/generate`
  - Auth: bearer user
  - Query: `text`
  - Response: generated hashtags string array

- `GET /api/v1/tags/last-used`
  - Auth: bearer user
  - Query: `userId?`
  - Response: last-used tags with counts and created date

### Crypto Projects / Market Data

- `POST /api/v1/crypto-projects/tags`
  - Auth: bearer admin
  - Body: multipart `{ name, image }`
  - Response: created tag

- `PUT /api/v1/crypto-projects/tags`
  - Auth: bearer admin
  - Body: multipart update tag DTO + optional image
  - Response: updated tag

- `PUT /api/v1/crypto-projects/categories`
  - Auth: bearer admin
  - Body: multipart update category DTO + optional image
  - Response: updated category

- `POST /api/v1/crypto-projects/categories`
  - Auth: bearer admin
  - Body: multipart `{ name, image }`
  - Response: created category

- `PUT /api/v1/crypto-projects/`
  - Auth: bearer admin
  - Body: multipart update project DTO + optional image
  - Response: updated project

- `POST /api/v1/crypto-projects/`
  - Auth: bearer admin
  - Body: multipart project payload + image
  - Response: created project

- `GET /api/v1/crypto-projects/tags`
  - Auth: none
  - Body: none
  - Response: all crypto tags

- `GET /api/v1/crypto-projects/categories`
  - Auth: none
  - Body: none
  - Response: all categories

- `GET /api/v1/crypto-projects/`
  - Auth: none
  - Body: none
  - Response: all crypto projects

- `GET /api/v1/crypto-projects/get-on-board-dlisted-crypto-projects`
  - Auth: none
  - Body: none
  - Response: onboarding shortlist entries

- `DELETE /api/v1/crypto-projects/delete/:id`
  - Auth: bearer admin
  - Body: none
  - Response: delete result

- `GET /api/v1/crypto-projects/get/:id`
  - Auth: bearer admin
  - Body: none
  - Response: one project

- `DELETE /api/v1/crypto-projects/tags/:id`
  - Auth: bearer admin
  - Body: none
  - Response: delete result

- `GET /api/v1/crypto-projects/tags/:id`
  - Auth: bearer admin
  - Body: none
  - Response: one tag

- `DELETE /api/v1/crypto-projects/categories/:id`
  - Auth: bearer admin
  - Body: none
  - Response: delete result

- `GET /api/v1/crypto-projects/categories/:id`
  - Auth: bearer admin
  - Body: none
  - Response: one category

- `GET /api/v1/crypto-projects/import`
  - Auth: none
  - Body: none
  - Response: currently empty/stub

- `POST /api/v1/crypto-projects/import-images`
  - Auth: none
  - Body: multipart `files[]`
  - Response: currently only logs files

- `POST /api/v1/crypto-projects/onboard-dlist/add`
  - Auth: none in controller
  - Body: `{ cryptoProjectIds }`
  - Response: add-to-shortlist result

- `POST /api/v1/crypto-projects/onboard-dlist/remove`
  - Auth: none in controller
  - Body: `{ cryptoProjectIds }`
  - Response: remove-from-shortlist result

- `GET /api/v1/crypto-projects/onboard-dlist`
  - Auth: none
  - Body: none
  - Response: shortlist

- `GET /api/v1/crypto-projects/get-coincap-market-crypto-currencies`
  - Auth: none
  - Body: none
  - Response: latest market currencies

- `POST /api/v1/crypto-projects/update`
  - Auth: bearer admin
  - Body: `{ limit? }`
  - Response: manual data update result

- `GET /api/v1/crypto-projects/update-status`
  - Auth: bearer admin
  - Body: none
  - Response: update status

- `POST /api/v1/crypto-projects/initialize`
  - Auth: bearer admin
  - Body: none
  - Response: `{ success, message }`

- `GET /api/v1/crypto-projects/top/:limit?`
  - Auth: none
  - Body: none
  - Response: top cryptocurrencies

- `POST /api/v1/crypto-projects/logos/download`
  - Auth: bearer admin
  - Body: `{ limit? }`
  - Response: logo download result

- `GET /api/v1/crypto-projects/logos/stats`
  - Auth: bearer admin
  - Body: none
  - Response: logo storage stats

- `POST /api/v1/crypto-projects/logos/cleanup`
  - Auth: bearer admin
  - Body: none
  - Response: cleanup result

- `POST /api/v1/crypto-projects/update-comprehensive`
  - Auth: bearer admin
  - Body: `{ limit? }`
  - Response: combined update result

- `GET /api/v1/crypto-projects/library/top/:limit?`
  - Auth: none
  - Body: none
  - Response: top cryptocurrencies from internal icon library

- `GET /api/v1/crypto-projects/library/icon/:symbol/:style?`
  - Auth: none
  - Body: none
  - Response: SVG content or error

### Crypto Library

- `GET /api/v1/crypto-library/`
  - Auth: none
  - Body: none
  - Response: all available cryptocurrencies with icon status

- `GET /api/v1/crypto-library/top/:limit?`
  - Auth: none
  - Body: none
  - Response: top cryptocurrencies

- `GET /api/v1/crypto-library/crypto/:symbol`
  - Auth: none
  - Body: none
  - Response: one cryptocurrency record

- `GET /api/v1/crypto-library/icon/:symbol/:style?`
  - Auth: none
  - Body: none
  - Response: SVG icon

- `GET /api/v1/crypto-library/styles/:symbol`
  - Auth: none
  - Body: none
  - Response: `{ styles }`

- `GET /api/v1/crypto-library/search?q=...&limit=...`
  - Auth: none
  - Body: none
  - Response: search results

- `GET /api/v1/crypto-library/stats`
  - Auth: none
  - Body: none
  - Response: library stats

### Internal Crypto

- `GET /api/v1/internal-crypto/stats`
  - Auth: none
  - Body: none
  - Response: internal library stats

- `GET /api/v1/internal-crypto/top/:limit?`
  - Auth: none
  - Body: none
  - Response: top cryptocurrencies

- `GET /api/v1/internal-crypto/crypto/:symbol`
  - Auth: none
  - Body: none
  - Response: one cryptocurrency

- `GET /api/v1/internal-crypto/icon/:symbol`
  - Auth: none
  - Body: none
  - Response: SVG icon

- `GET /api/v1/internal-crypto/search?q=...&limit=...`
  - Auth: none
  - Body: none
  - Response: search results

### Blogs

- `GET /api/v1/blogs/keepReading-blogs`
  - Auth: none
  - Query: `category, page, pageSize`
  - Response: paginated blogs

- `GET /api/v1/blogs/`
  - Auth: none
  - Query: `category, sort, page, pageSize`
  - Response: `{ featured, unfeatured, pagination }`

- `GET /api/v1/blogs/feeds`
  - Auth: none
  - Query: `category, page, pageSize`
  - Response: feed-specific featured/unfeatured blogs

- `GET /api/v1/blogs/slug/:slug`
  - Auth: none
  - Body: none
  - Response: blog by slug

- `GET /api/v1/blogs/categories`
  - Auth: none
  - Body: none
  - Response: blog categories

- `GET /api/v1/blogs/tags`
  - Auth: none
  - Body: none
  - Response: blog tags

- `GET /api/v1/blogs/by-ids?ids=a,b,c`
  - Auth: none
  - Body: none
  - Response: blogs for supplied ids

- `POST /api/v1/blogs/save`
  - Auth: none in controller
  - Body: save blog DTO
  - Response: saved-blog record

- `DELETE /api/v1/blogs/delete/:userId/:blogId`
  - Auth: none in controller
  - Body: none
  - Response: removed saved-blog record

- `GET /api/v1/blogs/saved/:userId`
  - Auth: none in controller
  - Body: none
  - Response: saved blogs for user

- `GET /api/v1/blogs/saved/check/:userId/:blogId`
  - Auth: none in controller
  - Body: none
  - Response: boolean

- `PUT /api/v1/blogs/views/:documentId`
  - Auth: none
  - Body: none
  - Response: updated view count record

### Settings / Legal Content

- `GET /api/v1/settings/terms`
  - Auth: none
  - Body: none
  - Response: terms HTML/content

- `GET /api/v1/settings/policy`
  - Auth: none
  - Body: none
  - Response: privacy policy HTML/content

- `POST /api/v1/settings/policy`
  - Auth: none in controller
  - Body: `{ policyHtml }`
  - Response: set result

- `POST /api/v1/settings/terms`
  - Auth: none in controller
  - Body: `{ termsHtml }`
  - Response: set result

- `GET /api/v1/settings/about`
  - Auth: none
  - Body: none
  - Response: about HTML/content

- `POST /api/v1/settings/about`
  - Auth: none in controller
  - Body: `{ aboutHtml }`
  - Response: set result

- `GET /api/v1/settings/accessibility`
  - Auth: none
  - Body: none
  - Response: accessibility HTML/content

- `POST /api/v1/settings/accessibility`
  - Auth: none in controller
  - Body: `{ accessibilityHtml }`
  - Response: set result

- `GET /api/v1/settings/user-agreement`
  - Auth: none
  - Body: none
  - Response: agreement HTML/content

- `POST /api/v1/settings/user-agreement`
  - Auth: none in controller
  - Body: `{ userAgreementHtml }`
  - Response: set result

- `GET /api/v1/settings/cookie-policy`
  - Auth: none
  - Body: none
  - Response: cookie policy HTML/content

- `POST /api/v1/settings/cookie-policy`
  - Auth: none in controller
  - Body: `{ cookiePolicyHtml }`
  - Response: set result

- `GET /api/v1/settings/copyright-policy`
  - Auth: none
  - Body: none
  - Response: copyright HTML/content

- `POST /api/v1/settings/copyright-policy`
  - Auth: none in controller
  - Body: `{ copyrightPolicyHtml }`
  - Response: set result

- `GET /api/v1/settings/brand-policy`
  - Auth: none
  - Body: none
  - Response: brand policy HTML/content

- `POST /api/v1/settings/brand-policy`
  - Auth: none in controller
  - Body: `{ brandPolicyHtml }`
  - Response: set result

- `GET /api/v1/settings/data-deletion`
  - Auth: none
  - Body: none
  - Response: data deletion HTML/content

- `POST /api/v1/settings/data-deletion`
  - Auth: none in controller
  - Body: `{ dataDeletionHtml }`
  - Response: set result

### SMS

- `POST /api/v1/sms/send-verification`
  - Auth: none
  - Body: `{ phone }`
  - Response: verification send result

- `POST /api/v1/sms/verify-code`
  - Auth: none
  - Body: `{ phone, code }`
  - Response: verification result

### Mail Test Endpoints

- `GET /mail/test-mailgun`
  - Auth: none
  - Body: none
  - Response: Mailgun connectivity result

- `POST /mail/test-verification`
  - Auth: none
  - Body: `{ email, userName? }`
  - Response: test verification email result

- `POST /mail/test-welcome`
  - Auth: none
  - Body: `{ email, userName }`
  - Response: test welcome email result

- `POST /mail/test-simple`
  - Auth: none
  - Body: `{ email, subject?, message? }`
  - Response: test email result

## Notes

Two important caveats:

- “Auth” above reflects actual controller guards, not what seems intended. Some sensitive routes are exposed without guards.
- “Response notes” reflect code-level return shapes; many endpoints return raw service/entity objects rather than stable DTO contracts.
