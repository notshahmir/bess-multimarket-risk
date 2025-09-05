# Test Cases

## D1) One-step charge test

**Params:**  
- Emax = 2  
- Pmax = 1  
- ηch = ηdis = 1  
- Δt = 0.5  
- s1 = 1.0  

**Action:**  
- p1ch = 1.0 MW  
- p1dis = 0  

**Expect:**  
- s2 = 1.0 + 1.0 × 0.5 = **1.5 MWh**  

If any result in your future notebook deviates, SoC update is wrong.  

---

## D2) Round-trip loss test

**Params:**  
- Same as D1, but ηch = ηdis = 0.95  
- Two periods  

**t=1 (charge 1.0 MW):**  
- s2 = 1.0 + 0.95 × 1.0 × 0.5 = **1.475 MWh**  

**t=2 (discharge 1.0 MW):**  
- s3 = 1.475 − (1.0 × 0.5 / 0.95) = **0.9474 MWh**  

**Net energy loss:** ≈ 0.0526 MWh  
**Round-trip efficiency:** ηrt = ηch × ηdis = **0.9025**  

---

## D3) Bound test

**Start:**  
- s1 = 1.95 MWh  

**Action:**  
- Try charging 1.0 MW for 0.5 h at any efficiency  

**Requirement:**  
- Solver must cap pch or reject the plan  
- s2 must not exceed Emax = **2.0 MWh**  

---

## D4) Cashflow sign test

**Params:**  
- Single period  
- Price = £100/MWh  
- Δt = 0.5  
- No degradation  

**Charge 1 MW:**  
- π1 = 100 × (−1) × 0.5 = **−£50**  

**Discharge 1 MW:**  
- π1 = **+£50**  

**Add degradation cost:**  
- cdeg = £2/MWh  
- Throughput = 1 MW × 0.5 h = 0.5 MWh  
- Extra cost = £1 per half-hour at 1 MW  
