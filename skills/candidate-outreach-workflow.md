---
name: candidate-outreach-workflow
description: >
  Research a candidate and run a full recruiting outreach workflow automatically.
  Given a candidate name and/or LinkedIn URL, this skill researches their background
  across the web, generates 5 customized outreach messages (LinkedIn personal,
  LinkedIn mission, email formal, email direct, GitHub/Twitter comment), and creates
  a structured entry in a candidate pipeline database (Notion). Configurable for any
  role or company. Trigger any time a recruiting workflow is implied — pasted LinkedIn
  URLs, names + companies, "add this person", "reach out to", "research this candidate".
---

# Candidate Research & Outreach Workflow

## What This Skill Does

Given a candidate's name and LinkedIn URL, this skill automatically:

1. **Pre-screens** the candidate against a role's must-have requirements
2. **Researches** the candidate across the web (LinkedIn, GitHub, personal site, Twitter/X)
3. **Generates 5 tailored outreach messages** customized to their specific background
4. **Creates a Notion pipeline entry** with all relevant candidate data
5. **Recommends the best outreach channel** based on where the candidate is most active

## Configuration (Set Per Engagement)

Before running, configure these values for the specific role and client:

```
ROLE_TITLE: [e.g., "Senior Backend Engineer"]
JD_LINK: [link to job posting]
CALENDAR_LINK: [link to recruiter's calendar]
NOTION_DATABASE_ID: [Notion database ID for candidate pipeline]
RECRUITER_NAME: [your name]
RECRUITER_TITLE: [your title, e.g., "Talent Acquisition, Acme Corp"]
MUST_HAVES: [list of non-negotiable requirements for pre-screen]
STRONG_SIGNALS: [list of preferred but not required qualifications]
SKILL_TAGS: [list of tags to apply in Notion, e.g., Backend, Python, Kubernetes]
```

---

## Step 1: Parse Candidate Input

Extract from whatever the user provides:
- Candidate name (required)
- LinkedIn URL (required)
- Email, company, title, years of experience, skills/tags, match score (optional)

Don't ask for missing optional fields — proceed with what you have. If name or LinkedIn URL is missing, ask only for those.

---

## Step 2: Quick Pre-Screen

Before doing full research, run 1–2 searches to get the candidate's current role, company, and rough career background. Then assess against the configured MUST_HAVES.

**Pre-screen output:**
- Score out of 10
- One-paragraph rationale covering: years of experience, relevant systems/domain, tech stack overlap, startup fit, and notable gaps
- Clear go/no-go call:
  - **Score 7+**: Good fit. Proceed to full research and outreach.
  - **Score below 7**: Not a fit. Explain why and stop — don't waste time on full research for weak matches.

If borderline (around 7), lean toward proceeding but flag concerns clearly.

---

## Step 3: Full Research (only if pre-screen score is 7+)

Run web searches to build a complete picture. Do all searches in parallel:

1. `[name] [company] [role title] LinkedIn` — confirm current role, prior companies, career arc
2. `[name] GitHub` — find GitHub username and notable repos/tech focus
3. `[name] [company] site:twitter.com OR site:x.com` — find Twitter/X handle if present
4. If a personal website surfaces, fetch it for blog topics, projects, and technical interests

**What to extract:**
- Current role and company
- Previous companies (especially high-signal ones)
- Tech stack (languages, infrastructure, systems)
- GitHub username, notable repos/contributions, recency of activity
- Twitter/X handle and approximate posting frequency
- LinkedIn activity signals (posts, articles, comments)
- Personal blog (posting frequency, recency)
- Location, years of experience, education
- Notable open-source work, writing, or public technical presence

**Channel activity assessment:**

Pick ONE channel as the best contact method and commit to it. Score each available channel:

- **GitHub:** 100+ followers OR recent commits in last 3 months OR 50+ repos = strong signal
- **Twitter/X:** Visible recent posts, 500+ followers, active engagement = strong signal
- **LinkedIn:** Default fallback only if GitHub and Twitter/X signals are weak
- **Email:** Always use if the candidate's email was provided directly

Write one sentence explaining the recommendation (e.g., "GitHub — Pull Shark badge and 3 repos updated this month"). Do not hedge with two channels.

---

## Step 4: Generate 5 Outreach Messages

Write 5 distinct message variants, each tailored to something specific from the candidate's background. Generic messages don't work — every message must include at least one detail that proves you looked at their actual work.

**Tone guidelines:**
- Keep it short. Long messages get ignored.
- Lead with something specific (a project, a company, a technology they worked on)
- Be honest about the role and company — don't oversell
- Each variant should feel meaningfully different
- Avoid em dashes (—) — they read as AI-generated. Use a hyphen, a period, or restructure

### Message 1: LinkedIn — Personal
Casual and direct. Open with something specific about their work. Brief intro as recruiter and company. One sentence on why their background is relevant. Link to JD. Soft ask. Max ~4 sentences.

### Message 2: LinkedIn — Mission
Lead with the *type of problem* the candidate works on and connect it to what the company is building. Skip flattery. Frame the role as a challenge worth considering. Include calendar link. Max ~4 sentences.

### Message 3: Email — Formal
**Subject:** "[Role Title] opportunity at [Company]"

Brief intro → 1-2 sentences on why their background is relevant (specific) → 1 sentence on the role → JD link → calendar link → email signature.

### Message 4: Email — Direct
**Subject:** "Quick question — open to exploring?"

3-4 lines max: what caught your eye → what the role is → both links. Nothing more.

### Message 5: GitHub Comment or Twitter/X DM
Reference a specific repo or type of work observed. If no GitHub, use Twitter/X. Under 3 sentences. Include JD link.

**Email signature for all emails:**
```
[RECRUITER_NAME]
[RECRUITER_TITLE]
```

---

## Step 5: Create Notion Entry

Create a page in the configured Notion candidate pipeline database.

**Standard fields to populate:**

| Field | Value |
|---|---|
| Name | Candidate full name |
| Company | Current company |
| Role | Current job title |
| LinkedIn | LinkedIn URL |
| GitHub | GitHub profile URL (if found) |
| Twitter/X | Twitter/X profile URL (if found) |
| Location | City, State (if found) |
| Years of Experience | Number (if estimable) |
| Tags | Role-relevant skill tags from SKILL_TAGS config |
| Match Score | Number 1–10 (if provided; otherwise leave blank) |
| Outreach Status | "Not Contacted" |
| Best Contact Method | LinkedIn / Email / GitHub / Twitter/X |
| Email Draft | Message 4 (direct email) — subject line first, then body |
| Notes | 2-3 sentence summary of background and why they're relevant |

Include all 5 outreach messages in the Notion page body as labeled sections.

---

## Step 6: Present Results

Show a clean summary with:

1. **Candidate profile** — name, current role/company, location, key links
2. **📡 Recommended outreach channel** — prominently placed, with one-sentence rationale
3. **All 5 messages** — numbered, labeled, ready to copy. Put ⭐ next to the message matching the recommended channel
4. **Notion link** to the newly created entry
5. **Suggested next steps:** send the ⭐ message first → update Notion status to "Message Sent" → set follow-up ~4 days out → add match score if missing

---

## Notes

- Don't ask clarifying questions before starting — run the workflow and surface gaps at the end
- If no GitHub profile is found, skip that Notion field and adapt Message 5 to Twitter/X or a generic community comment
- If the candidate's email was provided, set Best Contact Method to "Email"
- The Email Draft Notion field always gets Message 4 (direct email), ready to copy-paste
