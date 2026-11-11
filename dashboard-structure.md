# Dashboard structure — tab by tab

Five tabs, ordered by audience: leadership reads tab 1; operators live in tabs 2–5. Date filters apply to flow cards (campaign performance, pipeline) and explicitly NOT to snapshot cards — that distinction is printed on the dashboard header so nobody has to discover it.

## Tab 1 — Overview (audience: leadership)

- **Header text card**: what this dashboard shows, what the date filter does and doesn't affect, data freshness
- **OKR tiles** (layer 1): activation share vs target · pipeline vs target · adoption logos vs target
- **Status flags row**: at-risk accounts · churned-from-higher-tier · expansion-ready — each a count with a definition tooltip
- **Lifecycle snapshot**: accounts & ARR by lifecycle bucket (point-in-time; unaffected by date filter)
- **Bucket progression**: 28-day movement between buckets — the "is the ladder working?" card

## Tab 2 — Lifecycle Buckets (audience: lifecycle operator)

Per product tier (e.g. core product / add-on / AI tier): accounts & ARR by bucket, plus usage-context cards. This is the targeting layer — campaign audiences are defined against these buckets.

## Tab 3 — Campaign Performance (audience: lifecycle operator, weekly review)

- **Attribution & performance summary** — one row per campaign: sends, human open %, click %, conversions, attributed deals (the layer-3 funnel)
- **Sales-led campaign detail**: demos + CSM conversations booked, active/canceled/no-show, deals created, closed-won ARR
- **Weekly engagement trends** and per-campaign delivery volumes
- **AI-personalization detail**: per-recommendation-type performance for the personalized campaigns

## Tab 4 — Pipeline (audience: growth lead + sales stakeholders)

- Deal board: deal × product, filtered to attributed deals
- Deals by campaign / by medium / by source (percent shares)
- Demo-link clicks with redirect-safe canonical paths (measurement integrity: raw URLs lie)

## Tab 5 — Deep Dives (audience: whoever is debugging)

Education clicks by bucket, top content destinations, website visits by canonical path, booking trends by event type. Anything exploratory lands here first and only graduates to tabs 1–4 with a target attached.

## Placement rules

1. A card earns Overview placement only if a decision depends on it weekly.
2. Every card states its date semantics (snapshot vs. flow) if there is any ambiguity.
3. Diagnostics never sit above attribution — the page order is the argument.
