# Multi-Market Battery Dispatch & Risk Management (BESS)

## What this is
A quantitative, risk-aware digital twin of a UK battery trading strategy. It co-optimises Day-Ahead, Balancing/Intraday, and Ancillary (frequency response/reserve) while respecting battery physics, and reports risk-adjusted performance (VaR/CVaR, drawdowns).

## Markets in scope
- **Day-Ahead (DA):** scheduled half-hourly prices (ENTSO-E).
- **Balancing / System Price (BM):** realised imbalance cash-out prices (Elexon Insights).
- **Ancillary (Frequency Response/Reserve via EAC):** capacity auctions (NESO EAC).

## Planned features
- Battery physics engine (SoC, round-trip efficiency, power/energy bounds, simple degradation).
- Single-market optimiser (DA) → rolling version.
- Add BM stream → coordinated allocation.
- Add Ancillary capacity reservation.
- Scenario generator across markets (correlated).
- CVaR-aware optimisation; mean–CVaR frontier.
- Attribution: P&L by stream, tail-risk drivers.
- Visuals: dispatch overlays, P&L/drawdowns, contribution charts.

## Data sources (authoritative)
- **Elexon Insights (System Price DISEBSP & detail):** API docs + “Detailed system prices” explainer. :contentReference[oaicite:0]{index=0}
- **ENTSO-E Transparency (Day-Ahead prices):** REST API user guide / Postman. :contentReference[oaicite:1]{index=1}
- **NESO EAC (Ancillary auction results & context):** official page + Ofgem approval + market explainers. :contentReference[oaicite:2]{index=2}

## Folder structure
data/ # raw not tracked
docs/ # data notes, design docs
notebooks/ # colab-first workflows
reports/figures/ # images for the report
src/ # python modules later
tests/ # unit tests later


## Glossary
- **SoC:** state of charge (MWh).
- **Pmax/Em ax:** power/energy limits.
- **System Price:** imbalance cash-out price (GBP/MWh). :contentReference[oaicite:3]{index=3}
- **EAC:** Enduring Auction Capability for frequency response/reserve. :contentReference[oaicite:4]{index=4}

## Roadmap (milestones)
1) Physics engine (deterministic).  
2) DA optimiser (perfect foresight → rolling).  
3) Add BM stream (choice/reservation).  
4) Add Ancillary (capacity & activation).  
5) Scenario generator (correlated).  
6) CVaR-aware optimisation.  
7) Attribution & diagnostics.  
8) Final visuals + write-up.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/notshahmir/bess-multimarket-risk/blob/main/notebooks/01_physics.ipynb)
