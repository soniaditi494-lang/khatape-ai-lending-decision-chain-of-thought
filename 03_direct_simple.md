# Step 4: Direct Answer on a Simple Question

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Prompt type: Direct (answer only), one-step task

```text
Here are 8 lending scenarios for KhataPe, a digital lender.

For each scenario, which option has the higher interest rate? Answer only A or B.

Output a table: ID | Higher interest rate

Scenarios:

S01: Budget ₹40 crore | Option A: interest 28%, fee 0.5%, default 12%, cost of funds 10% | Option B: interest 18%, fee 1.5%, default 2%, cost of funds 10%
S02: Budget ₹60 crore | Option A: interest 20%, fee 2%, default 5%, cost of funds 10% | Option B: interest 16%, fee 1%, default 3%, cost of funds 9%
S03: Budget ₹25 crore | Option A: interest 25%, fee 1%, default 11%, cost of funds 11% | Option B: interest 17%, fee 2%, default 4%, cost of funds 9%
S04: Budget ₹80 crore | Option A: interest 21%, fee 2%, default 8%, cost of funds 10% | Option B: interest 17%, fee 1%, default 4%, cost of funds 9%
S05: Budget ₹15 crore | Option A: interest 15%, fee 0%, default 3%, cost of funds 9% | Option B: interest 19%, fee 2.5%, default 6%, cost of funds 10%
S06: Budget ₹90 crore | Option A: interest 15%, fee 2%, default 3%, cost of funds 8% | Option B: interest 29%, fee 0.5%, default 12%, cost of funds 12%
S07: Budget ₹55 crore | Option A: interest 19.5%, fee 1.5%, default 6.5%, cost of funds 10.5% | Option B: interest 22%, fee 2%, default 8.5%, cost of funds 11%
S08: Budget ₹100 crore | Option A: interest 24%, fee 1%, default 6%, cost of funds 10% | Option B: interest 20%, fee 2%, default 4%, cost of funds 9.5%
```

## AI output

| ID | Higher interest rate |
|---|---|
| S01 | A |
| S02 | A |
| S03 | A |
| S04 | A |
| S05 | B |
| S06 | B |
| S07 | B |
| S08 | A |

## Marking (✔ correct / ✘ wrong)

| ID | AI answer | Correct | Mark |
|---|---|---|---|
| S01 | A | A | ✔ |
| S02 | A | A | ✔ |
| S03 | A | A | ✔ |
| S04 | A | A | ✔ |
| S05 | B | B | ✔ |
| S06 | B | B | ✔ |
| S07 | B | B | ✔ |
| S08 | A | A | ✔ |

**Score: 8/8**

## What I noticed

All 8 answers are correct. Comparing two numbers is a one-step task with no formula or rule to apply, so a direct question is enough.
