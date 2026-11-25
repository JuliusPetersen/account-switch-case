# Account switch case: Revolut Portugal

**Revolut already offers an account switch in Portugal. How could it move more salaries?**

Live: https://account-switch-case.bot-pulse.workers.dev

Revolut counts a customer as a main-bank customer when their salary arrives at Revolut. In Portugal, a legal switching service (Decree-Law 107/2017) can move a salary, bills and standing orders to a new bank within two to three weeks. Revolut offers it, but as a PDF form that has to be signed and uploaded, and its own help page lists the payments the service doesn't cover. This case proposes moving the switch into the app and guiding customers through the payments it leaves out.

Independent work based on public sources. Not affiliated with or reviewed by Revolut. Statements marked Hypothesis are my assumptions and would need checking against internal data.

## What is in the case

1. Revolut's goal in Portugal, from its 2024 annual report and interviews: the salary
2. How the switching service works today, step by step, and what it excludes
3. Four hypotheses on where customers drop out
4. What I would check before building anything
5. The proposal: request the switch in the app, a tracker built from the list the old bank already sends, and next steps for each payment the service skips
6. Sizing: reach, value per customer, cost
7. Metric and test: main-bank status within 60 days of the request, with a guardrail
8. Sources with dates

## How the case changed

My first version proposed a guided flow to send the IBAN to the employer. Checking Revolut's help pages showed that the regulated switching service already does this. The useful question was a different one: why the existing service doesn't move more salaries. Version 2 starts from the service's own exclusions and from local barriers such as mortgage discounts that Portuguese banks tie to salary domiciliation.

## Built with

A single static page (`public/index.html`), served with Cloudflare Workers static assets (`wrangler.jsonc`). No tracking, no external scripts, `noindex` so it doesn't show up as if it were a Revolut page.

```
npx wrangler deploy
```

## Author

Julius Petersen, MSc Impact Entrepreneurship & Innovation at Nova SBE, Lisbon. [LinkedIn](https://www.linkedin.com/in/julius-petersen-is)
