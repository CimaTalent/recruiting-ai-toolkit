---
name: listening-tour-feedback-synthesizer
description: Synthesize listening tour stakeholder feedback into actionable insights. Takes compiled listening tour responses and automatically extracts themes, identifies top priorities, generates insights about what's working and what needs attention, and produces a professional synthesis report. Use this after conducting listening tour sessions to analyze stakeholder input without hours of manual synthesis work.
---

# Listening Tour Feedback Synthesizer

Automatically analyzes listening tour responses and produces insights and priorities your new leader should know.

## What This Skill Does

Takes raw listening tour feedback from stakeholders and transforms it into:

1. **Key Themes** — What topics stakeholders mentioned most
2. **Top Priorities** — Ranked list of what matters to your organization
3. **Executive Summary** — High-level insights about stakeholder sentiment
4. **What's Working** — Highlights of positive feedback
5. **Challenges to Address** — What needs attention
6. **Strategic Opportunities** — Where the new leader can make an impact

Produces a professional markdown report ready to share with your hiring committee and brief the new leader.

## When to Use This Skill

Use this after conducting listening tour sessions. Trigger with:
- "Synthesize listening tour feedback"
- "Analyze stakeholder responses from listening sessions"
- "Generate synthesis report for listening tour"
- "What themes emerged from our listening tour?"

Perfect timing: After all listening tour sessions are complete (1-2 weeks into hiring process).

## Required Input

You'll need to compile stakeholder responses into a structured format with:

**For each stakeholder:**
- Stakeholder role/title (optional but helpful for context)
- What excites them about the work/organization
- Challenges they see
- Top 3 priorities for the new leader
- Desired attributes/characteristics

**Format:**
```
[
  {
    "stakeholder": "Elementary School Principal",
    "whatExcites": "Strong commitment to equitable instruction",
    "challenges": "Need better alignment between grade levels",
    "priorities": "K-12 coherence, instructional excellence, teacher development",
    "attributes": "Systems thinker, equity-focused, collaborative"
  },
  {
    "stakeholder": "High School Dean",
    "whatExcites": "Rigorous academic standards across the network",
    "challenges": "Sustainability of special education services with budget constraints",
    "priorities": "Systems design, cross-functional collaboration, student outcomes",
    "attributes": "Strategic, operationally minded, experienced"
  }
]
```

## Output

Professional markdown report containing:

**Executive Summary**
- Key takeaway about stakeholder sentiment and alignment
- High-level insights

**Key Themes** (ranked by frequency)
- What stakeholders talked about most
- Percentage of mentions for each theme
- Helps identify organizational priorities

**Top Priorities** (ranked by mention count)
- What stakeholders want new leader to focus on
- How many times mentioned
- Ready to brief new leader

**Strategic Opportunities**
- Where new leader can have immediate impact
- Based on intersection of themes and priorities

**What's Working Well**
- Positive feedback from stakeholders
- Strengths to build on

**Challenges to Address**
- Issues stakeholders raised
- Problems new leader should understand

## How It Works

### Data Analysis
Skill automatically:
- Counts mentions of key topics (themes)
- Tags feedback by category
- Identifies sentiment (excitement vs. concerns)
- Recognizes patterns across multiple stakeholders

### Theme Extraction
Auto-identifies themes like:
- K-12 Alignment / Coherence
- Equity & Access
- Instructional Quality
- Systems & Execution
- Data & Accountability
- Leadership & Culture
- Student Outcomes
- Compliance & Quality

### Priority Ranking
Tallies priority mentions and ranks them by frequency to show what matters most to stakeholders.

### Insight Generation
Produces observations like:
- "Strong optimism about current work and future direction"
- "Significant challenges identified that require immediate attention"
- "Stakeholders have clear, specific expectations for new leader"
- "High engagement in listening process"

## Example Output

A complete synthesis report looks like:

```
# Listening Tour Synthesis Report

Executive Summary
- 15 stakeholders participated in listening sessions
- Strong consensus on top 3 priorities
- Mixed sentiment on current special education sustainability
- Clear expectations for new leader's approach

Key Themes
- Systems & Execution (24% of mentions)
- Student Outcomes (19%)
- Compliance & Quality (19%)
- Instructional Quality (14%)
- K-12 Alignment (10%)
- Equity & Access (7%)
- Data & Accountability (7%)

Top Priorities for New Leader
1. K-12 coherence (mentioned 7 times)
2. Instructional excellence (mentioned 6 times)
3. Teacher development (mentioned 5 times)
4. Systems sustainability (mentioned 5 times)
5. Cross-functional collaboration (mentioned 4 times)

Strategic Opportunities
- Strengthen cross-functional systems design
- Enhance data culture in decision-making
- Prioritize equitable access across network

What's Working Well
- Strong commitment to student achievement
- Collaborative culture among school leaders
- Focus on rigorous, inclusive instruction

Challenges to Address
- Grade-level alignment gaps in curriculum
- Special education service sustainability
- Resource constraints affecting implementation
```

## Quality Standards

The synthesis report:
- ✓ Is based only on what stakeholders actually said
- ✓ Represents themes accurately (weighted by mention frequency)
- ✓ Highlights both strengths and challenges
- ✓ Is actionable for new leader and hiring committee
- ✓ Is professional and ready to share
- ✓ Takes context into account (not just surface-level counts)

## Integration with Other Skills

Works with:
- **mega-hiring-workflow** — Use listening tour agenda from this skill to conduct sessions
- **interview-feedback-analyzer** — After hiring, new leader can use synthesized feedback to understand org priorities

## Time Saved

Without automation: 4-6 hours manually reading, tagging, synthesizing feedback

With this skill: 30 minutes to compile feedback + 5 minutes to run synthesis = clear, professional report

## How to Use

### Step 1: Conduct Listening Tours
Use the listening tour agenda from mega-hiring-workflow skill to run stakeholder sessions.

### Step 2: Compile Feedback
After sessions, gather responses in structured JSON format (template provided above).

### Step 3: Trigger Skill
Tell me: "Synthesize listening tour feedback" and paste/provide your compiled data.

### Step 4: Review Report
Get professional synthesis report with themes, priorities, and insights.

### Step 5: Share with Team
Use report to:
- Brief hiring committee on stakeholder input
- Share key priorities with new leader before they start
- Highlight opportunities for early impact
- Identify potential challenges to address

## Data Privacy

- Stakeholder names/roles kept confidential in final report (if desired)
- Quotes can be anonymized
- Focus is on themes and patterns, not individual voices
- Report suitable for sharing widely

## Success Indicators

You'll know this skill worked if:
- Hiring committee understands stakeholder priorities clearly
- Themes make sense given your organization
- Top priorities align with your sense of what matters
- Report is immediately usable for briefing new leader
- You saved 4+ hours vs. doing this manually

---

## Get Started

Ready to synthesize feedback? Provide your compiled stakeholder responses and this skill will handle the analysis automatically.
