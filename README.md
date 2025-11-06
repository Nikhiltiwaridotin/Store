# Nikhil Tiwari — Courses & 1:1 Coaching

Modern Next.js 14 app for courses, digital products, and paid 1:1 sessions with automated emails/WhatsApp, downloads, and bookings.

## Tech Stack
- Next.js 14 (App Router), TypeScript, Tailwind CSS, shadcn-style UI
- PostgreSQL + Prisma ORM
- Auth: NextAuth (Email magic link + Google)
- Payments: Razorpay (INR) + Stripe (international)
- Email: Resend (or Nodemailer)
- WhatsApp: WhatsApp Cloud API
- File storage: signed URLs (S3 or Vercel Blob)
- Calendar: Google Calendar API
- Deploy: Vercel

## Quickstart

```bash
pnpm i # or npm i / yarn
cp .env.example .env # fill values
pnpm prisma:generate
pnpm prisma:migrate
pnpm prisma:seed
pnpm dev
```

Open http://localhost:3000

## Environment
See `.env.example` for required keys.

## Webhooks (manual setup)
- Razorpay: add endpoint `https://YOUR_DOMAIN/api/webhooks/razorpay`
- Stripe: add endpoint `https://YOUR_DOMAIN/api/webhooks/stripe`

## Google Calendar
- Create OAuth credentials (Web app), add redirect URI from Google provider in NextAuth.
- Share target calendar with your service account or use OAuth tokens to create events.

## WhatsApp Cloud
- Create app, connect Business number, get token/phone/business IDs.
- Get message template approvals for: order_confirmation, booking_confirmed, download_ready, payment_failed, reminder_24h.

## Testing
```bash
pnpm test
```

## Notes
- This repo includes scaffolding for pages, API routes, Prisma schema, and minimal tests. Integrations (webhook verify, calendar, storage signing, templates) include TODOs to finalize with your credentials.


