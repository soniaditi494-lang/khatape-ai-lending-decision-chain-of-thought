# Step 1: The KhataPe Case Study

**Project:** KhataPe Lending Decisions – Direct vs Chain-of-Thought  
**Course:** Prompt Engineering, AI & Machine Learning | BBA (FinTech), Chitkara Business School  
**Tool used:** Claude (Anthropic)  

## Background

**KhataPe** is a fictional digital lender in Indore that gives small loans to kirana shops and college students through its app. Every month it has a fixed budget to lend and must choose between two loan products, Option A and Option B.

## The question

The CFO asks me, as a Business Analyst:

> **"Can AI help us pick the more profitable option every month? Can we trust a quick answer, or must the AI show its working?"**

## KhataPe decision rules

| Item | Rule |
|---|---|
| **Net return** | Interest rate + Processing fee − Expected default − Cost of funds (all in % per year) |
| **Profit** | Net return × Loan budget |
| **Decision** | Choose the option with the higher profit. If both profits are equal, choose the option with the lower expected default. |
| **Ignore** | Operating costs, taxes and the timing of payments |

## Worked example

- Option A: 22% interest + 2% fee − 6% default − 10% cost of funds = **8%** net return. On a ₹50 crore budget, profit = **₹4 crore**.
- Option B: 18% + 1% − 3% − 10% = **6%** net return, profit = **₹3 crore**.
- KhataPe chooses **Option A**.

## My approach

1. Create 8 synthetic monthly lending scenarios with AI.
2. Calculate the correct answers myself in a spreadsheet before testing.
3. Test a direct prompt on a one-step question (higher interest rate).
4. Test a direct prompt on the real decision (final answer only).
5. Test a chain-of-thought prompt on the same decision.
6. Check the working step by step, change one number, and compare scores.
