# Williamson County, TN — Vision Classification Report

**Date:** February 11, 2026  
**Sites Analyzed:** 22  
**Method:** Each satellite thumbnail with NDVI change overlay was analyzed via vision model to classify development type.

## Summary

| Classification | Count | % |
|---|---|---|
| CONFIRMED SUBDIVISION | 1 | 4.5% |
| PROBABLE DEVELOPMENT | 6 | 27.3% |
| COMMERCIAL/INDUSTRIAL | 1 | 4.5% |
| FALSE POSITIVE | 14 | 63.6% |

**Genuine subdivision development (Confirmed + Probable): 7 of 22 (31.8%)**

## Detailed Results

| Site | Lat | Lon | Acres | Score | Vision Classification | Explanation |
|---|---|---|---|---|---|---|
| 1 | 35.9358 | -86.9371 | 6.84 | 95 | FALSE POSITIVE | Golf course — sand bunkers, greens, and fairways visible; clearing is routine course maintenance. |
| 2 | 35.9631 | -86.8429 | 18.66 | 90 | PROBABLE DEVELOPMENT | Large contiguous clearing within established suburban neighborhood; consistent with infill subdivision prep, but no roads/lots visible yet. |
| 3 | 36.0302 | -87.0664 | 14.85 | 90 | PROBABLE DEVELOPMENT | Cleared forested parcel adjacent to existing road; consistent with early-stage site preparation, no platted infrastructure yet. |
| 4 | 35.9443 | -86.7671 | 13.34 | 90 | PROBABLE DEVELOPMENT | Clearing directly adjacent to existing subdivision with curvilinear streets; likely expansion phase, no new road grading visible. |
| 5 | 35.9370 | -86.9363 | 2.52 | 90 | FALSE POSITIVE | Golf course — same facility as Site 1; sand bunkers and manicured greens clearly visible. |
| 6 | 36.0188 | -86.7603 | 11.19 | 89 | CONFIRMED SUBDIVISION | Active subdivision under construction adjacent — visible cul-de-sacs, foundations, and completed homes; this clearing is next phase expanding east. |
| 7 | 35.9515 | -87.0185 | 10.08 | 89 | PROBABLE DEVELOPMENT | Scattered clearing in wooded area near road and structure; consistent with early land prep but no visible lot/road patterns. |
| 8 | 35.9276 | -87.0444 | 36.99 | 88 | PROBABLE DEVELOPMENT | Extensive 37-acre clearing with possible preliminary road/cul-de-sac outlines; adjacent to low-density residential area. |
| 9 | 35.9411 | -86.9936 | 16.56 | 88 | PROBABLE DEVELOPMENT | Systematic clearing near lake in forested area; consistent with initial subdivision phase but could also be timber harvesting. |
| 10 | 35.8749 | -86.7901 | 8.20 | 88 | FALSE POSITIVE | Scattered clearing across existing rural farmland/pastureland with farmstead structures; no subdivision infrastructure visible. |
| 11 | 35.8775 | -87.0840 | 2.22 | 88 | COMMERCIAL/INDUSTRIAL | Existing commercial/industrial facility with warehouses, paved lots, and equipment yards. |
| 12 | 35.8840 | -86.9270 | 22.68 | 87 | PROBABLE DEVELOPMENT (WEAK) | Irregular clearing in wooded area adjacent to rural properties; no graded roads or lot pads visible yet. |
| 13 | 35.8980 | -86.9125 | 19.97 | 87 | FALSE POSITIVE | Scattered clearing across existing rural residential parcels and fields; no new road infrastructure or platted lots. |
| 14 | 35.8733 | -86.7932 | 10.65 | 87 | FALSE POSITIVE | Rural/agricultural landscape with dispersed farmsteads and pastures; routine agricultural activity. |
| 15 | 35.9108 | -86.8794 | 5.96 | 87 | FALSE POSITIVE | Narrow linear corridor through developed area; likely road widening or utility corridor, not subdivision. |
| 16 | 35.9047 | -86.8802 | 2.25 | 87 | FALSE POSITIVE | Adjacent to commercial/industrial zone with materials yard; no residential patterns visible. |
| 17 | 36.0042 | -86.8119 | 21.65 | 86 | FALSE POSITIVE | Already-established residential neighborhood; detected change is seasonal leaf-off revealing existing rooftops. |
| 18 | 35.9360 | -86.8751 | 4.72 | 82 | FALSE POSITIVE | Fully built-out existing neighborhood; detected clearing is routine yard maintenance or tree removal. |
| 19 | 35.9456 | -87.0191 | 2.92 | 82 | FALSE POSITIVE | Narrow linear path through forest; likely utility corridor or trail clearing. |
| 20 | 35.9509 | -87.0159 | 3.26 | 81 | FALSE POSITIVE | Scattered points across disconnected wooded areas; natural vegetation change or timber harvesting. |
| 21 | 35.9489 | -87.0134 | 2.15 | 74 | FALSE POSITIVE | Scattered points on existing rural property with structures; natural canopy variation or minor tree removal. |
| 22 | 35.9442 | -86.9781 | 2.13 | 50 | FALSE POSITIVE | Small clearing within agricultural pastoral field; no subdivision infrastructure visible. |

## Key Takeaways

1. **Only 1 site (Site 6) is a confirmed active subdivision** — it shows clear cul-de-sacs, foundations, and homes under construction.
2. **6 sites are probable development** (Sites 2, 3, 4, 7, 8, 9) — showing clearing patterns consistent with early-stage subdivision prep but lacking visible infrastructure.
3. **14 of 22 sites (64%) are false positives** — including golf course maintenance (2), existing neighborhoods with seasonal change (2), agricultural activity (4), utility corridors (2), commercial/industrial (2), and rural property maintenance (2).
4. **The algorithm's highest-scored site (Site 1, score 95) is a golf course** — a clear false positive, suggesting the scoring model would benefit from incorporating land use data.
5. **Score correlation is weak** — false positives appear across all score ranges (50-95), indicating the NDVI/NDBI metrics alone cannot reliably distinguish subdivision development from other clearing activities.

## Recommendations for Algorithm Improvement

- **Add land use/zoning overlay** — would immediately filter golf courses, existing commercial, and agricultural parcels
- **Add road network proximity analysis** — genuine subdivisions almost always connect to existing road infrastructure with new internal roads
- **Filter existing built-up areas** — Sites 17, 18 are fully developed neighborhoods; a pre-existing impervious surface check would catch these
- **Minimum contiguous area threshold** — many false positives are small scattered clearings under 5 acres
