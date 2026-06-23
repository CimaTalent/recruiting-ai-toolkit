---
name: se-candidate-narrative
description: Generate a compelling candidate narrative for Sales Engineer candidates by synthesizing resume, interview transcript, and JD requirements into a story-driven summary. Produces a 250-350 word narrative overviewing career trajectory, areas of strength, and open questions. Configurable for any SE role — adjust domain focus (e.g., cybersecurity, supply chain, AI security) and sales motion (federal, commercial, enterprise) per engagement.
---

# Sales Engineer Candidate Narrative

This skill generates a story-driven candidate summary from resume + interview transcript,
framed against specific Sales Engineer role requirements. It is meant to complement a
structured evaluation (Advance/Hold/No) with a narrative that tells the human story
of the candidate's fit.

---

## Configuration (Set Per Role)

```
ROLE_TITLE: [e.g., "Sales Engineer"]
COMPANY_NAME: [e.g., "Acme Corp"]
DOMAIN_FOCUS: [e.g., cybersecurity, supply chain security, AI risk, healthcare IT]
SALES_MOTION: [e.g., federal + commercial, enterprise SaaS, mid-market]
KEY_COMPETENCIES: [3-5 most important competencies for this SE role]
WORD_TARGET: 250-350 words
```

---

## Inputs Required

1. **Candidate resume or LinkedIn profile**
2. **Interview transcript** (recruiter screen or hiring manager round)
3. **Job description** or configured role context

---

## Narrative Structure

### Opening: Career Arc (2-3 sentences)
Describe where the candidate started, how they got to where they are, and what trajectory that implies. This should be specific and earn attention — not just "X years of experience in Y."

### Strengths: 2-3 Named Capabilities
Name 2-3 standout capabilities directly relevant to the role. Each should be:
- **Specific** — not "strong communicator" but what kind of communication, in what context
- **Evidence-based** — tied to a specific role, project, or transcript quote
- **Relevant** — mapped explicitly to a configured KEY_COMPETENCY

Format example:
> **Technical Discovery**: [Candidate] demonstrates a pattern of leading with deep technical discovery before positioning solutions. In the interview, they described [specific example], which maps directly to the POV-first motion this role requires.

### Open Questions: 2-3 Genuine Uncertainties
These are not weaknesses — they are honest gaps where the evidence doesn't fully resolve an important question. Frame them as questions, not verdicts.

Format example:
> **[Domain] Depth**: [Candidate]'s background is strong on [adjacent area] but hasn't explicitly worked in [specific domain]. Open question: how quickly can they ramp on [key area], and do they have the intellectual curiosity to go deep fast?

### Closing: One-Sentence Summary
A direct, non-hedged synthesis. What is the most important thing to know about this candidate for this decision?

---

## Tone Guidelines

- Write for a hiring manager who will read this in 90 seconds before a debrief
- Be specific — name projects, companies, quotes. Vague narratives are useless.
- Be honest about gaps — a narrative that hides weaknesses doesn't help anyone make a good decision
- Avoid hedging language ("seems like," "appears to," "might be") — make calls
- No bullet points in the narrative body — this is prose

---

## Output Format

```
# Candidate Narrative: [Candidate Name]
**Role:** [ROLE_TITLE] | **Company:** [COMPANY_NAME]

[Narrative — 250-350 words in prose, following the structure above]
```

---

## Notes

- This skill complements a structured evaluator skill (Advance/Hold/No). The evaluator handles the recommendation; this skill handles the story.
- If the transcript is missing, note this prominently. Narratives built on resume only have lower confidence on soft-skill dimensions.
- The narrative should be something a hiring manager could read aloud in a debrief and have it hold up to scrutiny.
