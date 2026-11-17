# BLANK POSTER LAYOUT SPECIFICATION — 36 × 48 INCHES PORTRAIT
## Official LAKE 2026 Symposium Poster Shell
**Reference Template**: `deliberatingwatermelon_36x48.pptx` (from `LAKE_2026_Poster_Templates_All.zip`)  
**Design Authority**: Master Reference Poster (*"INTEGRATING BUSINESS AND BIODIVERSITY"*)  
**Physical Dimensions**:
- Width: **36.00 inches** ($91.44\text{ cm}$)
- Height: **48.00 inches** ($121.92\text{ cm}$)
- Aspect Ratio: **3 : 4** (0.750)  
- Orientation: **Portrait**  
**Author**: Mohammed Ibrahim  
**Affiliation**: School of Engineering, Chanakya University, Bengaluru, Karnataka, India  
**Programme**: BCA (Honours) — Data Science  
**Date**: November 3, 2026  

---

## 1. Page Budget & Vertical Zonation (Exact 36 × 48 Reference Match)

| Zone | Vertical Height % | Position from Top ($Y$) | Target Height | Primary Visual Content & Functional Elements |
|---|:---:|:---:|:---:|---|
| **A. Top Institutional Row** | 4.0% – 9.0% | $0.00\text{ in} - 4.32\text{ in}$ | $4.32\text{ in}$ | Clean horizontal row of official logos: **IISc seal badge** (`560x320`), **Chanakya University badge** (`560x320`), center conference identifier, and **LAKE 2026 official crest** (`900x379`). |
| **B. Upper Title & Abstract** | 10.0% – 32.0% | $4.32\text{ in} - 15.36\text{ in}$ | $11.04\text{ in}$ | **Left (56% width)**: Bold Royal Blue title (`#1b52a4`) `INTEGRATING BIG DATA AND WETLAND HYDROLOGY`, dark slate subtitle, author strip, and institutional credits.<br>**Right (44% width)**: Track badge pill (`LAKE2026-BD04`) and organic speech-bubble card enclosing the circular **3D Mobius Ribbon Ring** (`abstract_wetland_emblem.png`) and scientific abstract. |
| **C. Middle 3-Column Research Grid** | 33.0% – 72.0% | $15.36\text{ in} - 34.56\text{ in}$ | $19.20\text{ in}$ | 3 rounded column modules (`border-radius: 20px`) with pastel status tabs (Yellow, Green, Blue, Pink) and embedded 3D scientific illustrations:<br>• **Col 1 (Challenges)**: Measurement complexity, OSAB study area mask, and research objectives (`wetland_biodiversity.png`).<br>• **Col 2 (Levers)**: Sentinel-2 L2A (`sentinel2_satellite.png`), spectral index formulations (`spectral_analysis.png`), and PySpark engine (`bigdata_pyspark.png`).<br>• **Col 3 (Key Takeaways)**: Scheduled analytical outputs (gold pending alert), conservation policy, and Mendeley floristic data. |
| **D. Lower Central 3D Hero Region** | 73.0% – 95.0% | $34.56\text{ in} - 45.60\text{ in}$ | $11.04\text{ in}$ | **Center Stage**: Substantial 3D Wetland Earth Sphere resting on the futuristic circular telemetry control console (`hero_ankasamudra_wetland.png`), elevated with subtle drop shadows.<br>**Left**: Dual high-contrast scannable QR cards with quiet zones.<br>**Right**: Stacked key metric callout cards (97.82 ha OSAB, 1.2M+ pixels, 10m grid). |
| **E. Bottom Footer Strip** | 96.0% – 99.0% | $45.60\text{ in} - 48.00\text{ in}$ | $2.40\text{ in}$ | Thin divider with official symposium attribution, organizer credits, paper ID, and venue coordinates. |

---

## 2. Institutional Branding Assets Used

1. **IISc Official Badge**:
   - Source: `assets/official_lake2026_resources/logos/iisc_badge.png` (or `media_1793691171846_a7473b54.png`)
   - Native Size: $560 \times 320\text{ px}$
   - Placement: Top Left
2. **Chanakya University Official Badge**:
   - Source: `assets/official_lake2026_resources/logos/chanakya_badge.png`
   - Native Size: $560 \times 320\text{ px}$
   - Placement: Top Left (adjacent to IISc)
3. **LAKE 2026 Official Crest Badge**:
   - Source: `assets/official_lake2026_resources/logos/lake_badge.png` (or `media_1793691187537_072703a8.png`)
   - Native Size: $900 \times 379\text{ px}$
   - Placement: Top Right

---

## 3. Nano Banana 3D Scientific Illustration Integration

| Illustration Asset | Source File | Placement in 36 × 48 Layout | Visual Function |
|---|---|---|---|
| **Wetland Earth Hero** | `original.png` | Lower Central Console ($Y = 34.56\text{ in} - 45.00\text{ in}$) | Primary anchor showing wetland sphere on control platform |
| **Abstract Mobius Ring** | `original (1).png` | Upper-Right Abstract Speech Bubble ($Y = 5.50\text{ in}$) | 3D toroidal ring symbolizing cyclical wetland hydrology |
| **Sentinel-2 Satellite** | `original (2).png` | Column 2 — Remote Sensing Subcard ($Y = 16.50\text{ in}$) | Earth observation satellite projecting sensor swath |
| **Big Data Mainframe** | `original (3).png` | Column 2 — PySpark Engine Subcard ($Y = 27.50\text{ in}$) | Distributed compute engine with columnar data stacks |
| **Wetland Biodiversity** | `original (4).png` | Column 1 — Ecological Context Subcard ($Y = 16.50\text{ in}$) | Avifauna (Egrets) and emergent macrophytes |
| **Spectral Analysis** | `original (5).png` | Column 2 — Spectral Formulations Subcard ($Y = 22.00\text{ in}$) | Layered water & vegetation index analysis stack |

---

## 4. Deliverables Generated

1. **Editable PowerPoint Presentation (Exact 36 × 48 in)**:
   - [`poster/working/LAKE2026_Ankasamudra_Blank_Structure_36x48.pptx`](file:///d:/big%20data/poster/working/LAKE2026_Ankasamudra_Blank_Structure_36x48.pptx)
2. **High-Resolution Vector Layout (Full Portrait 36 × 48 in Canvas)**:
   - [`poster/working/LAKE2026_Ankasamudra_Blank_Structure_36x48.html`](file:///d:/big%20data/poster/working/LAKE2026_Ankasamudra_Blank_Structure_36x48.html)
3. **Stand-Alone Generator Script**:
   - [`scripts/build_36x48_pptx.py`](file:///d:/big%20data/scripts/build_36x48_pptx.py)

