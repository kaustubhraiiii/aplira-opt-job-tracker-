# IMPLEMENTATION PLAN (Aplira v1)

## Phase 1: Supabase Setup (Half Day)

1. Create Supabase project
2. Enable:
   - Email auth
   - Google OAuth
3. Create tables:
   - profiles
   - jobs
   - ai_generations
4. Enable RLS
5. Add policies:
   - user_id = auth.uid()

Success:
- Can register + login
- Can query own data only

---

## Phase 2: Extension Auth (Half Day)

1. Install supabase-js
2. Implement:
   - Sign up
   - Sign in
   - Google OAuth
3. Store session
4. Auto-refresh session

Success:
- User persists after extension reload

---

## Phase 3: Job Save & Pipeline (1 Day)

1. Content script extraction
2. Save job → Supabase insert
3. Side panel fetch jobs
4. Status update

Success:
- Jobs sync across browser sessions

---

## Phase 4: OPT Tracker (Half Day)

1. Profile table update
2. Calculate days used
3. Display progress bar

---

## Phase 5: AI Resume Tailor (1 Day)

1. Create serverless proxy
2. Connect extension to endpoint
3. Save AI outputs to ai_generations

Success:
- Generate bullets
- Store result
- Copy works

---

## Phase 6: Polish

- Loading states
- Error handling
- Empty states
- RLS testing
