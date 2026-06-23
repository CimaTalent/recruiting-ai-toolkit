# Recruiting AI Toolkit

A library of AI-powered recruiting workflows built and deployed in production across real client engagements.

Built by **Diana Andrade O'Neal** — Talent Acquisition leader and independent recruiting consultant based in Brooklyn, NY.

> 📧 diana@cimatalentllc.com · [LinkedIn](https://www.linkedin.com/in/dianaandrade41/)

---

## Why This Exists

Most recruiting teams spend hours on work that is fundamentally templated — writing interview guides, synthesizing feedback, drafting outreach, evaluating candidates against rubrics. That time should go toward judgment: understanding people, building relationships, making better hiring decisions.

This toolkit is what I built to close that gap. Each workflow started as a real problem encountered during a client engagement, got designed into a repeatable system, and was iterated based on live use. The skills here powered ~150 hires at a 17-site organization, 2 senior engineering placements that had been open for months, and multiple concurrent executive searches.

These are not demos. They run in production.

---

## Skills Index

### Full Hiring Lifecycle

| Skill | What It Does |
|---|---|
| [`hiring-workflow-generator`](skills/hiring-workflow-generator.md) | Transforms a JD + kickoff transcript into a complete hiring package: 5 competencies with 4 proficiency levels, 4 interview guides, performance task + rubric, tiered sourcing strategy, and LinkedIn announcement post — automatically saved to Google Drive |
| [`mega-hiring-workflow`](skills/mega-hiring-workflow.md) | Extended version for executive roles — adds listening tour agenda, audience-facing guide, and CEO one-on-one |
| [`interview-feedback-form-builder`](skills/interview-feedback-form-builder.md) | Generates stage-specific Google Forms for each interview round, auto-populated with role competencies |
| [`interview-feedback-analyzer`](skills/interview-feedback-analyzer.md) | Synthesizes feedback from all 4 interview stages — calculates competency averages, flags calibration gaps, tallies recommendation votes, outputs a final hiring recommendation |
| [`listening-tour-feedback-synthesizer`](skills/listening-tour-feedback-synthesizer.md) | Aggregates stakeholder listening tour responses into themes, priorities, and a synthesis report |

### Candidate Evaluation

| Skill | What It Does |
|---|---|
| [`se-candidate-narrative`](skills/se-candidate-narrative.md) | Generates a 250–350 word story-driven candidate narrative from interview transcript and available candidate materials, framed against role-specific requirements |

### Candidate Outreach

| Skill | What It Does |
|---|---|
| [`candidate-outreach-workflow`](skills/candidate-outreach-workflow.md) | Researches a candidate across the web and generates 5 customized outreach messages (LinkedIn personal, LinkedIn mission, email formal, email direct, GitHub/Twitter comment) + creates a Notion pipeline entry. Triggered by a name or LinkedIn URL. Configurable for any role. |

---

## How These Work

Each file in `/skills` is a **Claude skill** — a structured markdown prompt that instructs an AI assistant how to execute a specific workflow end-to-end. Each skill defines:

- **What it does** and when to trigger it
- **Configuration** — values to set per role or client engagement
- **Step-by-step instructions** the AI follows
- **Output specifications** — format, length, where to save, what to return
- **Quality checks** to run before delivering output

Skills connect to live tools via MCP (Model Context Protocol): Google Drive, Google Forms, Notion, Gmail, and document generators (`.docx`). The AI reads inputs, executes the workflow, and delivers structured outputs — no manual assembly required.

---

## System Architecture

```
JD + Kickoff Transcript
        │
        ▼
hiring-workflow-generator ─────────────────────────────────────────┐
        │                                                           │
        ├── Core Competencies Rubric (5 competencies, 4 levels)    │
        ├── Tiered Sourcing Strategy                               │
        ├── LinkedIn Announcement Post                             │
        ├── Recruiter Screener Guide                               │
        ├── Hiring Manager Interview Guide      ──► interview-feedback-form-builder
        ├── Panel Debrief Guide                                    │
        ├── CEO One-on-One Guide                                   │
        └── Performance Task + Rubric                              │
                                                                   │
Candidate Identified                                               │
        │                                                          │
        ├── candidate-outreach-workflow                            │
        │   (web research → pre-screen → 5 messages → Notion)     │
                                                                   │
Post-Interview                                                     │
        │                                                          │
        ├── interview-feedback-analyzer (aggregate → recommendation)│
        └── se-candidate-narrative (story-form summary for debrief)│
                                                                   ▼
                                          Complete hiring package in Google Drive
```

---

## Selected Results

- Closed 2 senior backend engineering roles at a cybersecurity startup in **6 weeks** — both had been open for multiple months prior
- Delivered ~150 hires at **95% fill rate** across a 17-site organization using infrastructure powered by these workflows
- Reduced hiring package creation from **weeks to hours** via `hiring-workflow-generator`
- Generated personalized, multi-channel candidate outreach researched and drafted in minutes per candidate

---

## Stack

**AI:** Claude (Anthropic) — workflow execution, synthesis, generation  
**Integrations:** Google Drive, Google Forms, Notion, Gmail, Slack (via MCP)  
**Document output:** `.docx` via `docx` npm library, Google Forms API  
**Sourcing tools referenced:** LinkedIn Recruiter, Juicebox AI, Greenhouse ATS
