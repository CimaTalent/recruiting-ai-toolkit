---
name: interview-feedback-analyzer
description: Synthesize interview feedback from all 4 interview stages into a data-driven hiring recommendation. Takes 4 interview feedback forms (Recruiter, Hiring Manager, Panel Debrief, CEO) and automatically calculates competency averages, measures interviewer consistency, tallies recommendation votes, and produces a final recommendation with supporting evidence. Use this after all 4 interviews are complete to generate an objective hiring decision backed by data.
---

# Interview Feedback Analyzer

Synthesizes 4 interview feedback forms into a data-driven hiring recommendation.

## What This Skill Does

Takes the 4 interview feedback forms (one from each stage) and produces:

1. **Overall Recommendation** — Hire, Hold, or Do Not Advance (with emoji and rationale)
2. **Competency Assessment** — Average proficiency for each competency
3. **Consistency Scores** — How much did interviewers agree or disagree?
4. **Recommendation Breakdown** — How many red/yellow/green votes from each interviewer
5. **Strengths Summary** — Which competencies are strongest
6. **Concerns Summary** — Which areas need attention
7. **Evidence Table** — All data in one place for hiring committee review

Produces a professional markdown report that removes bias and emotion from hiring decisions.

## When to Use This Skill

Use after all 4 interviews are complete for a candidate. Trigger with:
- "Analyze interview feedback for [Candidate Name]"
- "Generate hiring recommendation based on interview feedback"
- "Synthesize feedback from [Candidate]'s 4 interviews"

Perfect timing: Within 1-2 days of final (CEO) interview, before hiring committee meeting.

## Required Input

You'll need the 4 interview feedback forms with:

**For each of 4 interviews:**
- Interviewer name
- Interview stage (Recruiter / Hiring Manager / Panel / CEO)
- Competency ratings (5 competencies, each rated Foundation/Intermediate/Advanced/Expert)
- Overall recommendation (No / With Reservations / Yes / Would Succeed)
- Optional: Comments/observations

**Format:**
```
{
  "candidateName": "Jane Smith",
  "feedbackResponses": [
    {
      "interviewer": "Sarah Johnson",
      "stage": "Recruiter Screener",
      "competencies": [
        { "name": "Academic Architecture & K-12 Coherence", "level": "Advanced" },
        { "name": "Instructional Leadership & Equity", "level": "Advanced" },
        { "name": "Curriculum Design & Content Expertise", "level": "Intermediate" },
        { "name": "Leadership & Team Development", "level": "Advanced" },
        { "name": "Strategic Judgment & Decision-Making", "level": "Advanced" }
      ],
      "recommendation": "Yes",
      "comments": "Strong background in K-12 systems, asks insightful questions"
    },
    {
      "interviewer": "Marcus Chen",
      "stage": "Hiring Manager",
      "competencies": [
        { "name": "Academic Architecture & K-12 Coherence", "level": "Expert" },
        { "name": "Instructional Leadership & Equity", "level": "Advanced" },
        { "name": "Curriculum Design & Content Expertise", "level": "Advanced" },
        { "name": "Leadership & Team Development", "level": "Expert" },
        { "name": "Strategic Judgment & Decision-Making", "level": "Advanced" }
      ],
      "recommendation": "Would Succeed",
      "comments": "Exceptional team development experience, clear vision"
    },
    // ... Panel and CEO feedback similarly formatted
  ]
}
```

## Output

Professional report containing:

**Overall Recommendation**
- Clear hiring decision with emoji indicator
- Rationale explaining the recommendation
- Based on data, not intuition

**Competency Assessment Table**
Shows for each competency:
- Average score (1-4 scale)
- Proficiency level (Foundation/Intermediate/Advanced/Expert)
- Consistency (High/Moderate/Low) — did interviewers agree?
- Score range (e.g., "Scores: 3-4")

**Interview Recommendation Tally**
- Number who voted "No"
- Number who voted "With Reservations"
- Number who voted "Yes"
- Number who voted "Would Succeed"
- Shows consensus or disagreement

**Strengths**
- Lists competencies where candidate scored 3.0+ (Advanced or Expert)
- Shows what hiring committee should emphasize

**Concerns**
- Lists competencies below 1.5 or with disagreement between interviewers
- Flags areas to watch or address

## How It Works

### Scoring Algorithm

**Competency Averages:**
- Foundation = 1 point
- Intermediate = 2 points
- Advanced = 3 points
- Expert = 4 points
- Averages calculated from 4 interviewers

**Consistency Measurement:**
- High consistency = interviewers mostly agreed (std dev < 0.5)
- Moderate consistency = some variation (std dev 0.5-1.0)
- Low consistency = significant disagreement (std dev > 1.0)

**Recommendation Logic:**
- 3+ "Would Succeed" votes = Strongly Advance
- 3+ "Yes" votes and no "No" = Advance to Next Stage
- Multiple "No" votes = Do Not Advance
- Mixed votes = Hold/Continue Evaluation

### Intelligence

The skill considers:
- Raw scores (averaging across interviewers)
- Consistency (flagging disagreement)
- Consensus (looking at recommendation votes)
- Context (which competencies matter for this role)

## Example Report

```
# Interview Feedback Analysis

**Candidate:** Jane Smith
**Date:** April 28, 2026
**Interviews Completed:** 4

## Overall Recommendation

### 🟢 ADVANCE TO NEXT STAGE

**Rationale:** Strong consensus. Candidate demonstrates solid competency across multiple 
areas and clear potential for success in the role.

## Competency Assessment

| Competency | Average | Level | Consistency |
|-----------|---------|-------|-------------|
| Academic Architecture | 3.25 | Advanced | High |
| Instructional Leadership | 2.75 | Advanced | High |
| Curriculum Design | 2.50 | Advanced | Moderate |
| Leadership & Team Dev. | 3.50 | Expert | Moderate |
| Strategic Judgment | 3.25 | Advanced | High |

## Interview Recommendation Tally

- No: 0
- With Reservations: 0
- Yes: 2
- Would Succeed: 2

## Strengths

✓ Academic Architecture & K-12 Coherence (Advanced)
✓ Leadership & Team Development (Expert)
✓ Strategic Judgment & Decision-Making (Advanced)

## Concerns

No significant concerns identified.
```

## Quality Standards

The analysis:
- ✓ Is mathematically objective (scores averaged, not subjective)
- ✓ Flags inconsistency when interviewers disagreed
- ✓ Provides clear rationale for recommendation
- ✓ Is ready for hiring committee discussion
- ✓ Enables data-driven decision-making
- ✓ Reduces bias in hiring process

## Integration with Other Skills

Works with:
- **mega-hiring-workflow** — Uses interview forms created by this skill
- **interview-feedback-form-builder** — Compatible with forms from this skill

## Time Saved

Without automation: 2-3 hours manually tallying scores, averaging, creating tables, writing summary

With this skill: 5 minutes to compile feedback + 1 minute to run analysis = professional report with all data

## How to Use

### Step 1: Complete 4 Interviews
Use interview guides to conduct:
- Recruiter Screener
- Hiring Manager Interview
- Panel Debrief
- CEO One-on-One

### Step 2: Collect Feedback
Each interviewer completes the feedback form (competency ratings + recommendation).

### Step 3: Compile Responses
Gather all 4 forms' data in structured format (template provided above).

### Step 4: Trigger Skill
Tell me: "Analyze interview feedback for [Candidate Name]" and provide compiled data.

### Step 5: Review Report
Get objective analysis with:
- Competency averages
- Consistency scores
- Clear recommendation with rationale
- Strength and concern summary

### Step 6: Hiring Committee Discussion
Use report to:
- Present objective data to hiring team
- Discuss competency strengths and gaps
- Make informed advancement decision
- Have documented reasoning for decision

## Data Insights You Get

From the analysis, you can see:
- **Where candidate is strong** — Advanced/Expert competencies
- **Where there's agreement** — Consistency scores show if all interviewers saw the same thing
- **Where there's concern** — Low scores or inconsistency
- **Overall fit** — The recommendation synthesizes everything

## Removing Bias

This skill helps remove several biases:
- Recency bias (doesn't just remember last interview)
- Halo effect (averages across interviews, not swayed by one good performance)
- Gut feeling (uses data, not intuition)
- Interviewer differences (shows consistency/disagreement clearly)

## Success Indicators

You'll know this skill worked if:
- Hiring committee sees clear data-driven recommendation
- Everyone can understand the scoring
- Any disagreements between interviewers are visible and discussable
- You saved 2+ hours vs. doing this manually
- Decision is defensible based on documented evidence

---

## Get Started

Ready to analyze a candidate? Provide the 4 interview feedback forms and this skill will generate your hiring recommendation backed by data.

Perfect for:
- Making confident hiring decisions
- Discussing with hiring committee
- Documenting your reasoning
- Comparing multiple candidates objectively
