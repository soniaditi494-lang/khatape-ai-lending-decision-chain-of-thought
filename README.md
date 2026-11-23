# KhataPe Lending Decisions: Direct Answers vs Chain-of-Thought Prompting

**A FinTech case study on when AI can give a quick answer and when it must show its working.**

Author: [Your Name] · BBA (FinTech), Chitkara Business School · Tool: Claude · November 2026

## The case

**KhataPe** (fictional) is a digital lender in Indore that lends to kirana shops and students. Every month it must choose between two loan products with different interest rates, fees and default risk. As a Business Analyst, I tested whether AI can pick the more profitable option, and whether asking it to reason step by step makes it more reliable.

## The data

8 synthetic monthly scenarios created with AI, including 3 "trap" scenarios where the higher interest rate makes less profit and 1 tie. I calculated the correct answers myself in a spreadsheet before testing.

## Decision rule

Net return = Interest rate + Processing fee − Expected default − Cost of funds

Profit = Net return × Loan budget

## Approach

| Step | Prompt type | Task |
|---|---|---|
| 1 | Direct | Which option has the higher interest rate? |
| 2 | Direct | Which option makes more profit? (final answer only) |
| 3 | Chain-of-thought | Same decision, solved step by step |
| 4 | Chain-of-thought | One number changed: does the AI update every step? |

## Results

| Metric | Direct | Step by step |
|---|---|---|
| Correct choice (/8) | 8 | 8 |
| Correct profit figure (/8) | 8 | 8 |
| Trap scenarios correct (/3) | 3 | 3 |
| Working I could check | No | Yes |

## Key learnings

1. **A direct answer is enough for one-step questions:** all 8 "higher interest rate" answers were correct (8/8).
2. **Step-by-step reasoning helps multi-step decisions:** in this run it fixed no scenarios, because the direct answer was already 8/8; its benefit was that every step could be checked.
3. **Convincing is not the same as correct:** none found. All 12 steps I checked in S01 and S03 matched my spreadsheet, so the working was both convincing and correct here.
4. **What the numbers do not show:** RBI digital lending rules and collection costs.

## My recommendation to KhataPe

Use AI with step-by-step working for the monthly decision, so the CFO's team can verify every number, and keep a spreadsheet check as the control. A human must still review regulatory compliance, collection costs and the reliability of the expected default estimates before approving any option.

## Repository files

| File | Content |
|---|---|
| `01_case_study.md` | KhataPe case and decision rules |
| `02_scenarios.md` | Synthetic scenarios and answer key |
| `03_direct_simple.md` | Direct prompt on a one-step question |
| `04_direct_decision.md` | Direct prompt on the real decision |
| `05_cot_decision.md` | Chain-of-thought prompt on the same decision |
| `06_scorecard.md` | Step check, changed-number test, scorecard and reflection |

## Skills shown

Prompt engineering · Chain-of-thought prompting · Synthetic data creation · Spreadsheet financial analysis · AI output verification · Lending business basics

## What I learned

- A direct prompt works well for simple, one-step questions.
- Chain-of-thought prompting makes AI show each step, so I can check its working instead of trusting one number.
- Step-by-step working can look convincing and still contain a wrong number, so every step must be checked.
- How to create synthetic business scenarios with AI, including deliberate "trap" cases.
- Why I calculate my own answer key in a spreadsheet before testing AI.
- Changing one number is a quick test of whether AI really reasons or just repeats.
- Numbers alone do not make a lending decision; risk and regulation matter too.

*KhataPe and all data in this project are fictional and created for learning.*
