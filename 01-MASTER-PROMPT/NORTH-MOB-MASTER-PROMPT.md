# NORTH MOB — COMPLETE CODEX MASTER IMPLEMENTATION PROMPT

Repository: https://github.com/thebiggestkingbob/the-north-mob
Goal: Transform the EXISTING website into a premium cinematic entertainment platform with a fully functioning administration backend, merch commerce, and fan engagement. ONE coordinated public launch, internally staged.

## FIRST: AUDIT, DO NOT MODIFY YET
Inspect the existing repository, routes, frameworks, styles, animations, current Spotify/music playback, Brevo/email endpoints, media, tests, auth, hosting and deployments. Inspect ALL package media and the Mustard reference recording/screenshots. Read `06-IMPLEMENTATION/asset-inventory.csv`, contact sheet, and page blueprint. Produce a detailed feature inventory, gaps, risks, assets-to-pages map, data model, dependencies, staged implementation plan, and missing asset/credential list BEFORE modifying code. Work on a separate branch. Never overwrite working features or deploy production without explicit user approval.

## DESIGN LANGUAGE — LOCKED
Inspiration: Mustard / 10 Summers cinematic presentation, NOT a copy of its proprietary visuals, source, logo, film or exact compositions. Create an original NORTH MOB experience using the supplied approved MOB TIES assets and the existing official brand identity. Mostly black/white; filmic pacing; minimal corner/header navigation; full-bleed images/video; controlled transitions and editorial composition. The public experience should feel like continuous chapters of one film but remain navigable, accessible, and performant. NO giant NORTH MOB homepage title. NO generic card grids, gratuitous 3D, boxes or marketing filler. Reduced-motion, mobile-specific art direction and loading fallbacks are mandatory. Don't introduce unapproved stock imagery.

## HOMEPAGE
Full-viewport cinematic first-party NORTH MOB visuals, with discreet official logo, restrained navigation and media controls. Use optimized hosted video and `object-fit: cover` for a film-like background; autoplay muted only where allowed; poster frame and still-image fallback; user-controlled audio. Video is NOT a visible boxed YouTube embed. Sequence photography and footage through subtle GSAP/CSS motion without scroll hijacking. Include intuitive navigation to all sections.

## MUSIC + PERSISTENT MINI-PLAYER (NON-NEGOTIABLE)
Redesign the existing player from the ground up to Apple Music-inspired minimalism in NORTH MOB styling. ONE clean, small, consistently accessible player across Home, Music, The Mob, Visualz, Live, Business As Usual and Shop. No expanded or full-screen player. Show small artwork, artist/title, play/pause and supported next/previous/progress. User selection should start playback as immediately as browser/provider rules allow. Player/audio engine must remain mounted above route transitions; preserve playback/queue state, avoid restarting when navigating. Test Safari/iOS, Android and desktop. Spotify/YouTube embeds cannot be assumed to provide seamless persistent audio: verify provider-specific constraints and disclose unsupported scenarios. Music page: official H4B artwork and verified artist/collective catalogues, albums, tracklists, Spotify/Apple Music/SoundCloud/YouTube links/embeds where licensed and supported. Never invent missing album artwork or song data.

## VISUALZ
Major redesign: cinematic featured video followed by discoverable YouTube-inspired video library and photo archive. Videos play within the site via permitted embedded playback. Browsing/search/filtering by music video, behind-the-scenes, live, interview, studio and photography. Video metadata, featured selection, photo albums, tags, artist/event links, responsive thumbnails, gallery lightbox and swipe controls. Studio manages uploads, featured media and publishing. Avoid visually copying YouTube's interface.

## THE MOB
Rich individual artist profiles with real supplied portraits, bios, verified music/video/event links. Explore H4B identification-card interactions only after artist/card mapping is verified. Do not invent artist identities.

## LIVE
Upcoming and past events, verified flyers, dates, locations, ticket URLs, city filters and archived gig media. Studio event create/edit/publish/archive, with notification subscriptions and consent. Never invent gigs.

## BUSINESS AS USUAL
Rename consistently from incorrect Business Is Personal wording to BUSINESS AS USUAL. Redesign as minimal, premium editorial page. Adaptive enquiries: booking, media/press, sponsorship, partnerships, collaboration, general. Appropriate fields for dates, location, budget, brief and contact. Server validation, spam protection, consent and notification; submissions visible in Studio with statuses, notes and assignment. Retain working Brevo transactional email where appropriate.

## SHOP
Full integrated merch store: product/category/collection pages, product variants (sizes/colors), photos, pricing in ZAR, inventory, cart, checkout, shipping/tax handling, order confirmations, statuses, cancellations/refunds, limited drops and admin order management. Evaluate South Africa-compatible payment provider and implement secure verified webhooks, idempotency, sandbox checkout and settlement reconciliation. Never store card details. Product photography, final pricing, shipping policies and merchant credentials must be supplied/approved, not invented.

## NORTH MOB STUDIO — ONE OWNER AT LAUNCH
Private secure CMS/admin application with one owner initially; future role architecture without inviting artists at launch. Modules: Dashboard, Media Library, Music, Artists, Events, Visualz, Products, Orders, Business Enquiries, Fan Directory, Campaigns, Site Settings and Analytics. Secure login, server-side authorization, storage access rules, upload limits, moderation/publish states, audit log, backups, migrations and recovery. Use existing framework; evaluate Supabase PostgreSQL/Auth/Storage only after repo audit and migration risk review.

## FAN DIRECTORY + CAMPAIGNS — INCLUDE AT LAUNCH
No public fan accounts required. Collect fans via explicit email signup, city/event alerts, opt-in interests and legally appropriate order interactions. Model fan contacts, marketing consent, source, timestamp, preferences, purchase history (where lawful), segmentation and suppression. DO NOT identify anonymous Spotify/YouTube listeners or treat all shoppers as marketing subscribers. Integrate Brevo with newsletter templates, teaser campaigns, drafts, test sends, scheduling, unsubscribe, consent logs, export, correction, deletion, retention controls, deliverability reporting, retries and idempotent sending. Respect POPIA and provider requirements; distinguish marketing and transactional email. Never expose the entire fan directory publicly.

## SEARCH, DISCOVERY, ANALYTICS
Search across releases, artists, videos, gallery, events and merch. Deep-linkable pages, SEO and metadata. Privacy-conscious event tracking and consent controls; real metrics only, no fake listener data.

## ENGINEERING
Preserve existing working integrations, responsive layout and animations unless explicitly redesigned. Robust error/loading/empty states, accessible keyboard/focus, captions, contrast, responsive image cropping, optimized WebP/AVIF, streaming-friendly videos, lazy loading, reduced motion, Core Web Vitals. Secure API validation, CSRF/XSS protections as applicable, secrets only in deployment environment, rate limiting, webhook verification, transactional consistency, backups, monitoring and audit trails. Do not commit keys or private fan records. Keep Mustard references PRIVATE and do not publish them as site assets.

## REQUIRED E2E ACCEPTANCE TESTS
1. Persistent mini-player plays after user action and survives all internal navigation where the provider permits.
2. Studio owner can securely log in, upload images, publish Visualz galleries and events, edit artists/releases and see updates publicly.
3. Fan can subscribe with consent, receive permitted notifications, unsubscribe and request export/deletion.
4. Admin can draft, preview, test, schedule and send Brevo campaigns with no duplicate sends.
5. Customer can complete a sandbox merchandise order; inventory, webhook, receipt, order management, shipping/refund flows are correct.
6. Business enquiry is validated, stored, notified and managed.
7. Mobile Safari, Android Chrome, desktop browsers, accessibility and reduced-motion behavior pass.
8. Regression tests show existing working features preserved.
9. Logs, monitoring, backup/restore and rollback procedures are demonstrated.
Do not declare production ready based on mock interfaces or untested integrations.

## BUILD AND LAUNCH PROCESS
Audit → approve creative asset map → implement frontend → persistent mini-player → Studio → commerce → fan directory/Brevo → integrated tests → staging preview → explicit user approval → single complete public launch. If secrets, content or payment approvals are missing, clearly flag them as blockers rather than pretending they're complete.

IMPORTANT: H4B official cover, latest gig flyers, final merch photos, artist-to-ID mappings and live service credentials may be absent from this package. Inspect first, ask for missing material, do not fabricate.

START NOW WITH THE AUDIT AND IMPLEMENTATION PLAN ONLY. DO NOT DEPLOY OR MAKE DESTRUCTIVE CHANGES.
