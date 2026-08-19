<!--
  WORKED EXAMPLE — this is the actual content of the live, shipped kitchen-erp.html,
  reformatted into the markdown convention described in content/README.md.
  Compare this file to case-studies/kitchen-erp.html to see the mapping.
-->
---
title: Faster ERP discovery, tested on a kitchen pantry
where: Atom + Bits · Personal R&D · Discovery Methodology
dek: Enterprise ERP discovery usually runs on months of stakeholder interviews before the real dependencies show up. I built a working household inventory system in two weeks to test whether building beats talking — and hit five of the same six decision categories a $100M rollout would face.
role: Product Manager & UX Architect
timeline: July 2026 · 2-week build, still running
team: Solo discovery & PRD; Gabe Crooker on implementation, deployment, and QA
focus: Discovery methodology & zero-to-one build
metrics:
  - 2 weeks — idea to live system
  - 5 of 6 — ERP domains surfaced
  - $500 — total project budget
---

# Key image
[MEDIA: landscape — live stock overview screenshot]
Caption: The live stock overview — 30 products, real-time value, and automatic expiration tracking, built and running inside two weeks.

# The problem
Enterprise ERP discovery usually leans on round after round of stakeholder interviews, workshops, and document
reviews before the real dependencies show up: data quality issues, how zones and locations should actually be
modeled, exception handling, permissions, mobility constraints. Too often those show up late, during testing or
after launch, once they're expensive to fix.

I wanted to test whether that timeline could compress — not by skipping rigor, but by replacing talking about a
system with actually building one. So I used a real, working household kitchen inventory tool, built on the
open-source platform Grocy, as a lightweight stand-in for enterprise ERP discovery. If I actually built something
instead of just discussing it, would I run into the same kinds of decisions that show up in large-scale ERP
projects — item setup, inventory zones, barcode scanning, inventory rules, unit-of-measure configuration, mobility
UX — and would I get there faster?

> CALLOUT (teal): A note on framing
> The household problem — not knowing what's in the pantry, wasting food, buying doubles — is really just the
> vehicle here. What I actually wanted to test was the discovery method itself. In a lot of ways, this project is
> a pilot for how Atom + Bits approaches discovery with clients, dressed up as a kitchen app.

# What I did
I ran a structured, five-round PM/UX discovery process, deliberately modeled on the same lens I use in Atom + Bits
engagements: workflow, coordination, knowledge, decision-making, and readiness. Each round captured raw
requirements and decisions before anything got synthesized into a formal PRD — the same way an enterprise
discovery workstream logs interview notes before requirements get written up.

## Artifact 1: Foundations & core workflows
Defined users, the primary problem (inventory visibility), config-only prototype scope, target platform,
stock-in methods, and expiration tracking as a v1 must-have.

## Artifact 2: Rules & access
Set auto-add-at-threshold shopping behavior, scoped notifications to in-app only, chose hosting, and landed on an
equal-permission dual-login model.

## Artifact 3: Scope discipline
Dropped receipt and photo OCR from v1, locked the final stock-in method set, and confirmed no data migration was
needed — the round that kept the comparison to enterprise discovery clean.

**The key insight:** the thing that actually slowed discovery down wasn't a technology gap, it was scope
discipline. A few easy-yes requests — receipt and photo scanning, push notifications, meal planning — had to be
explicitly pushed to a later phase to keep the experiment honest.

# What building revealed
This is where the real evidence lives. Every decision I made building the Kitchen ERP has a direct match in
enterprise ERP discovery — and building it forced each decision out in days, not workshop cycles.

[MAP-LIST]
## Row: Custom, arbitrary storage locations instead of the platform's 3 defaults
DOMAIN: Inventory zones / bin config
The need for unlimited, custom zones — not a fixed template — was obvious on day one of physically stocking the
kitchen. It's the kind of requirement that's easy to state in the abstract and easy to underscope in a workshop.

## Row: Barcode plus manual entry, starting from zero, no data migration
DOMAIN: Item / master data setup
Real barcode coverage gaps (regional and generic products) showed up the moment I actually scanned items on hand
— not from asking someone "will barcodes work for you?" in an interview.

## Row: Native barcode support plus an open barcode lookup service
DOMAIN: Barcode scanning / lookup integration
It exposed the unhappy path right away: what happens when a scan comes back empty — a failure mode that often
gets glossed over in a requirements doc until real testing happens.

## Row: Auto-add to shopping list at a minimum-stock threshold
DOMAIN: Inventory management rules
It forced an actual number — a real threshold — instead of a vague ask like "let us know when we're running low."

## Row: Two logins, identical full permissions, no admin/restricted split
DOMAIN: Role & permission model
Landing on a real decision here took one round of questions, compared to the many workshop cycles a multi-role
enterprise permission matrix usually eats up.
[/MAP-LIST]

[MEDIA: landscape — custom storage locations configured in Grocy]
Caption: Five custom zones — Cupboard, Freezer, Fridge, Pantry, Spice Cabinet — set up in place of the platform's three defaults.

[MEDIA: landscape — purchase flow and product overview with price history]
Caption: The purchase flow, with the product overview panel — price history, average shelf life, and spoil rate tracked automatically.

# The build
I self-hosted Grocy, an open-source inventory and ERP tool, on a budget cloud VPS — configured to fit our
household rather than custom-built. Keeping v1 to configuration only was itself a strategic call: it kept the
discovery test clean, so what I learned could be credited to the discovery process itself, not to how fast we
could code. Gabe handled deployment, infrastructure, and device testing, while I owned requirements,
prioritization, and the PRD.

[MEDIA-GRID]
[MEDIA: landscape — recipe-linked shopping list with live cost and calorie data]
[MEDIA: landscape — weekly meal plan, checked against real stock]
[/MEDIA-GRID]
Caption: Recipes pull live cost and stock data; the meal plan checks each recipe against what's actually on hand before it lands on the calendar — phase-2 features layered on once v1 discovery was locked.

# Pull quote
> The thing that actually slowed discovery down wasn't a technology gap — it was scope discipline.

(No attribution line on this one — it's a self-authored insight, not a testimonial. Leave the `—` line off entirely when there's no one to attribute it to.)

# Validation
Instead of a walkthrough or a mockup, I tested the live production app on an actual Android phone, across two
mobile browsers, within the first two days it was live. It loaded and worked on both. Barcode scanning
specifically wasn't verified yet on that platform, since that workflow wasn't fully configured at test time.

> CALLOUT (orange): Logged as a risk, not assumed
> I logged the unverified barcode-scanning path as an open risk instead of assuming it would be fine — a
> discipline enterprise testing often skips when a deadline is looming.

# Outcome
The long-term product metric — whether we actually keep using it day to day — needs more time before I can report
it honestly. What I can report now is how fast discovery and decisions actually moved, which is really the point
of this case study.

## Stat 1: 5 rounds
of structured discovery, compressed into one v1 PRD

## Stat 2: ~1 day
from PRD kickoff to a live production system

## Stat 3: 5 of 6
ERP-relevant decision categories surfaced and resolved in two weeks

# Reflection
Pairing — or in some cases swapping out — traditional interview-heavy ERP discovery with a real, working,
low-fidelity analog can surface the same kinds of dependencies and trade-offs in days instead of months, without
waiting on a long requirements document to get reviewed and signed off. That's directly useful for Atom + Bits'
Operational Readiness & Workflow Intelligence Assessment work, and it's worth trying out as an actual
client-facing method.

What I still need to test: a two-person household is a much simpler stakeholder environment than a
multi-department enterprise rollout, where competing incentives — not just missing information — are what
actually slow discovery down. I need to test this against a situation with real stakeholder conflict before I can
say it generalizes to enterprise clients. And I'd stress-test unit-of-measure configuration on purpose in v1
instead of defaulting past it, so the discovery-coverage story is a clean 6 for 6 instead of 5 of 6.
