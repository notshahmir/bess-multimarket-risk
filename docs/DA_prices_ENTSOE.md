# Day-Ahead Prices (ENTSO-E)

What we need:
- Bidding zone: Great Britain (GB).
- Resolution: 30 min (map to UK settlement periods; handle DST).
- Units: EUR/MWh or GBP/MWh (document units returned).

Docs:
- ENTSO-E Transparency REST API guide. :contentReference[oaicite:5]{index=5}
- Developer Postman collection (handy field names). :contentReference[oaicite:6]{index=6}

Notes:
- Requires API token (free, register on Transparency Platform Help/KB). :contentReference[oaicite:7]{index=7}
- Keep an index of timestamps aligned to settlement periods (SP1..SP48; SP46–SP50 on DST days).
