# BIZRIUM — Fresh SaaS Foundation v1

Clean Next.js + Supabase foundation for the BIZRIUM multi-company Business OS.

## Included
- Public landing page
- Email/password signup and login
- Business workspace onboarding
- Workspace membership and RLS tenant isolation
- Persistent left navigation
- Starter record pages for Sales, Purchases, Inventory, Customers, Suppliers, Expenses, Reports, Team and Settings
- Subscription plan display and schema for trials/subscriptions

## Important
This is the foundation release, not yet a complete production accounting system. The business modules currently use a generic record model. Dedicated sales invoices, payment allocations, inventory movements and costing, double-entry accounting, returns, tax, reconciliation, team invitations, platform super-admin, and Paystack checkout/webhooks are subsequent build milestones. The displayed plan prices are proposed placeholders and should be commercially validated.

## Windows setup
1. Install Node.js 20 LTS or newer.
2. Create a NEW Supabase development project.
3. Open Supabase SQL Editor and run `supabase/migrations/202611160001_bizrium_core.sql`.
4. Copy `.env.example` to `.env.local`; enter only the Supabase project URL and publishable/anon key in the NEXT_PUBLIC variables.
5. Open PowerShell in this folder and run:
   ```powershell
   npm.cmd install
   npm.cmd run dev
   ```
6. Open http://localhost:3000

Enable email/password authentication in Supabase. Configure Site URL and Redirect URLs for localhost and later your Vercel domain.

## Security
Never put service-role or Paystack secret keys in frontend code, chat, GitHub, or any `NEXT_PUBLIC_` variable. Keep them in server-only deployment environment settings. Apply migrations to development first and have tenant isolation, financial calculations, and accounting postings independently reviewed before production.
