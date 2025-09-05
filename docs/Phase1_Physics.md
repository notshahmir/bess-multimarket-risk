# Phase 1 — Battery Physics (half-hourly)

Time grid: t = 1..T, Δt = 0.5 h

Variables (conceptual):
- s_t  : SoC at start of period t  [MWh]
- p_ch_t, p_dis_t : charge/discharge power [MW]

Parameters:
- Emax, Pmax       : energy/power limits
- ηch, ηdis        : efficiencies (0,1]
- c_deg            : £/MWh throughput cost

Dynamics:
s_{t+1} = s_t + ηch * p_ch_t * Δt − (1/ηdis) * p_dis_t * Δt

Bounds:
0 ≤ s_t ≤ Emax
0 ≤ p_ch_t ≤ Pmax
0 ≤ p_dis_t ≤ Pmax
(soft) no simultaneous charge/discharge: penalise overlap initially

Cashflow per period:
π_t = price_t * (p_dis_t − p_ch_t) * Δt − c_deg * (p_ch_t + p_dis_t) * Δt

KPIs to report (later):
- Net revenue = Σ π_t
- Utilisation = Σ (p_ch_t + p_dis_t) Δt / (2 * Emax)
- Throughput (MWh), cycles/day (via rainflow later)
- Constraint binding rates (% periods at bounds)
