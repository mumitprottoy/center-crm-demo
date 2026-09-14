# Center Command — Centers CRM demo

A clickable, self-contained demo of the BowlersNetwork Centers CRM, built to
share with bowling center owners and managers.

**Live:** https://center-demo.bowlersnetwork.com

## What it is

A single static HTML file. No backend, no database, no build step. All state
lives in the page, so every click works — importing a list, filtering an
audience, messaging a team — but nothing leaves the browser and nothing is
sent to anyone.

Sample data is generated from a fixed seed, so every viewer sees identical
numbers. That matters when it's being screen-shared and pointed at.

## What it demonstrates

- **Dashboard** — customers, how many have joined BowlersNetwork, reachable
  by filter, upcoming events.
- **Customers** — import a CSV/XLSX looking for three columns (`email`
  required, `first_name` / `last_name` optional), reporting what it mapped,
  skipped and merged. Plus single add via the existing invite flow.
- **Groups** — a league, its teams, rosters, captains, and a subs list.
  Message any level: whole league, one team, the subs, or one bowler.
- **Contact record** — a bowler's live BowlersNetwork profile (average, age,
  DOB, favourite brands, accomplishments), not a copy. One-click rewards on
  accomplishments.
- **Events** — set up an event and watch a live count of exactly who it
  reaches as the filters change, then invite them in one click.
- **Reach** — the same audience filters pointed at feed, message and groups.

## Deploying a change

Edit `index.html`, commit, push. Prod pulls from `main`:

```bash
ssh bn-prod 'cd /var/www/center-demo && git pull'
```

No restart, no build — nginx serves the file directly.

## Known gaps (deliberate)

- **SMS/text** is offered as a channel in the UI but is not built in the
  platform — Twilio groundwork only.
- **Sub-groups** (League → Team nesting) do not exist in the shipped Groups
  feature. Shown here as product direction.
