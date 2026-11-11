# growth-dashboard-spec

**How to build a lifecycle/growth dashboard that leadership actually reads** — the full specification of a dashboard I built and ran in production: metric hierarchy, tab structure, SQL patterns, and the design decisions behind them.

## The problem this solves

Most marketing dashboards report *activity* (sends, opens, campaigns launched) — so leadership stops reading them. This spec rebuilds reporting around *impact*: OKRs at the top, revenue attribution in the middle, diagnostics at the bottom. It's generalized from a dashboard I built for a lifecycle program; all table and metric names here use a fictional company.

## What's here

| File | What it covers |
|---|---|
| [`metric-hierarchy.md`](metric-hierarchy.md) | The four-layer hierarchy: OKR tiles → revenue attribution → funnel conversion → engagement diagnostics. Human metrics only — machine-inflated opens never appear |
| [`dashboard-structure.md`](dashboard-structure.md) | Tab-by-tab layout: Overview (OKR tiles + lifecycle snapshot), Campaign Performance, Pipeline, Deep Dives — with what belongs on each and why |
| 🔒 `sql-patterns.md` | The reusable queries: UTM-slug attribution joins, human-vs-machine open separation, per-campaign booking attribution, lifecycle bucket snapshots |

## What's public and what's on request

The metric hierarchy and dashboard structure are public. The SQL patterns (🔒) are **available on request**: [LinkedIn](https://www.linkedin.com/in/sara-beheyt/).

## The three design decisions that matter

1. **`utm_campaign` = registry slug is the only join key.** Every campaign built through the [pipeline](https://github.com/sara-beh8/lifecycle-campaign-skills) carries its registry slug in every link — so the attribution query is one join, and a new campaign appears in the dashboard the day it launches, with zero dashboard work.
2. **Human metrics only, at every layer.** Apple's mail privacy inflates opens with machine fetches; on the program this spec comes from, real human opens were about half the reported figure. The dashboard separates them once, at the SQL layer, and every downstream card inherits the honest number.
3. **Snapshot vs. flow, explicitly separated.** Lifecycle-bucket counts are a point-in-time snapshot; campaign performance is a dated flow. Mixing them is the #1 source of "these numbers don't add up" — here they live on different tabs with different date semantics, labeled as such.

## Companion repos

- [`lifecycle-campaign-skills`](https://github.com/sara-beh8/lifecycle-campaign-skills) — the build pipeline that generates the tracking this dashboard consumes
- [`lifecycle-ops-standards`](https://github.com/sara-beh8/lifecycle-ops-standards) — the naming/UTM/registry standards underneath both

Full case study with results: [sara-beh8.github.io](https://sara-beh8.github.io)
