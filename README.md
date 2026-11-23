# AB SmartTag by ABTechInnovation

Responsive React/Vite prototype for QR-based vehicle identity and emergency contact.

## Run
- Node.js 20+
- `npm install`
- `npm run dev`
- Production build: `npm run build`

## Vercel
Import this GitHub repository into Vercel. Framework: Vite; build command: `npm run build`; output directory: `dist`. SPA rewrite is included.

## Current prototype limitations
This is a frontend demonstration. Vehicles, contacts and scan events are stored in the current browser's localStorage and are not shared between devices. Seeded records are fictional demo data. The QR scan route, WhatsApp handoff and location sharing are demonstration flows only. No automatic WhatsApp/SMS alerts, dispatch, authentication, subscriptions or payment processing are active.

Before public launch, implement Supabase/PostgreSQL with row-level security, authentication, server-side QR token resolution, secure role checks, WhatsApp Business API with opt-in and webhooks, verified payment webhooks, abuse prevention, audit logs, privacy policy and data-retention controls. Keep all provider secrets server-side. Never expose vehicle-owner private phone numbers on the public scan page.

## Font
Inter — https://fonts.google.com/specimen/Inter