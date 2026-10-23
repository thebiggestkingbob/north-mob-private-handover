# Data and integration plan (validate against actual repository)
Entities: AdminUser, Artist, Release, Track, MediaAsset, MediaCollection, Event, Product, Variant, StockMovement, Order, OrderItem, PaymentEvent, Fan, FanConsent, FanPreference, Campaign, CampaignDelivery, Enquiry, AuditEvent.
Data access: one authenticated owner; server-side permissions, storage access policies and admin route protection. Future role support without granting access at launch.
Music: playback engine at app root; separate first-party audio from provider embeds; preserve state and document restrictions.
Media: signed uploads, originals, optimized derivatives, responsive crop, alt text, collections, publish status, soft delete.
Commerce: payment gateway with verified webhooks, stock consistency, receipts, shipping, refund and failed-payment recovery.
Fans: opt-in and consent audit, purchase-based segmentation only where permitted, no inferred identities from anonymous plays; unsubscribed suppression; POPIA-aware export/delete and retention.
Brevo: drafts, templates, test sends, scheduled sends, delivery logs, retries, deduplication, transactional versus marketing separation.
Operations: error monitoring, backups, migrations, deployment environment variables, audit logging, staging and production separation.
