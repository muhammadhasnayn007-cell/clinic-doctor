# MediCare Clinic Management Website

A responsive React, Vite, Tailwind CSS, and Supabase clinic website with public marketing pages, appointment booking, patient authentication, contact storage, and a protected administration view.

## Current implementation

- Responsive home, about, doctors, services, contact, booking, patient portal, and admin views
- Search and specialty filters for doctors
- Multi-step booking with client and server validation
- Atomic slot reservation through a unique database key to prevent duplicate doctor/date/time bookings
- Supabase Auth patient registration and login
- Patient-scoped appointment retrieval and eligible cancellation
- Server-authorized administrator overview and appointment status transitions
- Persisted contact messages
- Honest placeholders for clinic facts, pricing, address, phone, WhatsApp, map, and testimonials

## Local development

The Figma Make Vite server starts automatically. For a standalone checkout:

```bash
pnpm install
pnpm dev
```

Build with:

```bash
pnpm build
```

## Supabase setup

This project is connected through Figma Make. The generated public project information is in `utils/supabase/info.tsx`; the service role key remains server-side.

1. In Supabase Edge Function secrets, set `ADMIN_EMAILS` to a comma-separated allowlist.
2. Deploy `supabase/functions/server/index.tsx` from the Figma Make settings after server changes.
3. Enable the desired Supabase Auth email provider and configure confirmation/redirect URLs.
4. Create patient and administrator test accounts with synthetic data only.

Admin access is granted only after Supabase validates the bearer token and the authenticated email matches `ADMIN_EMAILS`. Frontend state is never used as authorization.

## Production checklist

- Replace every placeholder clinic detail and all sample people/content with verified information.
- Confirm actual services, prices, qualifications, schedules, policies, and opening hours.
- Replace the placeholder phone, email, address, WhatsApp URL, and map.
- Configure and test Supabase Auth email delivery and production redirect URLs.
- Add rate limiting, bot protection, monitoring, backups, retention rules, and incident procedures.
- Complete a qualified security, accessibility, privacy, and regulatory review.
- Verify desktop, tablet, and mobile booking, cancellation, contact, and admin workflows.
- Test concurrent appointment requests for the same slot.
- Do not use this demonstration to collect real patient data until the clinic's legal, privacy, and security requirements have been independently validated.

## Important privacy note

Figma Make is not represented as a healthcare-compliant patient records system. The site intentionally collects minimal scheduling data and warns users not to submit emergencies or sensitive clinical details. No claim of HIPAA, GDPR, or other regulatory compliance is made.
