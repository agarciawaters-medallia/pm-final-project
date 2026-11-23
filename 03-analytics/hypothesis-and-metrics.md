# Hypothesis & Success Metrics: RouteLogic Velocity

> **Module 3 · ★ Deliverable 3.** Repo file `03-analytics/hypothesis-and-metrics.md` — part of your submission.
> It feeds the **Problem, Value & Hypothesis** slide of your Module 6 final deck.

## Persona and problem

**Persona:** Frontline Driver — a delivery driver on a daily route, often handling packages in bad weather with one hand free.

**Goal:** Mark each stop complete quickly and accurately so the route moves on without slowing the delivery.

**Friction confirmed:**
- **Taps:** Marking a stop delivered takes three taps across three screens. Drivers have started texting their dispatcher instead (UXR-01; BUG-2055).
- **Routing accuracy:** Optimized routes send drivers down closed roads and ignore loading docks and one-way streets. One driver overrides the route every day (UXR-05; BUG-2068).
- **Availability:** The app crashes on longer routes and loses every remaining stop, costing up to twenty minutes while the office reads the list aloud (UXR-03; BUG-2031). In low-signal areas the stop list does not load and the route is blank (UXR-06; BUG-2050).

**Quantitative signal:** 31 min of daily time lost to manual workarounds, a 3.4x increase. Compliance CSAT is 2.8, the lowest score for drivers on the CSAT heatmap.

## Finalized product hypothesis

> Based on reported driver feedback (UXR-01, UXR-03, UXR-05, UXR-06) and the 31 min of daily time lost to manual workarounds, I believe that solving route accuracy, stop-completion speed, and offline availability for **Frontline Drivers** will result in **increased satisfaction and reduced churn**, as measured by a **[X%] reduction in average daily time lost** to workarounds. I will protect **NPS** and make a go/no-go decision after **30 days**, with an initial pivot analysis at **7 days**.

## Success metrics

| Metric | Type | Target | Why it matters |
|---|---|---|---|
| Enterprise customer churn (Frontline Driver accounts) | North-star (outcome) | [TBD: baseline and target not yet set] | Tests whether removing driver friction keeps high-value enterprise customers from moving to leaner alternatives. |
| Avg. daily time lost to workarounds | Leading indicator (initiative) | [X%] reduction from 31 min/day baseline | Direct measure of the administrative burden drivers currently absorb outside the platform. Primary signal for the 7-day pivot and 30-day go/no-go. |
| NPS | Guardrail (product) | Must not drop from current baseline | Protects the existing customer base while the friction fixes ship. |

## Decision window

- **7 days:** Initial pivot analysis on average daily time lost.
- **30 days:** Go/no-go decision. The 30-day view checks whether the change holds beyond the first week.
