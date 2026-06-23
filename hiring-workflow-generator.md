---
name: hiring-workflow-generator
description: Generate complete hiring packages for any role. Use this skill whenever a user has a job description and kickoff meeting transcript and needs to build a structured hiring process. The skill creates a Google Drive folder structure, develops 5 core competencies with 4 proficiency levels each, generates a tiered sourcing strategy, creates a LinkedIn announcement post, and generates all interview guides (recruiter screener, hiring manager, panel debrief, CEO one-on-one), a performance task with rubric, and a competencies rubric. Automatically organizes everything into folders. Triggers on requests like "create hiring process", "build interview guides", "develop competencies for this role", "sourcing strategy", or when the user provides a JD + meeting transcript. FLAG AND STOP if any required input is missing before proceeding.
---

# Hiring Workflow Generator

This skill transforms a job description and kickoff meeting transcript into a complete, structured hiring package for any role.

## What This Skill Does

Given:
- Job description
- Kickoff meeting transcript
- Time requirements for performance task (to be asked)

This skill generates:
1. **Core Competencies Rubric** - 5 competencies with 4 proficiency levels (Foundation, Intermediate, Advanced, Expert)
2. **Recruiter Screener** - Initial screening questions organized by competency
3. **Hiring Manager Interview Guide** - In-depth interview questions organized by competency with objectives
4. **Panel Debrief Interview Guide** - Questions to evaluate candidate's performance task
5. **CEO One-on-One Guide** - Brief final conversation guide
6. **Performance Task** - Realistic role-based task with evaluation rubric
7. **Sourcing Strategy** - Tiered sourcing approach (Tier 1 Bull's Eye → Tier 4) with specific sourcing channels and strategies
8. **LinkedIn Announcement Post** - Ready-to-publish post announcing the search

All materials are saved to a Google Drive folder (created if it doesn't exist) with this structure:
```
[Role Name]
├── Core Competencies Rubric
├── Sourcing & Marketing
│   ├── Sourcing Strategy
│   └── LinkedIn Announcement Post
├── Interview Guides
│   ├── Recruiter Screener
│   ├── Hiring Manager Interview Guide
│   ├── Panel Debrief Interview Guide
│   └── CEO One-on-One Guide
└── Performance Task
    ├── Prompt
    └── Candidate Submissions
```

## How to Use This Skill

### Step 1: Gather Required Inputs
You need:
- ✅ Job description (text or document)
- ✅ Kickoff meeting transcript (text or document)
- ✅ Role title/name
- ✅ Performance task time requirement (ask the user if not provided)

**STOP POINT**: If any of the above are missing, flag it clearly to the user and do not proceed.

### Step 2: Analyze & Extract
From the JD + transcript, identify:
- Key responsibilities and success metrics
- Team context and reporting structure
- Technical vs. soft skill requirements
- Company culture/values emphasis
- Unique challenges or priorities

### Step 3: Create Sourcing Strategy
Develop a tiered sourcing approach with specific channels and tactics:

**Tier 1: Bull's Eye** 
- The exact profile you're looking for
- Direct competitors or adjacent industries
- Specific companies, titles, and skill combinations to target
- Sourcing channels: Direct outreach, targeted LinkedIn search, executive recruiters
- Messaging: Focus on specific pain points they likely have

**Tier 2: Strong Adjacent**
- Similar roles or related industries
- Slightly different background but transferable skills
- Expansion of companies/networks from Tier 1
- Sourcing channels: LinkedIn recruiter, industry events, referral networks
- Messaging: Show how their experience translates

**Tier 3: Growth Potential**
- Earlier in career but demonstrates the core competencies
- Coming from different industries but with relevant skills
- High-potential candidates who may need mentoring
- Sourcing channels: Universities, talent networks, community/nonprofit organizations
- Messaging: Growth opportunity, high-impact role

**Tier 4: Long-Tail Opportunities**
- Emerging talent, potential from non-traditional backgrounds
- Passive candidates who might not actively be looking
- Boomerangs or previous candidates
- Sourcing channels: Social media, industry forums, cold outreach, networking events
- Messaging: Career change opportunity, unique upside

For each tier, specify:
- Target companies/industries
- Job titles to search for
- Key skills/certifications to look for
- Estimated # of candidates available
- Primary sourcing channels
- Outreach messaging approach

### Step 4: Create LinkedIn Announcement Post
Write a compelling LinkedIn post that:
- Announces the search in an engaging way
- Highlights key aspects of the role and what makes it exciting
- Describes the ideal candidate profile (without being too prescriptive)
- Includes a call-to-action for referrals or direct interest
- Reflects company culture and values
- Is 3-5 paragraphs, ready to publish immediately
- Includes relevant hashtags

### Step 5: Develop Core Competencies
Create exactly 5 competencies based on the role. For each competency:
- **Name** - Clear, concise title
- **Definition** - 1-2 sentence description of what this competency means for this role
- **4 Proficiency Levels**:
  1. **Foundation** - Basic understanding; needs guidance
  2. **Intermediate** - Can perform independently; occasional support needed
  3. **Advanced** - Expert-level; can guide others
  4. **Expert** - Sets standards for the organization; strategic impact

Include observable behaviors/examples for each level specific to the role.

### Step 6: Create Recruiter Screener
- 8-12 screening questions organized by competency
- Quick questions suitable for 20-30 minute calls
- Questions should uncover deal-breakers or strong fits early
- Format: Question | Competency | What you're listening for

### Step 7: Create Hiring Manager Interview Guide
- **Interview Objectives** - 3-4 clear goals for this interview
- 12-16 open-ended questions organized by competency
- Each question section includes:
  - The question
  - Competency it assesses
  - What you're looking for
  - Red flags (what NOT to see)
  - Green flags (what you want to see)
- Suggested interview duration

### Step 8: Create Performance Task
- **Task Description** - Realistic scenario matching actual job responsibilities
- **Time Requirement** - Ask user if not provided (typically 1-3 hours)
- **Instructions** - Clear, specific deliverables expected
- **Evaluation Rubric** with 4-5 criteria matching core competencies
- **Rubric Levels**: Foundation, Intermediate, Advanced, Expert (matching competency framework)

### Step 9: Create Panel Debrief Interview Guide
- **Debrief Objectives** - What you want to learn from discussion
- 10-12 questions organized by competency
- Questions explore the "why" behind their approach and decisions
- Questions should uncover:
  - How they approached the problem
  - Trade-offs they made and why
  - Collaboration/communication approach
  - How they'd improve their solution

### Step 10: Create CEO One-on-One Guide
- Brief, 15-20 minute conversation
- 5-7 questions focused on:
  - Cultural fit
  - Leadership presence
  - Vision alignment
  - Excitement about the role/company
  - Any final questions or concerns

### Step 11: Create Google Drive Folder Structure
- Create main folder named [Role Name] if it doesn't exist
- Create subfolders as specified above
- Save each document to appropriate folder
- Return links to user

## Key Principles

**Competency-Centered**: All interview guides are organized by the 5 core competencies, not generic categories. This ensures consistent evaluation.

**Observable & Specific**: Questions and rubrics describe observable behaviors, not vague traits. Example: Instead of "leadership", ask about specific situations where they influenced others.

**Realistic Tasks**: Performance tasks mirror actual job responsibilities. A sales leader should do sales work; an engineer should solve engineering problems.

**Consistent Framework**: All materials use the same 4-level proficiency scale for consistency across the hiring process.

**No Surprises**: Always flag missing information before proceeding. Ask about time requirements upfront.

## Workflow Checks

- [ ] All required inputs present? (JD, transcript, role name, time requirement)
- [ ] Sourcing strategy created with 4 tiers?
- [ ] LinkedIn announcement post written and ready?
- [ ] 5 competencies identified and clearly defined?
- [ ] All interview guides organized by competency?
- [ ] Performance task time requirement confirmed?
- [ ] Rubrics use consistent 4-level scale?
- [ ] Google Drive folder structure created?
- [ ] All documents saved to correct folders?

## Example Competencies Framework

For reference, here's what a competencies framework might look like (customize based on role):

**Example: Sales Leader Role**
1. **Federal Market Expertise** - Understanding of government buying processes, compliance, key stakeholders
2. **Strategic Pipeline Development** - Building long-term opportunities, forecasting accuracy, territory planning
3. **Team Leadership & Coaching** - Developing sales talent, driving culture, accountability
4. **Complex Deal Navigation** - Managing multi-stakeholder deals, negotiation, problem-solving
5. **Executive Presence & Communication** - Board-ready communication, stakeholder management, influence

---

## Notes for Claude Using This Skill

- Ask for missing inputs before proceeding — don't make assumptions
- When creating competencies, use language specific to the role and industry
- Performance tasks should be doable in the stated timeframe, not exhaustive
- Interview questions should feel natural to ask, not robotic
- Always provide the Google Drive folder links at the end
- Offer to refine any section after user reviews
