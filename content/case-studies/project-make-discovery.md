---
title: Scaling discovery to 100+ interviews without breaking the rules
where: Kroger · Manufacturing · Project MAKE
dek: Project MAKE had no inherited documentation, process, or roadmap — every workflow across 32 manufacturing facilities had to be discovered from scratch. Manual discovery couldn't move fast enough, and nothing outside Kroger's approved Microsoft 365 stack was on the table. So discovery had to be built twice — once on the plant floor, and once as a self-built AI workflow to make it scale.
role: Sr. Manager, Product & Program Management
timeline: Project MAKE · 2022-2025
team: Plant leadership, operators, 8 product teams, PMs
focus: Field discovery & AI-assisted synthesis at scale
metrics:
  - 100+ workflows mapped
  - 100+ interviews in 2 weeks
  - 8 product teams
---

<!-- NOTE: this page's map-list uses the two-label "DECISION: / DOMAIN:" variant — see the README's map-list
     note on the known inconsistency between this page and kitchen-erp.html. -->

# Key image
[MEDIA: landscape — photo or diagram representing field discovery, e.g. plant-floor observation, an interview guide template, or the SharePoint synthesis repository]
Caption: Discovery had to run on two tracks at once: hands-on field mapping, and a self-built workflow to synthesize it at scale.

# The problem
Project MAKE was moving 32 grocery, dairy, and bakery manufacturing facilities onto a modern, data- and
AI-enabled operating model — with no inherited documentation, process, or roadmap to build from. Every one of the
100+ workflows that ran those plants had to be discovered before it could be redesigned, and the stakes were
high: nuanced, high-stakes requirements had to translate into decisions that scaled across every facility, not
just the one where they were captured.

Later in the program, discovery had to scale again — this time for product requirements, not workflows. Eight
product teams needed input from 100+ stakeholders, on a timeline that made a manual interview-and-synthesis
process untenable. And the constraint that shaped the solution wasn't capability, it was security: only tools
already approved for enterprise use, Microsoft 365, could be considered. Nothing outside that stack was an
option.

> CALLOUT (teal): The constraint that shaped this
> No outside AI tools, no new vendor approvals, no additional cost. Whatever got built had to run entirely on
> Copilot, Teams, SharePoint, and Power Automate — tools Kroger had already sanctioned.

# What I did
Discovery ran on two tracks. The first was entirely hands-on: personally mapping 100+ undocumented workflows
through direct field discovery — onsite observation, interviews, and workflow mapping with plant leadership and
operators, facility by facility. There was no shortcut for this part; it required being on the floor.

## Artifact 1: Direct field discovery
Onsite observation and interviews with plant leadership and operators, mapping 100+ workflows facility by
facility with no inherited documentation to start from.

## Artifact 2: Self-built AI workflow
An automation layer on Copilot, Teams, SharePoint, and Power Automate to run stakeholder discovery at a scale
manual synthesis couldn't support.

## Artifact 3: Centralized synthesis repository
Thematic analysis across every transcript, routed and organized so product managers could pull findings
directly instead of waiting on a synthesis cycle.

The second track was the AI workflow, built to run 100+ stakeholder interviews across 8 product teams in two
weeks — with product requirements identified almost immediately after. Here's how the pieces fit together:

[MAP-LIST]
## Row: Interview guide creation
DECISION: Manual step replaced
DOMAIN: Auto-generated per session
The workflow auto-generated interview guides for each session from a master interview list, instead of a PM
assembling one by hand every time.

## Row: Document creation & naming
DECISION: Manual step replaced
DOMAIN: Power Automate orchestration
Power Automate orchestrated document creation and enforced naming conventions automatically, so nothing got
lost to an inconsistent file name.

## Row: Transcript routing
DECISION: Manual step replaced
DOMAIN: Routed to SharePoint by team
Transcripts were routed to the correct SharePoint folder by team automatically — no PM hunting for the right
interview later.

## Row: Synthesis & findings
DECISION: Manual step replaced
DOMAIN: Thematic analysis, centralized repository
Thematic analysis ran across transcripts automatically and synthesized findings into a repository PMs could
pull from directly, instead of waiting on a written report.
[/MAP-LIST]

# Pull quote
> The constraint that shaped this was security, not capability. I had to build that connective layer myself,
> using tools that were already sanctioned.
— Karina, on why the AI workflow had to be self-built rather than bought

# Outcome
Together, the two tracks turned a discovery problem with no starting material into a repeatable process: field
discovery gave the program its first real map of how the plants actually worked, and the AI workflow gave
product teams a way to gather and synthesize stakeholder input at a pace that matched the program's timeline
instead of lagging behind it. The bigger shift wasn't just speed — product managers got their time back from
administrative synthesis work and could focus on requirements that were both accurate and identified fast enough
to matter.

## Stat 1: 100+
workflows mapped facility by facility, with no inherited documentation

## Stat 2: 2 weeks
to run 100+ interviews across 8 product teams

## Stat 3: Weeks → days
requirements-gathering timeline, cut with zero added cost or security approval

# What's next in this series
This case study covers how Project MAKE built its discovery process from nothing, on the floor and in a
self-built AI workflow. The [alignment workshop](project-make-alignment.html) that turned that discovery work
into a shared plan is its own case study, as is the [change-management work](project-make-go-live.html) that
carried the plan through to a zero-downtime go-live. A mobility hardware rollout — Android handhelds and
scanners tested on the plant floor before deployment — is still to come.
