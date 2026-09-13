# Thermal Integration and Life-Cycle Carbon Optimization of a Naphtha Hydrotreating Unit

**Engineering Project Report** — Aspen Plus · Excel (Problem Table Algorithm) · openLCA

**Author:** Shivam Sharma
**Institution:** Indian Institute of Technology Guwahati
**Project area:** Naphtha Hydrotreating, Heat Integration and Life-Cycle Assessment

---

## Overview

This project is an independently developed engineering study of a light-naphtha hydrotreating (NHT/HDS) unit, built across three complementary computational layers:

1. **Aspen Plus** — process simulation and stream characterization of the naphtha hydrotreating unit (thiophene hydrogenolysis in a plug-flow reactor, PR-BM thermodynamics).
2. **Excel / Problem Table Algorithm (PTA)** — pinch-analysis heat-integration targeting between the reactor effluent (hot stream) and the incoming mixed feed (cold stream).
3. **openLCA** — comparative life-cycle assessment (GWP100) of the baseline vs. heat-integrated utility scenarios.

The central question: **can the reactor effluent supply the sensible heating requirement of the incoming feed, and what is the environmental payoff of doing so?**

## Key Results

| Metric | Baseline | Optimized (heat-integrated) |
|---|---|---|
| Mixed feed / reactor inlet / outlet temperature | 17.141 °C / 310 °C / 343.063 °C | — |
| Cold-stream duty (PTA) | 31.483 GJ/h | supplied internally |
| Hot-stream duty (PTA) | 32.504 GJ/h | recovered internally |
| Minimum hot utility (ΔTmin = 20 °C) | — | **0 GJ/h** |
| Minimum cold utility | — | **1.020 GJ/h** |
| Total GWP100 | 5,339.298 kg CO₂-eq/h | **94.279 kg CO₂-eq/h** |
| Annualized GWP100 (8,000 h/yr) | 42,714.38 t CO₂-eq/yr | 754.23 t CO₂-eq/yr |
| **GWP100 reduction** | — | **98.234 %** |

Full derivations, the heat cascade, composite curves, and the Aspen–PTA–openLCA data-reconciliation are in the report.

## Repository Structure

```
├── report/         Full engineering report (PDF/DOCX)
├── data/
│   ├── aspen/       Aspen Plus Results.xlsx — stream & unit-duty outputs
│   ├── pta_excel/   Excel Results (Problem Table Algorithm).xlsx — hot/cold streams, cascade, composite curves
│   └── openlca/     openLCA Results.xlsx — GWP100 baseline vs. optimized LCIA results
├── flowsheet/       Process flowchart (Naphtha Hydrotreating unit)
└── figures/         Supporting charts (heat cascade, composite curves, GWP comparison)
```

## Methodology Summary

| Step | Tool | Purpose |
|---|---|---|
| 1 | Aspen Plus | Thermodynamic model, stream conditions, reaction section, unit results |
| 2 | Excel / PTA | Stream extraction, temperature shifting, cascade, utility targeting, composite curves |
| 3 | Network concept | Reactor-effluent heat recovery translated into a practical HEN arrangement |
| 4 | openLCA | Baseline vs. integrated utility scenarios, ecoinvent 3.12, IPCC 2021 GWP100a |
| 5 | Reconciliation | Cross-checking Aspen block duties, PTA stream duties, and annualized LCA results |

## Assumptions

- 8,000 operating hours/year
- 20 °C minimum temperature approach (±10 °C stream shift)
- Constant heat-capacity-flow (CP) treatment across PTA intervals
- 80% fired-heater efficiency (baseline hot utility)
- Cooling COP = 3.0 (cooling duty → equivalent electrical load)
- ecoinvent 3.12 (allocation, cut-off) background data

## References

- Abdullah, A. S., Al-Behadili, S. A., Homod, R. Z., & Mohammed, H. I. (2024). *Process Simulations and Analysis of Optimal Naphtha Hydrotreating Operating Range Parameters: A Case Study in Basra Refinery.* Process Integration and Optimization for Sustainability, 8, 1–11.
- Gary, J. H., Handwerk, G. E., & Kaiser, M. J. (2007). *Petroleum Refining: Technology and Economics* (5th ed.). CRC Press.
- Smith, R. (2005). *Chemical Process Design and Integration.* John Wiley & Sons.
- Towler, G., & Sinnott, R. (2012). *Chemical Engineering Design* (2nd ed.). Butterworth-Heinemann.
- Wernet, G., Bauer, C., Steubing, B., Reinhard, J., Moreno-Ruiz, E., & Weidema, B. (2016). *The ecoinvent database version 3 (part I): overview and methodology.* Int. J. LCA, 21(9), 1218–1230.

## Notes on Scope

This is a comparative, gate-to-gate utility-system LCA — not a cradle-to-grave assessment of the naphtha product, catalyst, or plant construction. The PTA result is a thermodynamic target, not a mechanical heat-exchanger design; area, pressure drop, fouling, and control philosophy are recommended as next-stage work (see report, Section 13.3).

---
*This repository is maintained as supporting evidence for the corresponding entry in the author's CV, submitted to the Career Development Centre (CCD), IIT Guwahati.*
