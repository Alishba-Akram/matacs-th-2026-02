# Design Write-up

## 1. What should AI do, and what should fixed rules do?

AI should read each proposal and pull out useful facts, such as the contractor's licence, WSIB clearance, insurance, price, completion time, experience, warranties, and team plan. It should show evidence for each fact and mark information as unknown when it cannot find a clear answer.

Fixed rules should check the required conditions and calculate scores using the administrator's chosen criteria and weights. AI should not make up scores or choose the winning contractor. A human reviewer makes the final decision.

## 2. How will the system give repeatable and explainable results?

The system should use the same documented scoring formulas and the same version of the criteria for each review. It should save the facts found, their evidence, each score, the criteria version, and the prompt or model version used for extraction.

The rules engine should give the same result when it receives the same validated facts and the same settings. AI extraction can sometimes be wrong or unclear, so uncertain facts should be checked by a person.

## 3. How will human review and audit work?

A procurement reviewer should be able to open the evidence, correct a mistake, ask a contractor for clarification, and record why they changed a result. The system should flag missing or unclear important information instead of guessing.

The audit record should include dates, evidence references, score details, criteria versions, reviewer changes, and the final decision. The system gives advice and comparisons; an authorised person remains responsible for the procurement decision.

## 4. What happens if the criteria change after scoring?

Each set of criteria should have a version number and an effective date. Old results should keep the version that was used at the time. If an administrator changes a weight or rule, the system should create a new evaluation instead of silently changing the old one.

The reviewer should be able to compare the two evaluations and see why the scores or order changed.

## 5. What are the main risks, and how can they be reduced?

- **Instructions hidden in a proposal:** Treat proposal text as untrusted data. Do not let it change the system instructions or procurement criteria.
- **Wrong information extracted by AI:** Keep evidence, validate the output, and send unclear details to a human reviewer.
- **Unfair or inconsistent scores:** Use written scoring formulas, version the rules, and test them on sample proposals.
- **Missing information:** Mark it as unknown and request clarification instead of guessing.
- **Private or sensitive information:** Limit access, store files securely, and keep information only as long as needed.
- **Too much trust in automation:** Show how scores were calculated and require a human to approve the final decision.

The system should be tested before real use, and any change to criteria should be documented.


## Scoring rules used for the sample ranking

The administrator's weights are experience 30%, price 25%, timeline 15%, warranty 15%, and team/approach 15%. The weights add up to 100%.

For a repeatable sample, this design uses these example scales:

- **Experience:** 0 qualifying projects = 0; 1-2 = 25; 3-5 = 50; 6-9 = 75; 10 or more = 100.
- **Price:** lowest price among proposals that pass mandatory checks and have enough information to be ranked, divided by the proposal's price, multiplied by 100. The project budget is CAD 260,000.
- **Timeline:** 8 weeks or less = 100; 9-10 = 90; 11-12 = 80; 13-14 = 70; 15-16 = 60. A timeline over 16 weeks does not meet the stated project deadline. A missing timeline is unknown and is flagged instead of scored.
- **Warranty:** panel warranty score is 100 when it is at least 25 years. Workmanship warranty score is 50 for 1–5 years, 75 for 6–8 years, 90 for 9–10 years, and 100 for more than 10 years. The warranty raw score is the average of the two scores.
- **Team and approach:** 25 points each for a named project lead, described crew, safety plan, and monitoring plan. Missing evidence receives no points for that checklist item; if the evidence is unclear, a reviewer should clarify it.

For each criterion, weighted points equal the raw score multiplied by the criterion weight divided by 100. The total score is the sum of all five weighted contributions. The example ranking is based only on the stated proposal information and these sample scales. The procurement team should approve the scales before real use. Any changes should be versioned and recorded.

The bidder-held licence and the confirmed WSIB clearance plus CAD 5 million liability insurance are mandatory checks. Proposal B does not establish that the bidder itself holds the licence, so it is ineligible under the current stated rule. Proposal D has no confirmed completion timeline, so it is flagged and not given a final rank. A human reviewer should confirm the procurement policy and evidence before treating any sample result as a real procurement decision.
