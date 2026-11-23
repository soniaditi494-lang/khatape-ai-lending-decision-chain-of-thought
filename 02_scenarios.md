# Steps 2 & 3: Synthetic Scenarios and Answer Key

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Step 2: Scenarios created with AI

**Why synthetic data?** Real lending data is confidential, so the AI was asked to create realistic but fictional scenarios.

### Data prompt used

```text
You are helping me build a realistic test dataset for a business case study.

KhataPe is a fictional digital lender in Indore. Every month it chooses between two loan products, Option A and Option B.

Create 8 monthly decision scenarios (S01 to S08).

For each scenario give:
- Loan budget in ₹ crore (between 10 and 100)
- For Option A and for Option B: interest rate %, processing fee %, expected default %, cost of funds %

Rules:
- Use whole numbers or one decimal place only.
- Interest rate between 12% and 30%; processing fee between 0% and 3%; expected default between 1% and 12%; cost of funds between 8% and 12%.
- In 3 scenarios, the option with the HIGHER interest rate must make LESS profit because its expected default is much higher.
- In 1 scenario, both options must make exactly the same profit.
- Do NOT calculate profit and do NOT say which option is better.

Output a table with these columns: ID | Budget (₹ crore) | A interest | A fee | A default | A cost of funds | B interest | B fee | B default | B cost of funds
```

### AI output (8 scenarios, all values in %)

| ID | Budget (₹ crore) | A interest | A fee | A default | A cost of funds | B interest | B fee | B default | B cost of funds |
|---|---|---|---|---|---|---|---|---|---|
| S01 | 40 | 28 | 0.5 | 12 | 10 | 18 | 1.5 | 2 | 10 |
| S02 | 60 | 20 | 2 | 5 | 10 | 16 | 1 | 3 | 9 |
| S03 | 25 | 25 | 1 | 11 | 11 | 17 | 2 | 4 | 9 |
| S04 | 80 | 21 | 2 | 8 | 10 | 17 | 1 | 4 | 9 |
| S05 | 15 | 15 | 0 | 3 | 9 | 19 | 2.5 | 6 | 10 |
| S06 | 90 | 15 | 2 | 3 | 8 | 29 | 0.5 | 12 | 12 |
| S07 | 55 | 19.5 | 1.5 | 6.5 | 10.5 | 22 | 2 | 8.5 | 11 |
| S08 | 100 | 24 | 1 | 6 | 10 | 20 | 2 | 4 | 9.5 |

---

## Step 3: Answer key (calculated by me before testing)

Calculated in a spreadsheet using the rules in `01_case_study.md`:

- Net return % = Interest + Fee − Default − Cost of funds
- Profit (₹ crore) = Net return ÷ 100 × Budget
- Correct choice = higher profit; if equal, the option with the lower expected default

| ID | A net return % | A profit (₹ cr) | B net return % | B profit (₹ cr) | Correct choice |
|---|---|---|---|---|---|
| S01 | 6.5 | 2.6 | 7.5 | 3.0 | B |
| S02 | 7.0 | 4.2 | 5.0 | 3.0 | A |
| S03 | 4.0 | 1.0 | 6.0 | 1.5 | B |
| S04 | 5.0 | 4.0 | 5.0 | 4.0 | B |
| S05 | 3.0 | 0.45 | 5.5 | 0.825 | B |
| S06 | 6.0 | 5.4 | 5.5 | 4.95 | A |
| S07 | 4.0 | 2.2 | 4.5 | 2.475 | B |
| S08 | 9.0 | 9.0 | 8.5 | 8.5 | A |

**This key was fixed before running any test prompt and was not changed afterwards.**

### Check of the AI's dataset

I checked whether the AI followed the "3 traps and 1 tie" instruction.

| ID | Higher interest option | Type |
|---|---|---|
| S01 | Higher interest: A | Trap (higher interest rate, lower profit) |
| S02 | Higher interest: A | Regular |
| S03 | Higher interest: A | Trap (higher interest rate, lower profit) |
| S04 | Higher interest: A | Tie (equal profit; lower default wins) |
| S05 | Higher interest: B | Regular |
| S06 | Higher interest: B | Trap (higher interest rate, lower profit) |
| S07 | Higher interest: B | Regular |
| S08 | Higher interest: A | Regular |

**Finding:** the dataset contains exactly 3 trap scenarios (S01, S03, S06) and 1 tie (S04). All values are inside the allowed ranges (budget 10–100, interest 12–30, fee 0–3, default 1–12, cost of funds 8–12). In S04 both options earn ₹4.0 crore, so the tie rule applies and Option B wins because its expected default (4%) is lower than Option A's (8%).
