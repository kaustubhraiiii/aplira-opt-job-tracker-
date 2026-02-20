# TECH_STACK (Aplira v1)

## Architecture

- Chrome Extension (Manifest V3)
- Supabase (Auth + Postgres)
- Serverless AI proxy (Next.js API route or Supabase Edge Function)

---

## Frontend (Extension)

- React 18.2
- TypeScript 5.x
- Tailwind CSS 3.x
- Plasmo Framework
- Lucide React icons

---

## Authentication

- Supabase Auth
- Email/password
- Google OAuth
- JWT stored via Supabase client
- Session refresh handled automatically

---

## Backend

- Supabase Postgres 15+
- Supabase Row Level Security (RLS)
- Supabase Edge Functions (optional AI proxy)

---

## Database

- PostgreSQL (Supabase managed)
- UUID primary keys
- Timestamps on all tables

---

## AI Layer

- OpenAI or equivalent
- API key stored only in:
  - Edge Function OR Next.js server route

---

## Hosting (AI Proxy)

Option 1:
- Vercel (Next.js serverless API)

Option 2:
- Supabase Edge Function

---

## Dev Tools

- Node 20 LTS
- pnpm
- ESLint + Prettier
- GitHub

---

## Security

- RLS enabled
- JWT validation
- No secrets in extension
- HTTPS enforced
