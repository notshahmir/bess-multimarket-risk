# Ancillary Auctions via EAC (NESO)

What we need:
- Day-ahead auction results for Dynamic Containment/Regulation/Moderation (and Reserve where applicable).
- Fields: clearing price (capacity), cleared volume, start/end timestamps for each service period.

Context & docs:
- NESO official EAC page (co-optimised procurement, multi-service participation). :contentReference[oaicite:12]{index=12}
- Ofgem decision approving EAC (Oct 13, 2023). :contentReference[oaicite:13]{index=13}
- Market explainers / changes in data format post-launch. :contentReference[oaicite:14]{index=14}

Notes:
- EAC rows are defined by start/end timestamps (not EFA blocks). :contentReference[oaicite:15]{index=15}
- Expect occasional negative clearing prices (charging incentive).
