# Step 5: Direct Answer on the Real Decision

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Prompt type: Direct (final answer only, no working)

```text
You are a financial analyst at KhataPe, a digital lender.

For each scenario below, decide which option KhataPe should choose to earn the higher profit.

Rules:
Net return = Interest rate + Processing fee − Expected default − Cost of funds
Profit = Net return × Loan budget
If both profits are equal, choose the option with the lower expected default.

Give the final answer only. Do not show any working.

Output a table: ID | Choice (A or B) | Profit of chosen option (₹ crore)

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

| ID | Choice | Profit of chosen option (₹ crore) |
|---|---|---|
| S01 | B | 2.6 |
| S02 | A | 4.2 |
| S03 | B | 1.0 |
| S04 | B | 4.0 |
| S05 | B | 0.45 |
| S06 | A | 5.4 |
| S07 | B | 2.2 |
| S08 | A | 9.0 |

## Marking against my answer key (✔ correct / ✘ wrong)

| ID | Type | AI choice | Correct choice | Choice | AI profit | Correct profit | Profit |
|---|---|---|---|---|---|---|---|
| S01 | Trap | B | B | ✔ | 2.6 | 2.6 | ✔ |
| S02 | Regular | A | A | ✔ | 4.2 | 4.2 | ✔ |
| S03 | Trap | B | B | ✔ | 1.0 | 1.0 | ✔ |
| S04 | Tie | B | B | ✔ | 4.0 | 4.0 | ✔ |
| S05 | Regular | B | B | ✔ | 0.45 | 0.45 | ✔ |
| S06 | Trap | A | A | ✔ | 5.4 | 5.4 | ✔ |
| S07 | Regular | B | B | ✔ | 2.2 | 2.2 | ✔ |
| S08 | Regular | A | A | ✔ | 9.0 | 9.0 | ✔ |

**Score: choice 8/8, profit 8/8, trap scenarios 3/3.**

## What I noticed

The AI got every choice and profit figure right, including the three trap scenarios (S01, S03, S06) and the tie (S04). The assignment allows for this result, so I am recording it honestly. The problem is that the answer gave only final numbers: I cannot see how they were obtained, so I could only trust them by checking each one against my spreadsheet.
