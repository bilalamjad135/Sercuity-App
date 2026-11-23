# AB SmartTag by ABTechInnovation

Responsive React/Vite prototype for QR-based vehicle identity and emergency contact.

## Run
- Node.js 20+
- `npm install`
- `npm run dev`
- Production build: `npm run build`

## Vercel
Import this GitHub repository into Vercel. Framework: Vite; build command: `npm run build`; output directory: `dist`. SPA rewrite is included.

## Public launch status — not production-ready yet

The emergency helpline directory is a convenience directory, not an emergency dispatch integration. Public QR lookup is currently based on browser-local storage; a QR generated in one person's browser will not reliably resolve vehicle details on another person's phone. Owner contacts, scan events and vehicles are not backed by a shared database. Do not distribute QR tags publicly or advertise owner-notification features until Supabase (or an equivalent backend), secure QR-token lookup, owner verification/consent, privacy controls and end-to-end tests are implemented.

The QR page now supports tap-to-call buttons for emergency contacts that the owner explicitly opts in to share. Add a contact under **Emergency Contacts** and tick **Allow this contact to appear on the public vehicle QR page**. The public page shows the contact name and relationship, not the number as visible text; tapping Call opens the visitor's dialler, where the number may be visible. The visitor must confirm the call. This consent control is a frontend demo and is not a substitute for authenticated, server-enforced privacy controls.

## Current prototype limitations
This is a frontend demonstration. Vehicles, contacts and scan events are stored in the current browser's localStorage and are not shared between devices. Seeded records are fictional demo data. The QR scan route, WhatsApp handoff and location sharing are demonstration flows only. No automatic WhatsApp/SMS alerts, dispatch, authentication, subscriptions or payment processing are active.

Before public launch, implement Supabase/PostgreSQL with row-level security, authentication, server-side QR token resolution, secure role checks, WhatsApp Business API with opt-in and webhooks, verified payment webhooks, abuse prevention, audit logs, privacy policy and data-retention controls. Keep all provider secrets server-side. Never expose vehicle-owner private phone numbers on the public scan page.

## Font
Inter — https://fonts.google.com/specimen/Inter
## Expanded customer-facing prototype screens

The current frontend now includes:
- Customer profile records with linked-vehicle counts (local browser demo).
- Scan Activity with event time, vehicle, event source, device and location fields where available. Current test events do not represent real public QR scans.
- GPS Tracking status and a map placeholder.
- Device Mapping to associate a tracker identifier / IMEI with a registered vehicle.
- Call & Support with a callback-request form and quick-call links to saved contacts.

These are interface demonstrations, not live services. The tracking screen does not receive GPS coordinates. Device mapping only records the device identifier; it does not activate a tracker or communicate with a telematics provider. Support requests are saved locally and are not delivered to a call centre. The customer, scan, device and support records remain in localStorage and are not shared across browsers or devices.

## Production integration needed

1. Shared backend and authentication: move customer, vehicle, consent, QR-scan, device and support records to a secure database with server-side access controls and audit history.
2. QR scan analytics: resolve opaque random QR tokens server-side; log timestamp, scan source, approximate location only with the visitor's explicit permission, and the actions taken. Avoid collecting unnecessary personal or device identifiers.
3. GPS tracking: choose compatible hardware and a telematics provider, obtain their API/protocol documentation, install the tracker and SIM, then connect a server-side ingestion service. Only then can live location, last-seen status, trip history, geofences and movement alerts be shown.
4. Call centre: connect a staffed support phone number or cloud telephony provider. A callback form needs a server endpoint, consent text, ticketing and an assigned support team. Emergency calls must continue to use the relevant public emergency authorities.
5. Customer experience: add guided registration, plain-language labels, language support, accessible forms, help articles and clear error messages.

Never describe QR scan location as live vehicle tracking. Do not display a moving map or route unless fresh GPS telemetry is actually received from the vehicle's tracker.
