# Step 6: Chain-of-Thought on the Same Decision

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Prompt type: Chain-of-thought (step-by-step instructions)

The only change from Step 5 is that "final answer only" is replaced by step-by-step instructions.

```text
You are a financial analyst at KhataPe, a digital lender.

For each scenario below, decide which option KhataPe should choose to earn the higher profit.

Rules:
Net return = Interest rate + Processing fee − Expected default − Cost of funds
Profit = Net return × Loan budget
If both profits are equal, choose the option with the lower expected default.

Think step by step. For each scenario:
Step 1: Write the four numbers for Option A and calculate its net return.
Step 2: Calculate Option A's profit in ₹ crore.
Step 3: Repeat Steps 1 and 2 for Option B.
Step 4: Compare the two profits and apply the tie rule if needed.
Step 5: State the choice.

Show your working for every scenario, then give a final summary table: ID | A profit (₹ crore) | B profit (₹ crore) | Choice

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

## AI output: working

### S01 (Budget ₹40 crore)

**Step 1 – Option A net return:** interest 28% + fee 0.5% − default 12% − cost of funds 10% = 6.5%  
**Step 2 – Option A profit:** 6.5% × ₹40 crore = ₹2.6 crore  
**Step 3 – Option B net return:** interest 18% + fee 1.5% − default 2% − cost of funds 10% = 7.5%  
**Step 3 (profit) – Option B profit:** 7.5% × ₹40 crore = ₹3.0 crore  
**Step 4 – Compare:** A = ₹2.6 crore, B = ₹3.0 crore. B is higher.  
**Step 5 – Choice:** Option B.

### S02 (Budget ₹60 crore)

**Step 1 – Option A net return:** interest 20% + fee 2% − default 5% − cost of funds 10% = 7.0%  
**Step 2 – Option A profit:** 7.0% × ₹60 crore = ₹4.2 crore  
**Step 3 – Option B net return:** interest 16% + fee 1% − default 3% − cost of funds 9% = 5.0%  
**Step 3 (profit) – Option B profit:** 5.0% × ₹60 crore = ₹3.0 crore  
**Step 4 – Compare:** A = ₹4.2 crore, B = ₹3.0 crore. A is higher.  
**Step 5 – Choice:** Option A.

### S03 (Budget ₹25 crore)

**Step 1 – Option A net return:** interest 25% + fee 1% − default 11% − cost of funds 11% = 4.0%  
**Step 2 – Option A profit:** 4.0% × ₹25 crore = ₹1.0 crore  
**Step 3 – Option B net return:** interest 17% + fee 2% − default 4% − cost of funds 9% = 6.0%  
**Step 3 (profit) – Option B profit:** 6.0% × ₹25 crore = ₹1.5 crore  
**Step 4 – Compare:** A = ₹1.0 crore, B = ₹1.5 crore. B is higher.  
**Step 5 – Choice:** Option B.

### S04 (Budget ₹80 crore)

**Step 1 – Option A net return:** interest 21% + fee 2% − default 8% − cost of funds 10% = 5.0%  
**Step 2 – Option A profit:** 5.0% × ₹80 crore = ₹4.0 crore  
**Step 3 – Option B net return:** interest 17% + fee 1% − default 4% − cost of funds 9% = 5.0%  
**Step 3 (profit) – Option B profit:** 5.0% × ₹80 crore = ₹4.0 crore  
**Step 4 – Compare:** both profits are ₹4.0 crore, so the tie rule applies. Default A = 8%, default B = 4%; the lower default is B.  
**Step 5 – Choice:** Option B.

### S05 (Budget ₹15 crore)

**Step 1 – Option A net return:** interest 15% + fee 0% − default 3% − cost of funds 9% = 3.0%  
**Step 2 – Option A profit:** 3.0% × ₹15 crore = ₹0.45 crore  
**Step 3 – Option B net return:** interest 19% + fee 2.5% − default 6% − cost of funds 10% = 5.5%  
**Step 3 (profit) – Option B profit:** 5.5% × ₹15 crore = ₹0.825 crore  
**Step 4 – Compare:** A = ₹0.45 crore, B = ₹0.825 crore. B is higher.  
**Step 5 – Choice:** Option B.

### S06 (Budget ₹90 crore)

**Step 1 – Option A net return:** interest 15% + fee 2% − default 3% − cost of funds 8% = 6.0%  
**Step 2 – Option A profit:** 6.0% × ₹90 crore = ₹5.4 crore  
**Step 3 – Option B net return:** interest 29% + fee 0.5% − default 12% − cost of funds 12% = 5.5%  
**Step 3 (profit) – Option B profit:** 5.5% × ₹90 crore = ₹4.95 crore  
**Step 4 – Compare:** A = ₹5.4 crore, B = ₹4.95 crore. A is higher.  
**Step 5 – Choice:** Option A.

### S07 (Budget ₹55 crore)

**Step 1 – Option A net return:** interest 19.5% + fee 1.5% − default 6.5% − cost of funds 10.5% = 4.0%  
**Step 2 – Option A profit:** 4.0% × ₹55 crore = ₹2.2 crore  
**Step 3 – Option B net return:** interest 22% + fee 2% − default 8.5% − cost of funds 11% = 4.5%  
**Step 3 (profit) – Option B profit:** 4.5% × ₹55 crore = ₹2.475 crore  
**Step 4 – Compare:** A = ₹2.2 crore, B = ₹2.475 crore. B is higher.  
**Step 5 – Choice:** Option B.

### S08 (Budget ₹100 crore)

**Step 1 – Option A net return:** interest 24% + fee 1% − default 6% − cost of funds 10% = 9.0%  
**Step 2 – Option A profit:** 9.0% × ₹100 crore = ₹9.0 crore  
**Step 3 – Option B net return:** interest 20% + fee 2% − default 4% − cost of funds 9.5% = 8.5%  
**Step 3 (profit) – Option B profit:** 8.5% × ₹100 crore = ₹8.5 crore  
**Step 4 – Compare:** A = ₹9.0 crore, B = ₹8.5 crore. A is higher.  
**Step 5 – Choice:** Option A.

## AI output: final summary table

| ID | A profit (₹ crore) | B profit (₹ crore) | Choice |
|---|---|---|---|
| S01 | 2.6 | 3.0 | B |
| S02 | 4.2 | 3.0 | A |
| S03 | 1.0 | 1.5 | B |
| S04 | 4.0 | 4.0 | B |
| S05 | 0.45 | 0.825 | B |
| S06 | 5.4 | 4.95 | A |
| S07 | 2.2 | 2.475 | B |
| S08 | 9.0 | 8.5 | A |

## Marking against my answer key (✔ correct / ✘ wrong)

| ID | Type | Choice | A profit | B profit | Mark |
|---|---|---|---|---|---|
| S01 | Trap | B | 2.6 | 3.0 | ✔ |
| S02 | Regular | A | 4.2 | 3.0 | ✔ |
| S03 | Trap | B | 1.0 | 1.5 | ✔ |
| S04 | Tie | B | 4.0 | 4.0 | ✔ |
| S05 | Regular | B | 0.45 | 0.825 | ✔ |
| S06 | Trap | A | 5.4 | 4.95 | ✔ |
| S07 | Regular | B | 2.2 | 2.475 | ✔ |
| S08 | Regular | A | 9.0 | 8.5 | ✔ |

**Score: choice 8/8, profit 8/8, trap scenarios 3/3.**

## What I noticed

Every step of the working matches my spreadsheet, and the final choices match Step 5. Accuracy did not change because the direct answer was already correct. What changed is that every number is now visible and can be checked. The tie in S04 was handled correctly: equal profits of ₹4.0 crore, then Option B chosen for its lower default.
