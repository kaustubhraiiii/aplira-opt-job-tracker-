# Application Flow (Aplira v1)

## Entry Points

1. Extension popup click
2. Side panel open
3. OAuth redirect (Google login)

---

# FLOW 1: Authentication

### Entry: First popup open

IF not authenticated:
→ Show Auth Screen

Auth Screen:
- Continue with Google
- Continue with Email
- Switch to Sign In

On Success:
→ Redirect to Home Dashboard

Error States:
- Invalid credentials
- Network error
- OAuth cancelled

---

# FLOW 2: First-Time Setup

After login:
IF opt_start_date is null
→ Show setup prompt

User sets date
→ Store in Supabase profile table

---

# FLOW 3: Save Job

Entry: On job page + popup open

1. Content script extracts:
   - title
   - company
   - location
   - URL
   - JD text

2. Popup displays form
3. User selects:
   - status
   - visa tag
4. Save

System:
- Inserts into jobs table
- Returns success
- Toast confirmation

---

# FLOW 4: Pipeline View

Entry: Side panel

1. Fetch jobs (user_id scoped)
2. Display cards
3. Filter by status
4. Update status inline
5. Open link

Empty State:
- “Save your first job”

---

# FLOW 5: AI Resume Tailor

Entry: Popup AI section

1. User pastes project summary
2. JD auto-filled or pasted
3. Click Generate

System:
- Call AI proxy endpoint
- Store result in ai_generations table
- Return bullets

User:
- Click Copy

Error States:
- Missing input
- AI timeout
- Rate limit

---

# Decision Logic

IF session expired:
→ Force logout
→ Show auth screen

IF JD extraction fails:
→ Require manual paste
