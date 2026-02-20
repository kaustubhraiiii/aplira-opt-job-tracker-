# Product Requirements Document (PRD)

## 1. Product Overview

- **Project Name**: Aplira
- **Version**: 1.0 (Auth + Sync)
- **Platform**: Chrome Extension (Manifest V3)
- **Owner**: Kaustubh Rai
- **Target Users**: F1 / OPT job seekers

Aplira is an AI-powered job application tracker designed specifically for F1/OPT students. It combines application tracking, OPT unemployment monitoring, visa tagging, and AI resume tailoring into a lightweight browser-native tool.

---

## 2. Problem Statement

International students on OPT face unique challenges:

1. Tracking job applications across multiple platforms.
2. Monitoring OPT unemployment days (90-day limit).
3. Identifying visa-friendly employers.
4. Tailoring resumes quickly for each role.

Existing tools (Notion, Excel, Huntr) are generic and do not address OPT-specific constraints.

---

## 3. Goals & Objectives

### Business Goals
- 100 installs within 14 days
- 40% activation (save ≥3 jobs)
- 30% users set OPT start date
- 50% of active users generate at least 1 AI output

### User Goals
- Save jobs in < 10 seconds
- See OPT unemployment days instantly
- Prioritize visa-friendly roles
- Generate tailored bullets in < 30 seconds

---

## 4. Success Metrics

- Activation Rate ≥ 40%
- AI Usage ≥ 50% of activated users
- Median job-save time < 10 sec
- 7-day retention ≥ 25%

---

## 5. Target Personas

### Persona 1: OPT Engineer
- 22–27 years old
- On F1 OPT
- Applies to 10+ roles weekly
- Uses LinkedIn heavily
- Needs unemployment visibility

### Persona 2: International Grad
- Internship seeker
- Unsure about visa sponsorship
- Needs structure in job search

---

## 6. Core Features (P0)

### 1. Supabase Authentication
- Email/password login
- Google OAuth
- Persistent session in extension
- Logout capability

### 2. Job Save & Sync
- Extract job details from page
- Editable before save
- Persist to Supabase
- Sync across devices

### 3. Pipeline View (Side Panel)
- Status filtering
- Visa tag badges
- Inline status updates
- Open original job link

### 4. Visa-Friendly Tag
- Manual tag:
  - visa_friendly
  - sponsorship_required
  - unknown
- Visible on cards
- Editable anytime

### 5. OPT Unemployment Tracker
- User sets OPT start date
- Calculates:
  - Days elapsed
  - Days remaining (90-day baseline)
- Progress bar visualization

### 6. AI Resume Tailor
- Inputs:
  - Job description
  - Project summary
- Output:
  - 3–4 ATS-friendly bullets
- Copy-to-clipboard
- Cached per job

---

## 7. Out of Scope (v1)

- Automatic visa detection
- Employer database
- Payment/subscriptions
- Email tracking
- ATS auto-apply automation
- Immigration advice

---

## 8. Non-Functional Requirements

- Popup load < 300ms
- API latency < 5s typical
- Secure auth (Supabase JWT)
- No API keys exposed client-side
- WCAG AA color contrast
