# Step 7: Check the Working, Change One Number, Scorecard

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Part A: Checking the working

Both Step 5 answers and Step 6 working were fully correct, so I chose two trap scenarios (S01 and S03) and checked every step of the Step 6 working against my spreadsheet.

| Scenario | Step | AI result | Your result | Correct? |
|---|---|---|---|---|
| S01 | Step 1 (A net return) | 6.5% | 6.5% | ✔ |
| S01 | Step 2 (A profit) | ₹2.6 crore | ₹2.6 crore | ✔ |
| S01 | Step 3 (B net return) | 7.5% | 7.5% | ✔ |
| S01 | Step 3 (B profit) | ₹3.0 crore | ₹3.0 crore | ✔ |
| S01 | Step 4 (compare) | B higher | B higher | ✔ |
| S01 | Step 5 (choice) | B | B | ✔ |
| S03 | Step 1 (A net return) | 4.0% | 4.0% | ✔ |
| S03 | Step 2 (A profit) | ₹1.0 crore | ₹1.0 crore | ✔ |
| S03 | Step 3 (B net return) | 6.0% | 6.0% | ✔ |
| S03 | Step 3 (B profit) | ₹1.5 crore | ₹1.5 crore | ✔ |
| S03 | Step 4 (compare) | B higher | B higher | ✔ |
| S03 | Step 5 (choice) | B | B | ✔ |

**Result:** all 12 checked steps are correct. No error was found in these two scenarios.

## Part B: Change one number

Prompt sent in the same chat as Step 6:

```text
Change only one number: in S01, Option B's expected default is now 6% (old value 2% + 4).
Recalculate S01 step by step and tell me whether the choice changes.
```

### AI output

**S01 recalculated (Option B default changed from 2% to 6%)**

**Step 1 – Option A net return:** 28% + 0.5% − 12% − 10% = 6.5% (unchanged)  
**Step 2 – Option A profit:** 6.5% × ₹40 crore = ₹2.6 crore (unchanged)  
**Step 3 – Option B net return:** 18% + 1.5% − 6% − 10% = 3.5%  
**Step 3 – Option B profit:** 3.5% × ₹40 crore = ₹1.4 crore  
**Step 4 – Compare:** A = ₹2.6 crore, B = ₹1.4 crore. A is now higher.  
**Step 5 – Choice:** Option A.

**Does the choice change?** Yes. Before the change the choice was Option B (₹3.0 crore vs ₹2.6 crore); after the change it is Option A (₹2.6 crore vs ₹1.4 crore).

### Check against my spreadsheet

| Item | AI | Spreadsheet | Correct? |
|---|---|---|---|
| B net return | 3.5% | 3.5% | ✔ |
| B profit | ₹1.4 crore | ₹1.4 crore | ✔ |
| A profit (should stay the same) | ₹2.6 crore | ₹2.6 crore | ✔ |
| New choice | A | A | ✔ |

**What I noticed:** the AI updated every step that depended on the changed number (B's net return, B's profit, the comparison and the choice) and kept Option A's steps unchanged. It did not just repeat the old answer.

## Part C: Scorecard

| What I checked | Direct (Step 5) | Step by step (Step 6) |
|---|---|---|
| Correct choice (out of 8) | 8 | 8 |
| Correct profit figure (out of 8) | 8 | 8 |
| Trap scenarios correct (out of 3) | 3 | 3 |
| Working I could check (yes / no) | No | Yes |

## Reflection

1. **Direct answer good enough?** Yes for Step 4: all 8 higher-interest answers were correct, because comparing two numbers is one step with no rules to apply.

2. **Which scenarios did step-by-step fix?** None. The direct answer in Step 5 was already 8/8, including the traps S01, S03 and S06 and the tie S04. I am recording this honestly.

3. **More accurate or just more convincing?** In this run it was not more accurate, since both were fully correct; it was more checkable. For example, in S01 I could verify Option A's net return of 6.5% and profit of ₹2.6 crore line by line instead of trusting one number.

4. **What the numbers do not show:** RBI digital lending rules (disclosure of fees, rules on lending service providers and recovery practices) and collection costs, plus the reliability of the expected default estimates, which are only forecasts.
