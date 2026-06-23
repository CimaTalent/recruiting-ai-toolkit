---
name: interview-feedback-form-builder
description: Generate Google Forms for interview feedback and scoring. Creates separate forms for each interview stage (Recruiter Screener, Hiring Manager, Panel Debrief, CEO One-on-One) with competency proficiency rating, recommendation scale, and comments. Integrates with core competencies from hiring workflow to automatically populate form questions. Triggers on requests like "create feedback forms", "build interview scoring forms", "interview evaluation forms", or when user provides role-specific competencies and interview stages.
---

# Interview Feedback Form Builder

This skill generates professional Google Forms for collecting interview feedback and candidate evaluations. Forms are customized per interview stage and role, with built-in competency assessment, proficiency rating, and recommendation tracking.

## What This Skill Does

Given:
- Role name (e.g., "Senior Managing Director of Academics")
- 5 core competencies (from hiring workflow)
- Interview stage (Recruiter Screener, Hiring Manager, Panel Debrief, CEO One-on-One)

This skill generates:
1. **Separate Google Form for each interview stage**
2. **Interview feedback form with:**
   - Interviewer name (short text)
   - Candidate name (short text)
   - Interview date (date picker)
   - 5 competency rating questions (multiple choice: Foundation, Intermediate, Advanced, Expert)
   - Additional comments section (long text)
   - Recommendation question with color-coded options (Red, Yellow, Green)
3. **Pre-populated form descriptions and help text**
4. **Shareable links for each form**

## How to Use This Skill

### Step 1: Gather Required Inputs
You need:
- ✅ Role name (e.g., "Senior Managing Director of Academics")
- ✅ 5 core competencies with definitions
- ✅ Interview stage (Recruiter Screener, Hiring Manager, Panel Debrief, CEO One-on-One)
- ✅ Access to Google Drive to create forms

**STOP POINT**: If any of the above are missing, flag it clearly and do not proceed.

### Step 2: Confirm Form Details
Verify with the user:
- [ ] Competencies are correct and finalized
- [ ] Interview stage is clear
- [ ] User wants separate forms for each stage (default: YES)
- [ ] User wants recommendation scale with Red/Yellow/Green (default: YES)

### Step 3: Generate Form Structure

For each interview stage, create a form with this structure:

**Form Title:** `[Role Title] - [Interview Stage] Feedback Form`

**Form Description:** 
```
This form captures interview feedback for [Role Title] candidates at the [Interview Stage] 
stage. Please rate the candidate's proficiency on each core competency and provide your 
overall recommendation.

Estimated time: 5-10 minutes
```

**Form Sections:**

#### Section 1: Interviewer & Candidate Info
- **Interviewer Name** (required, short text)
  Help text: "Your full name"
  
- **Candidate Name** (required, short text)
  Help text: "Full name of the candidate interviewed"
  
- **Interview Date** (required, date picker)
  Help text: "Date the interview took place"

#### Section 2: Competency Assessment
For each of the 5 competencies, create a question:

**Question:** `[Competency Name] - [Brief Definition]`

**Type:** Multiple choice (required)

**Options:** 
1. Foundation
2. Intermediate
3. Advanced
4. Expert

**Help text:** Include 1-2 word example for each level from the competencies rubric

Example:
```
COMPETENCY: Academic Architecture & K-12 Coherence
Definition: Designs and ensures a coherent K–12 academic experience where curriculum, 
instruction, and assessment build intentionally across grade levels and content areas.

Rating options:
- Foundation: Understands single grade band
- Intermediate: Describes vertical alignment
- Advanced: Designs coherent programs across grades
- Expert: Defines organization's K-12 model
```

#### Section 3: Additional Comments
- **Additional Comments** (optional, paragraph text / long text)
  Help text: "Please provide any additional observations, examples, or context about the candidate's fit for this role."

#### Section 4: Final Recommendation
- **Overall Recommendation** (required, multiple choice with descriptions)

**Options with descriptions:**

🔴 **No** - Not a strong fit. This candidate does not demonstrate sufficient proficiency 
in key competencies for this role. I would not recommend advancing to the next stage.

🟡 **With Reservations** - Potentially viable but has some gaps. This candidate shows 
promise in some areas but has notable concerns in one or more competencies. Recommend 
discussion with hiring team before advancing.

🟢 **Yes** - Strong fit. This candidate demonstrates solid competency across multiple 
areas and appears well-suited for the role. Recommend advancing to next stage.

🟢 **I think this person would succeed in this role** - Exceptional fit. This candidate 
demonstrates advanced or expert-level proficiency and shows strong potential to excel 
in this position. Highly recommend advancing.

**Help text:** "Based on your assessment above, what is your overall recommendation?"

### Step 4: Create Forms in Google Drive

**For each interview stage:**
1. Create a new Google Form
2. Name it: `[Role] - [Interview Stage] Feedback Form`
3. Add the role and stage info to the form description
4. Populate all questions exactly as specified above
5. Set response destination to a Google Sheet for data collection
6. Enable "Require sign-in" if desired (recommended)
7. Get shareable link

### Step 5: Organize in Google Drive

**Folder structure to create:**
```
[Role Name] - Interview Feedback Forms
├── Recruiter Screener Feedback Form
├── Hiring Manager Feedback Form
├── Panel Debrief Feedback Form
└── CEO One-on-One Feedback Form
```

Create a summary document with:
- All form links
- Instructions for interviewers
- Recommendation scale definitions
- Note about response collection

### Step 6: Share Forms with Interviewers

Provide the shareable links and include:
- Clear instructions on how to complete
- Timeline for completion
- Where to send forms (email, Drive folder, etc.)
- Who to contact with questions

## Form Content Guidelines

### Competency Descriptions
Use the exact competency definitions from the core competencies rubric. Keep descriptions concise (1-2 sentences).

### Help Text
Provide brief guidance for each proficiency level. Reference actual behaviors from the rubric.

### Recommendation Scale
The 4-color scale should be clear:
- **Red (No):** Deal-breaker issues, not ready
- **Yellow (With Reservations):** Some gaps, needs discussion
- **Green (Yes):** Strong fit, recommend advancing
- **Green+ (Would Succeed):** Exceptional fit, highly recommend

### Comments Field
Make this optional and encourage interviewers to provide:
- Specific examples from the interview
- Evidence supporting their rating
- Any standout strengths or concerns
- Questions for the hiring committee

## Key Principles

**Role-Specific:** Forms are customized to the exact role competencies and interview stage.

**Easy to Complete:** Simple structure takes 5-10 minutes per interviewer.

**Consistent Framework:** All stages use the same competency rating scale for consistency.

**Actionable Feedback:** Recommendation scale is clear and tied to advancement decisions.

**Data-Driven:** Responses feed into a shared Sheet for easy analysis and comparison.

## Workflow Checks

- [ ] Role name and competencies identified?
- [ ] All 5 competencies have clear definitions?
- [ ] Interview stages confirmed (4 separate forms)?
- [ ] Google Drive access verified?
- [ ] Form structure reviewed for accuracy?
- [ ] Forms created and tested?
- [ ] Shareable links generated?
- [ ] Folder structure organized in Drive?
- [ ] Interviewers have links and instructions?

## Example Form Questions

### RECRUITER SCREENER FORM

**Title:** Senior Managing Director of Academics - Recruiter Screener Feedback Form

**Competency Question Examples:**
1. "Academic Architecture & K-12 Coherence - Does this candidate demonstrate understanding of K-12 systems and coherence?"
   - Foundation / Intermediate / Advanced / Expert

2. "Instructional Leadership & Equity - Does this candidate show commitment to equitable instruction?"
   - Foundation / Intermediate / Advanced / Expert

### HIRING MANAGER INTERVIEW FORM

**Title:** Senior Managing Director of Academics - Hiring Manager Interview Feedback Form

**Same competency questions, but help text emphasizes:**
- Depth of strategic thinking
- Ability to lead teams
- Evidence of driving outcomes
- Communication clarity

### PANEL DEBRIEF FORM

**Title:** Senior Managing Director of Academics - Panel Debrief Interview Feedback Form

**Focus on:**
- Problem-solving approach
- Quality of analysis
- Trade-off navigation
- Communication of complex ideas

### CEO ONE-ON-ONE FORM

**Title:** Senior Managing Director of Academics - CEO One-on-One Interview Feedback Form

**Focus on:**
- Cultural fit and values alignment
- Leadership presence
- Vision clarity
- Partnership readiness

## Notes for Claude Using This Skill

- Always verify competencies match the role's core competencies rubric
- Confirm interview stage before creating form
- Test form submission to ensure it works properly
- Provide clear instructions to interviewers
- Set up response collection sheet to track feedback
- Consider enabling "Require sign-in" for accountability
- Share forms with all interviewers at same time for consistency
- Follow up after interview stage to collect all feedback

## Integration with Hiring Workflow

This skill works best in conjunction with the **hiring-workflow-generator** skill:
1. Create core competencies (hiring-workflow-generator)
2. Build interview guides (hiring-workflow-generator)
3. Create feedback forms (this skill)
4. Conduct interviews using guides
5. Collect feedback via forms
6. Analyze responses in shared Sheet
7. Make advancement decisions

## Google Forms Best Practices

**Form Settings to Enable:**
- Require sign-in (if using with organization)
- Shuffle question order (optional, for consistency)
- Collect email addresses (optional, for tracking)
- Response destination: Google Sheet (required)
- Notifications: Email when form submitted (optional)

**After Responses Collected:**
- Review responses in Google Sheet
- Use Sheet functions to calculate average ratings per competency
- Create summary dashboard for hiring team
- Track recommendation patterns across interviewers

---

## Template Variables for Form Creation

When creating forms, use these standard elements:

**Form Title Format:**
`[Role Title] - [Interview Stage] Feedback Form`

**Form Description Format:**
```
This form captures interview feedback for [Role Title] candidates at the [Interview Stage] 
stage. Please rate the candidate's proficiency on each core competency and provide your 
overall recommendation.

Estimated time: 5-10 minutes
```

**Competency Question Format:**
`[Competency Name] - [Definition]`

**Recommendation Scale Definitions:**

🔴 No
- Not a strong fit
- Does not demonstrate sufficient proficiency
- Do not recommend advancing

🟡 With Reservations  
- Potentially viable with gaps
- Shows promise in some areas
- Notable concerns in one or more competencies
- Recommend hiring team discussion

🟢 Yes
- Strong fit
- Solid competency across multiple areas
- Well-suited for the role
- Recommend advancing to next stage

🟢 I think this person would succeed in this role
- Exceptional fit
- Advanced/expert proficiency
- Strong potential to excel
- Highly recommend advancing
