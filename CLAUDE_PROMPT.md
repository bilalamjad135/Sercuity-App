# Claude implementation brief — AB SmartTag

Act as senior full-stack engineer for AB SmartTag by ABTechInnovation, a Pakistan-focused QR vehicle identity and emergency contact service. Preserve the Inter font, navy/blue/white identity, mobile-first layout and accessible controls.

Current project: Vite + React frontend prototype. It includes vehicle management, QR generation, emergency contacts, scan history, public scan view and browser-local demo persistence. Do not claim this is production-ready.

Production phases:
1. Supabase Auth and PostgreSQL tables: profiles, organizations, members, vehicles, qr_tags, emergency_contacts, scan_events, subscriptions, notification_jobs and audit_logs. Apply RLS to every user-facing table.
2. Generate cryptographically random, non-sequential QR tokens. Resolve them server-side. Public responses must expose only minimum safe vehicle information and enabled actions.
3. Keep owner contacts private. Require authenticated authorization for edits. Never put service-role or WhatsApp secrets in frontend code.
4. Implement WhatsApp Business API only with user opt-in, approved templates, delivery webhooks, retries, rate limits and audit records. A QR scan alone must not silently message anyone.
5. Request location only after a clear user action and consent. Define retention and deletion rules.
6. Add Pakistan emergency quick-dial options (1122 Rescue, 15 Police, 115 Edhi), noting regional availability may vary.
7. Verify payment gateway signatures server-side before activating subscriptions.
8. Add customer portal, organization/fleet support, admin roles, printable QR sheets, exports, privacy/terms pages and automated security tests.

Work in small phases, preserve existing features, provide migrations and setup docs, and do not claim a feature is live until it is implemented and verified.