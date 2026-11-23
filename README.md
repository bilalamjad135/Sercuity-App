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