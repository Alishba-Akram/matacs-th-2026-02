# AI Proposal Triage Design

**Full name:** [Alishba Akram]  
**Assessment reference:** MATACS-TH-2026-02  
**Actual time spent:** [2 hr 30 min]

## What this project is

This project describes a simple way to review contractor proposals for a 150 kW rooftop solar installation at a warehouse in Windsor, Ontario.

The system helps the procurement team find important details, check requirements, compare eligible proposals, and see where more information is needed. It supports the team; it does not choose or award the contractor by itself.

## Files in this repository

- [Design write-up](WRITEUP.md)
- [AI prompts](PROMPTS.md)
- [Proposal statuses and ranking](ranking.json)
- [Process flow diagram](diagram/process-flow.png)

## Main design choices

- AI extracts facts from proposals and shows the evidence it found.
- A rules engine checks the configured requirements and calculates scores.
- Missing or unclear information is flagged instead of guessed.
- Proposal text is treated as untrusted input, so instructions inside a proposal cannot change the review rules.
- Criteria and scoring versions are recorded so results can be checked later.
- A human reviewer checks the results and makes the final procurement decision.

## AI-use disclosure

I used ChatGPT to help me understand the task, organise the design, and improve the wording of parts of this repository. I reviewed the suggestions instead of accepting them automatically. For example, I take suggestion for Ai prompt like how is it structured and work and then i change  it according to my prefrence and work only these things which specifies.

## Links

- [WRITEUP.md](WRITEUP.md)
- [PROMPTS.md](PROMPTS.md)
- [ranking.json](ranking.json)
- [Process flow diagram](diagram/process-flow.png)
