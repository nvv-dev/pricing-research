---
name: pricing-research
description: Use when the human asks what to charge for a product or service, whether to raise or lower a price, or how a price compares with the market. For each product or service, collects a cost floor, a competitor range with source and date, and a value ceiling, then recommends one price with its assumption and a way to test it. Never publishes or changes prices.
disable-model-invocation: true
---

# Pricing research

A price has a floor (what it costs you), a market range (what alternatives charge) and a ceiling (what it is worth to the buyer). The recommendation lives between the floor and the ceiling, informed by the range. Collect the three references with evidence, then recommend one price and a way to prove it wrong.

## Before starting

Read `.agents/product-context.md` if it exists. Ask only for what is missing: the products or services in scope, the current prices, the goal (growth, revenue or margin), the customer type, and who approves price changes. Without a goal, ask for one.

## Step 1: cost floor

- List the costs the human provides: time, tools, licences, fees, support, taxes already known. Mark each as provided, estimated or unknown.
- Compute the minimum price that covers them at the expected volume. Show the formula.
- Do not invent costs, hours or rates. Missing input stays "unknown" and is listed as a question for the owner.

## Step 2: competitor range

- Pick three to six real alternatives, including doing nothing or doing it in-house.
- For each price record: the amount, what it includes, the source URL and the date seen. A price without source and date is not used.
- Read only public pages the site allows. Respect terms of use and robots rules; do not scrape, log in or bypass paywalls. If a price is not public, record "quote only" and do not guess.
- Report the low, median and high, and treat them as data points, not as the answer.

## Step 3: value ceiling

- Describe the outcome the buyer gets and what it is worth to them: time saved, revenue gained, risk avoided, or the cost of their next-best alternative.
- Use numbers from the owner or customers, with the source. Where none exist, state the reasoning and mark it "unvalidated".
- The ceiling is an argument, not a fact. Say how it could be checked (customer interviews, price-sensitivity questions).

## Step 4: recommendation

- One price per product or service (or one structure: tiers, a usage metric), placed between floor and ceiling and justified in two lines.
- State the assumption it depends on, for example "buyers compare us with agencies, not with templates".
- State how to test it: who sees it (new customers or leads only), for how long or how many conversations, the metric, the baseline, and what result means keep, adjust or revert.
- Avoid a price so low it signals low quality and is hard to raise later.

## Output

Use this table, one row per product or service:

```
| Product | Cost floor | Competitor range (low / median / high) | Sources and dates | Value ceiling | Recommended price | Assumption | Test and decision rule |
```

Then list: unknowns for the owner, items to validate with an accountant, and next three actions.

## Rules

- This skill researches and recommends. It never publishes prices, edits a live page, changes a billing system or contacts a competitor or customer.
- It gives no tax or accounting advice. For taxes, invoicing and withholding, write "validate with an accountant".
- Never invent competitor prices, costs, conversion rates or benchmarks.
- Raising prices for existing customers needs the owner's explicit decision and advance notice; propose, do not execute.

## Known failures

_Record real mistakes here with a date and the rule that prevents them._
