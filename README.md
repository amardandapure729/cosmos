# COSMOS — Event, Celebration & Adventure Management Platform

A full-stack, futuristic 3D Event, Celebration & Adventure Management SaaS platform built with React, TypeScript, Tailwind CSS, Three.js / React Three Fiber, Framer Motion, Recharts, and a relational database backend (Node.js + SQLite local server + full Supabase PostgreSQL/RLS/Storage migrations).

## Features
- **3D Galaxy & Interactive Black Hole Landing Page**: WebGL starfield, glowing accretion disk, gravitational lensing halo, orbiting planets, mobile-optimized DPR, and WebGL error fallbacks.
- **Authentication & RBAC**: Sign Up, Login, Forgot/Reset Password, Profile & Organization settings, and Role-Based Access Control (`admin`, `organizer`, `member`), plus an isolated **Demo Mode** workspace.
- **12 Workspace Modules**: Overview Dashboard, Events, Celebrations (Birthdays), Tours & Trips, Trekking (with interactive gear checklist), Venues & Bookings, Members, Money Collections, Expenses & Receipts, Reports (PDF, Excel `.xlsx`, CSV), Notifications & Audit Logs, and Settings.
- **Financial Integrity**:
  - Payments cannot be marked paid without recording an immutable `payments` ledger entry.
  - `Remaining Balance = Total Collected - Total Expenses`.
  - Positive balances are explicitly classified as **Surplus (Refundable / Carry-Forward)**, never mislabeled as profit; negative balances are flagged as **Deficit (Additional Collection Needed)**.

## Quick Start (Local Full-Stack Mode)
```bash
npm install
npm run dev
```
- Frontend runs at `http://localhost:5173`
- Backend API & Uploads server runs at `http://localhost:4000` (proxied automatically by Vite)

## Supabase Deployment
Run the SQL migrations in `supabase/migrations/` in order:
1. `001_cosmos_schema.sql`
2. `002_rls_policies.sql`
3. `003_storage_buckets.sql`

Then configure `.env` with `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY`.

## Testing
```bash
npm test
npm run build
```
