# Coverage Navigator

A bilingual (EN/ES) guide for families navigating Florida's disability benefits system —
three agencies (DCF, APD, SSA) that rarely coordinate, explained in plain language.

**Live:** https://bluefintuna27.github.io/coverage-navigator/

## What it does

- **Intake wizard** routes a family to the right starting point based on their situation
  (age-18 SSI redetermination is the biggest fork, and the hardest gate — SSA's own data
  shows 55.7% of childhood SSI recipients are initially found ineligible at that step)
- **Letter identifier** — figure out which agency sent a notice from its trigger phrases
- **Notice translator** — plain-language explanation of what a letter actually requires,
  powered by live Claude API calls, with a checklist for the SSA Adult Function Report
- Surfaces the frequently missed Disabled Adult Child (DAC) benefit pathway
- Spanish content written natively, not machine-translated

## How it's built

Single static HTML/CSS/JS pages — no server, no accounts, nothing entered is stored.

The translator calls Anthropic's Messages API (claude-sonnet-4-6) with a prompt
constrained to calm, jargon-free explanations under 180 words. The public demo ships
**without an API key on purpose** — client-side code can't keep secrets — so it degrades
gracefully to saved example explanations; live calls run where the request can be made
safely. Sample notices are composites, not real letters.

Built with Claude Code. Prototype for demonstration — not affiliated with DCF, APD,
or the Social Security Administration, and not a substitute for legal or caseworker advice.
