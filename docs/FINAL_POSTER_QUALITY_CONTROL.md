# FINAL POSTER QUALITY CONTROL & MASTER REFERENCE COMPARISON
## LAKE 2026 — 15th Biennial Lake Symposium
**Master Design Authority**: User-Uploaded Reference Poster (*"INTEGRATING BUSINESS AND BIODIVERSITY"*)  
**Topic**: *"BIG DATA ANALYTICS OF MULTI-YEAR SENTINEL-2 SATELLITE IMAGERY FOR SEASONAL SURFACE-WATER MONITORING AT ANKASAMUDRA BIRD CONSERVATION RESERVE, KARNATAKA"*  
**Author**: Mohammed Ibrahim (BCA Honours – Data Science, Chanakya University)  
**Date**: November 3, 2026  
**Final Production Files**:
- Master Vector HTML Poster: [`poster/final/LAKE2026_Ankasamudra_Final.html`](file:///d:/big%20data/poster/final/LAKE2026_Ankasamudra_Final.html)
- High-Resolution Preview: [`poster/working/LAKE2026_Ankasamudra_Final_Preview.html`](file:///d:/big%20data/poster/working/LAKE2026_Ankasamudra_Final_Preview.html)
- Editable Presentation Generator: [`scripts/generate_pptx_reference_matched.py`](file:///d:/big%20data/scripts/generate_pptx_reference_matched.py)

---

## 1. Direct Visual Comparison against Master Reference

| Design Dimension | Master Reference Poster (*"Business & Biodiversity"*) | Final LAKE 2026 Poster (*"Ankasamudra"*)| Quality Audit |
|---|---|---|:---:|
| **Physical Dimensions** | Standard ISO A0 Portrait ($841 \times 1189\text{ mm}$, Aspect Ratio 1 : 1.414) | Configured with exact CSS `@page { size: 841mm 1189mm; margin: 0; }` and container ratio $1080 \times 1527\text{ px}$. | **PASSED** |
| **Top Institutional Logos** | Horizontal row of institutional partner logos across upper 3–6% margin | Clean white badges featuring official **IISc seal & Chanakya University emblem** (left) and **LAKE 2026 conference crest** (right). | **PASSED** |
| **Upper-Left Title** | Large bold uppercase royal-blue typography (`#1b52a4`) with dark slate subtitle and author line | Large bold royal-blue uppercase title: `INTEGRATING BIG DATA AND WETLAND HYDROLOGY`, with subtitle and student author strip. | **PASSED** |
| **Upper-Right Abstract** | Organic speech-bubble panel with a 3D circular ring emblem and concise abstract | Organic rounded card with the genuine **3D Toroidal Mobius Ribbon Ring** (`abstract_wetland_emblem.png`) and scientific abstract. | **PASSED** |
| **Middle 3-Column System** | 3 vertical modules (`Challenges`, `Levers`, `Key Takeaways`) with rounded borders and pastel status tabs | 3 rounded column modules (`border-radius: 18px`) with pastel badges (Yellow, Green, Blue, Pink) and clean internal hierarchy. | **PASSED** |
| **Scientific Visual Integration** | Modular cards embedding custom 3D isometric scientific models | Embedded **`sentinel2_satellite.png`**, **`bigdata_pyspark.png`**, **`wetland_biodiversity.png`**, and **`spectral_analysis.png`** with natural transparent alpha blending. | **PASSED** |
| **Lower 25–30% Hero** | 3D Earth globe resting on a circular futuristic white control console with rotary knobs and dials | Genuine **3D Wetland Earth Sphere** on white futuristic monitoring console (`hero_ankasamudra_wetland.png`) flanked by connecting telemetry paths. | **PASSED** |
| **Lower-Left QR Arrangement** | Stack of scannable QR codes with top labels | Scannable QR codes for Sentinel-2 GEE catalog, Mendeley Data DOI, and Ramsar Information Sheet. | **PASSED** |
| **Lower-Right Metrics** | Three stacked metric callout bubbles | Stacked metric badges: $97.82\text{ ha}$ OSAB, $1.2\text{M+}$ Pixels, and $10\text{m}$ Resolution. | **PASSED** |
| **Typography & Spacing** | High visual density, elegant margins, zero excessive blank space | Balanced whitespace, clean typography hierarchy (system UI / Inter / SF Pro fonts), zero generic blue box cards. | **PASSED** |

---

## 2. Scientific Integrity & Attribution Check

1. **No Data Fabrication**: Module 07 in Column 3 is styled with a prominent amber alert badge stating:
   > **STATUS: RESULTS PENDING SATELLITE PROCESSING**  
   Outlining planned empirical curves (Panel A: Seasonal Inundation, Panel B: 10m Hydroperiod Grid, Panel C: *Acacia nilotica* Dynamics) without fabricating fictional statistics.
2. **Boundary Definition**: Explicitly clarifies that Ankasamudra Reserve holds a gazetted area of **98.76 ha** (Survey No. 203, Ramsar Site 2535), while the **Operational Study-Area Boundary (OSAB v1.0, 97.82 ha)** reflects the physical tank-bed waterbody buffered by **>900m** from Tungabhadra backwaters.

