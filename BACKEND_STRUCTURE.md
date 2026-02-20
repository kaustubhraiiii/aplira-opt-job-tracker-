# Backend Structure (Supabase)

## Tables

---

## users (managed by Supabase auth)

id UUID PK
email TEXT
created_at TIMESTAMP

---

## profiles

id UUID PK (references auth.users.id)
opt_start_date DATE
created_at TIMESTAMP
updated_at TIMESTAMP

RLS:
user_id = auth.uid()

---

## jobs

id UUID PK
user_id UUID (FK auth.users.id)
title TEXT
company TEXT
location TEXT
url TEXT
status TEXT
visa_tag TEXT
jd_text TEXT
created_at TIMESTAMP
updated_at TIMESTAMP

Indexes:
- user_id
- status

RLS:
user_id = auth.uid()

---

## ai_generations

id UUID PK
user_id UUID
job_id UUID
type TEXT
content TEXT
created_at TIMESTAMP

RLS:
user_id = auth.uid()
