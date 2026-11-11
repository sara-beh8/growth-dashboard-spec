# Metric hierarchy — impact first, diagnostics last

The order on the page is the argument: the dashboard opens with what leadership is accountable for and descends toward what marketers debug with. A reader who stops after ten seconds still leaves with the right picture.

## Layer 1 — OKR tiles (top of Overview)

One tile per OKR, each with actual vs. target and a trend:

| Tile | Example (fictional) | Why a tile |
|---|---|---|
| Activation share | "Feature X active accounts: 14% → target 18%" | The single number the program exists to move |
| Pipeline vs target | "Q cumulative attributed pipeline vs $400k target" | Revenue accountability, stated plainly |
| Adoption logos | "New feature adoptions: actuals vs quarterly target" | Volume complement to the share metric |

Rules: a tile shows ONE number, its target, and direction. No tile without a target — an untargeted number is a diagnostic, and belongs in layer 4.

## Layer 2 — Revenue attribution

Deals and closed-won ARR attributed to campaigns via the `utm_campaign` join (SQL patterns available on request). Reported per campaign and per motion, with the attribution window stated on the card (e.g. 7-day click-based). Honesty rule: the window and the method are printed on the card itself — an attribution number without its method is an argument waiting to happen.

## Layer 3 — Funnel conversion

Per campaign: sends → human opens → clicks → conversions (bookings, feature enablements, trials). This is where "sends → booked conversations" lives — the layer that connects activity to layer 2's revenue.

## Layer 4 — Engagement diagnostics

Weekly deliveries, human open/click trends, segment sizes, suppression counts. Useful for the operator, invisible to leadership by default (bottom tab placement).

## The human-metrics rule (applies to every layer)

Machine-inflated opens are excluded at the SQL layer, once, in a shared view — not per-card. Every card that says "opens" means human opens. The inflated figure appears exactly once in the whole dashboard: on a small reference card explaining why the numbers are lower than the ESP's UI shows.
