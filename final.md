# Management & Leadership in CS — Final Report
## Initiative: HAAG Faculty Relations — Standardized Faculty Engagement Framework

**Author:** Kevin Lemus-Medrano
**Program:** Human Augmented Analytics Group (HAAG) — Georgia Institute of Technology

---

## Table of Contents

1. [Initiative Scope](#1-initiative-scope)
2. [Evidence of Alignment with HAAG Goals](#2-evidence-of-alignment-with-haag-goals)
3. [Procedures Generated](#3-procedures-generated)
4. [Procedure 1: Faculty Check-In Template](#4-procedure-1-faculty-check-in-template)
5. [Procedure 2: AI-Assisted Faculty Communication](#5-procedure-2-ai-assisted-faculty-communication)
6. [Procedure 3: Faculty Feedback Survey](#6-procedure-3-faculty-feedback-survey)

---

## 1. Initiative Scope

This initiative creates a Standardized Faculty Engagement and Retention Framework for HAAG, with AI integrated directly into the communication workflow. No formal process existed for faculty sponsor communication — no structured check-ins, no communication schedule, and no feedback collection mechanism. The framework consists of three procedures: a Faculty Check-In Template, an AI-Assisted Communication Procedure, and a Faculty Feedback Survey. The AI layer replaces manual tier assignment with a lightweight prompt-based system: PMs describe the faculty relationship in plain language, and the AI recommends the right communication cadence and drafts the outreach message in one step. The scope covers all active HAAG projects with a faculty sponsor and is built to be maintained by PMs and enforced by HAAG admin in future semesters.

---

## 2. Evidence of Alignment with HAAG Goals

Evidence was gathered through direct observation throughout Spring 2026. Slack communication patterns showed irregular faculty outreach across project teams — some faculty went weeks without contact, with no consistent structure. Review of the master Excel tracker confirmed no standardized logging process existed at the org level. Direct conversations with faculty sponsors was atemmpted and reaching out to my teammate conversations with revealed widely varying preferences (async Slack vs. structured meetings), confirming that a rigid one-size-fits-all schedule was less appropriate than a flexible, signal-driven approach. These observations informed all three procedures and validated that the initiative addresses a real operational gap within HAAG. The AI integration in Procedure 2 specifically addresses the finding that manual tier assignment added friction without adding value — PMs consistently found the classification decision ambiguous and time-consuming.

---

## 3. Procedures Generated

Three procedures are included below. Each targets HAAG PMs and Team Leads as the primary audience, integrates into existing HAAG infrastructure (Slack, Operations Tracker), and includes a built-in enforcement mechanism so the framework persists beyond this semester. Procedure 2 has been redesigned from the original three-tier manual system into an AI-assisted workflow that removes the classification burden from PMs entirely.

---

## 4. Procedure 1: Faculty Check-In Template

**Audience:** HAAG Project Managers and Team Leads
**Frequency:** Once per month per faculty sponsor, or after any major milestone

### Purpose
Provide a consistent, reproducible structure for faculty check-in meetings so that feedback, preferences, and action items are documented after every interaction.

### Pre-Meeting Checklist
- [ ] Review previous check-in notes from the shared repository
- [ ] Pull current project status from relevant weekly reports
- [ ] Confirm meeting time at least 48 hours in advance
- [ ] Prepare 2–3 updates or questions to raise

### Check-In Form

**Date:** _______________ **Faculty Sponsor:** _______________ **PM / Team Lead:** _______________
**Format:** ☐ In-person  ☐ Video call  ☐ Async (Slack/email)  **Project(s):** _______________

**Section 1 — Project Status**

| Item | Status |
|------|--------|
| Current milestone or deliverable | |
| On track? (Yes / At Risk / Behind) | |
| Key blockers | |

**Section 2 — Faculty Feedback**

1. What is the faculty sponsor most pleased with so far?
   Response: _______________________________________________

2. Any concerns about direction, pace, or communication?
   Response: _______________________________________________

3. Are expectations clearly understood by the team?
   ☐ Yes  ☐ Partially  ☐ No — Notes: _______________________________________________

4. Preferred communication going forward?
   ☐ Sync meetings  ☐ Async updates  ☐ Mix  Frequency: _______________

5. Any changes to scope or timelines?
   Response: _______________________________________________

**Section 3 — Action Items**

| Action Item | Owner | Due Date |
|-------------|-------|----------|
| | | |
| | | |

### Post-Meeting Actions
1. Save completed form to `/faculty-relations/check-ins/[FacultyLastName]_[YYYY-MM-DD]`
2. Run the AI Check-In Summary tool (Procedure 2, Step 1) to generate the Slack post and Ops Tracker log entry
3. Post the AI-generated Slack summary in `#faculty-relations` within 24 hours
4. Log the AI-generated entry in the master Operations Tracker
5. Escalate any urgent concerns to HAAG admin immediately

### Integration and Enforcement
HAAG admin audits the shared repository monthly to confirm check-ins are completed. Missing submissions are flagged to the relevant PM. Non-completion across two consecutive months is escalated to the HAAG manager group.

---

## 5. Procedure 2: AI-Assisted Faculty Communication

**Audience:** HAAG Project Managers, Team Leads, and Admin
**Scope:** All active HAAG projects with a faculty sponsor

### Purpose
Replace manual communication tier assignment with an AI-assisted workflow. Rather than classifying each faculty relationship into a rigid tier, PMs describe the current relationship in plain language and receive a recommended cadence and a ready-to-send outreach message in one step. This removes ambiguity from the classification decision and reduces the time cost of routine outreach to under two minutes per faculty sponsor.

### Why AI Instead of Tiers

The original framework used a three-tier system (Engaged / Standard / Light Touch) that required PMs to classify each faculty relationship and manually log the assignment. In practice, this created two problems. First, the classification was ambiguous — most relationships fell between tiers, and PMs defaulted to the middle option regardless of actual engagement signals. Second, the tier label did not automatically produce the outreach message, so PMs still had to draft communications from scratch. The AI-assisted approach collapses both steps into one: the PM provides context, the AI outputs a recommendation and a draft message ready to send.

### Semester Calendar (Minimum Requirements)

The following schedule applies to all faculty sponsors regardless of the AI-recommended cadence. These are floor requirements, not the full communication plan.

| Week | Action | Owner |
|------|--------|-------|
| Week 1 | Send welcome message using AI-assisted draft (Step 2 below) | PM |
| Week 2–3 | First formal check-in using Procedure 1 | PM |
| Week 6 | AI-assisted async update or sync check-in | PM |
| Week 8 | Mid-semester survey distributed (Procedure 3) | Admin |
| Week 10 | Follow-up check-in addressing survey feedback | PM |
| Week 14 | End-of-semester check-in | PM |
| Week 15 | Admin reviews Operations Tracker; logs outcomes | Admin |

### Step 1 — AI Check-In Summary (after every Procedure 1 check-in)

After completing a check-in, the PM uses the HAAG Check-In Summary Tool — a web-based form powered by the Claude API — to generate two outputs automatically:

**Input:** Faculty name, project name, PM name, meeting date, current milestone, status (On Track / At Risk / Behind), raw meeting notes (unformatted), and action items (format: item | owner | due date).

**Output 1 — Slack post** ready to paste into `#admin-faculty`:
> *HAAG Check-In — [Project] — [Month Year]*
> - [Key update 1]
> - [Key update 2]
> - [Action item or next step]
> — [PM Name], HAAG

**Output 2 — Operations Tracker log entry** in 3–4 sentences summarizing the interaction, faculty sentiment, and next steps.

**Output 3 — Structured action items table** parsed from the PM's raw input.

The tool is accessible at [haag_checkin_tool.html](haag_checkin_tool.html) (see **Figure 1** below). No formatting is required from the PM — raw notes are sufficient input.

---

**Figure 1 — HAAG Check-In Summary Tool**

<img width="723" height="822" alt="image" src="https://github.com/user-attachments/assets/a1e735a1-985f-4188-bcc7-8f55665cb0f8" />


<img width="689" height="678" alt="image" src="https://github.com/user-attachments/assets/84edf6a5-b975-451f-8645-72c3f675d5f9" />




*The Check-In Summary Tool input form (top) and its three AI-generated outputs: a ready-to-paste Slack post for `#faculty-relations`, a 3–4 sentence Ops Tracker log entry, and a parsed action items table. The PM fills in raw meeting notes — no formatting required.*

---

### Step 2 — AI Outreach Drafter (for async updates and welcome messages)

When a PM needs to send a routine async update or a semester welcome message, they use the AI Outreach Drafter rather than writing from scratch.

**Input prompt template** (send directly to Claude or use the HAAG tool):

> You are a HAAG PM assistant. Draft a [welcome message / monthly async update / milestone update] for faculty sponsor [Name] on project [Project Name]. Current status: [On Track / At Risk / Behind]. Key update: [1–2 sentences]. Items needing faculty input: [list or "none"]. Faculty preference: [Slack / email / meetings]. Keep it under 100 words, professional but warm, and sign off as [PM Name], HAAG.

**Review before sending.** The PM reads the draft, makes any necessary adjustments, and sends via the faculty's preferred channel. Log the send date in the Operations Tracker. The Outreach Drafter is accessible at [haag_outreach_tool.html](haag_outreach_tool.html) (see **Figure 2** below).

---

**Figure 2 — AI Outreach Drafter**

<img width="679" height="810" alt="image" src="https://github.com/user-attachments/assets/ae792653-d6c3-490e-8ea2-ff6e73e1a3cb" />

<img width="692" height="617" alt="image" src="https://github.com/user-attachments/assets/3e132130-6d8b-48ee-ad6f-bf832248a90c" />

*The Outreach Drafter showing a monthly async update in progress. The PM selects the message type, fills in status and key updates, and receives an AI-drafted message under 100 words. The prompt sent to the Claude API is shown at the bottom for transparency. The PM reviews before marking as sent.*

---

### Step 3 — AI Cadence Recommendation (start of semester and after survey)

At the start of each semester and after the Week 8 survey results are reviewed, PMs use the following prompt to get a recommended communication approach for each faculty sponsor:

> Based on the following signals, recommend a communication cadence and channel for this faculty sponsor. Signals: stated preference = [preference], response time to last message = [fast / slow / no response], satisfaction score from last survey = [score or "not yet surveyed"], last check-in outcome = [brief description]. Recommend: how often to reach out, what channel to use, and whether to flag this relationship for admin review.

Log the AI recommendation in the Operations Tracker under the faculty sponsor's entry. Update at mid-semester if survey results indicate a change is needed.

### Minimum Requirements (All Faculty)
- [ ] Week 1 welcome message sent (AI-drafted, PM-reviewed)
- [ ] At least one formal check-in using Procedure 1, with AI summary posted to Slack
- [ ] Mid-semester survey link sent by admin (Week 8)
- [ ] AI cadence recommendation logged at semester start and updated post-survey
- [ ] Closing message at end of semester

### Integration and Enforcement
AI-generated summaries, log entries, and cadence recommendations are reviewed at each bi-weekly HAAG manager meeting. Admin flags any faculty sponsor with no logged contact in the prior 30 days and assigns a follow-up owner. The AI tools do not replace PM judgment — all AI outputs are reviewed before use.

---

## 6. Procedure 3: Faculty Feedback Survey

**Audience:** HAAG Admin (administers); HAAG PMs and Team Leads (act on results)
**Frequency:** Once per semester, Week 8

### Purpose
Collect structured faculty satisfaction data mid-semester to surface at-risk relationships while there is still time to act — not at the end of the semester when it is too late.

### Step 1 — Prepare (Admin, Week 7)
Create the survey in Google Forms using the required questions below. Add the current semester to the title. Test the form before sending.

**Required Survey Questions**

| # | Question | Format |
|---|----------|--------|
| 1 | Which HAAG project(s) are you sponsoring? | Short answer |
| 2 | How satisfied are you with communication from the HAAG team? | 1 (Low) – 5 (High) |
| 3 | Do you feel your expectations have been clearly communicated? | ☐ Yes  ☐ Somewhat  ☐ No |
| 4 | How often would you like to receive updates? | ☐ Weekly  ☐ Bi-weekly  ☐ Monthly  ☐ Milestone-based |
| 5 | Preferred communication channel? | ☐ Slack  ☐ Email  ☐ Meetings  ☐ No preference |
| 6 | Is there anything the HAAG team could do differently? | Open-ended (optional) |
| 7 | How likely are you to sponsor a HAAG project next semester? | 1 (Low) – 5 (High) |

### Step 2 — Distribute (Admin, Week 8)
Send the survey to all active faculty sponsors via their preferred channel. Use this message:

> Hi [Faculty Name], we'd love a quick check-in on your HAAG experience this semester. This survey takes under 5 minutes: [LINK]. Thank you — [Admin Name], HAAG Admin

Log the send date in the Operations Tracker. Send one reminder after 5 business days to non-respondents. Close the survey after 7–10 days.

### Step 3 — Analyze (Admin, Week 9)
Export results and flag any faculty sponsor who meets one or more of the following criteria:

| Flag Condition | Threshold |
|---------------|-----------|
| Satisfaction score (Q2) | ≤ 2 out of 5 |
| Retention likelihood (Q7) | ≤ 2 out of 5 |
| Expectation clarity (Q3) | Response is "No" |

Notify the relevant PM privately for each flagged sponsor. Post aggregate results to `/faculty-relations/survey-results/`. Feed survey results into the Step 3 AI cadence recommendation prompt (Procedure 2) to update communication approaches for the remainder of the semester.

### Step 4 — Follow-Up (PM, Week 10)
For each flagged faculty sponsor, the PM reaches out within 5 business days using Procedure 1 as the follow-up structure and the AI Outreach Drafter (Procedure 2, Step 2) to draft the message. Document the interaction in the Operations Tracker. Escalate unresolved concerns to HAAG admin within 3 business days.

### Integration and Enforcement
The survey is a standing Week 8 calendar event set by admin at the start of each semester. Results feed directly into the AI cadence recommendation step (Procedure 2) and are presented at the end-of-semester manager debrief to improve the framework for the following semester.

AI Acknowledgment

Claude was used as a writing assistant during the preparation of this document.
It was used for drafting, editing, and structuring content based on the author's notes, ideas, and existing project documentation. 
All content was reviewed, revised, and approved by the author. It was also used to help generate the UI mockups included in Procedure 2
The initiative methodology, observations, and conclusions are the author's own.
