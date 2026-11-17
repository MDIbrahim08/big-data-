# FINAL POSTER DESIGN AUDIT & SCIENTIFIC PRODUCTION REPORT
## LAKE 2026 — 15th Biennial Lake Symposium
**Host Institutions**: Chanakya University & Energy and Wetlands Research Group (EWRG), Centre for Ecological Sciences, Indian Institute of Science (IISc), Bengaluru  
**Title**: *"BIG DATA ANALYTICS OF MULTI-YEAR SENTINEL-2 SATELLITE IMAGERY FOR SEASONAL SURFACE-WATER MONITORING AT ANKASAMUDRA BIRD CONSERVATION RESERVE, KARNATAKA"*  
**Author**: Mohammed Ibrahim  
**Programme**: Bachelor of Computer Applications (Honours) – Data Science  
**Affiliation**: School of Engineering, Chanakya University, Bengaluru, Karnataka, India  
**Date**: November 3, 2026  
**Primary Deliverables**:
1. HTML Master Document: [`poster/working/LAKE2026_Ankasamudra_ReferenceMatched.html`](file:///d:/big%20data/poster/working/LAKE2026_Ankasamudra_ReferenceMatched.html)
2. Standalone Editable PPTX Script: [`scripts/generate_pptx_reference_matched.py`](file:///d:/big%20data/scripts/generate_pptx_reference_matched.py)
3. Asset Register: [`docs/NANO_BANANA_ASSET_REGISTER.md`](file:///d:/big%20data/docs/NANO_BANANA_ASSET_REGISTER.md)

---

## 1. Executive Summary & Design Authority

The visual architecture for this scientific research poster has been reconstructed to achieve a **1:1 compositional match** with the user-designated Master Design Reference (*"INTEGRATING BUSINESS AND BIODIVERSITY"*), while strictly incorporating the **official LAKE 2026 symposium branding**, institutional marks, and genuine geospatial research data for Ankasamudra Bird Conservation Reserve.

---

## 2. Side-by-Side Visual Feature Matrix

| Master Reference Element | Reference Specification | LAKE 2026 Ankasamudra Implementation | Audit Status |
|---|---|---|:---:|
| **Poster Dimensions** | ISO Standard A0 Portrait ($841 \times 1189\text{ mm}$, Aspect Ratio 1 : 1.414) | Formatted with CSS `@page { size: 841mm 1189mm; margin: 0; }` and container ratio $1080 \times 1527\text{ px}$. | **MATCH** |
| **Canvas Background** | Pure white page with subtle drop-shadow on presentation wall | Pure white canvas (`#ffffff`), 0-margin vector layout on royal-blue review backdrop. | **MATCH** |
| **Top Institutional Logos** | Horizontal row of sponsor and institutional badges across upper margin | Official IISc seal & Chanakya University composite emblem (left) and LAKE 2026 official crest (right). | **MATCH** |
| **Upper-Left Title** | Large bold uppercase royal-blue typography (`#1b52a4`) with dark slate subtitle and author metadata | `INTEGRATING BIG DATA AND WETLAND HYDROLOGY` in uppercase royal blue, followed by subtitle and student credits. | **MATCH** |
| **Upper-Right Abstract** | Organic speech-bubble rounded panel with a 3D circular ring emblem and concise abstract paragraph | Organic card (`border-radius: 20px`) with circular 3D Mobius toroidal ring emblem and peer-reviewed abstract. | **MATCH** |
| **Track Badge Pill** | Dark blue pill badge in upper-right corner (`PB62`) | Royal-blue track pill: `LAKE2026-BD04`. | **MATCH** |
| **Middle 3 Columns** | Three rounded vertical modules (`Challenges`, `Levers`, `Key Takeaways`) with internal subcards and pastel tabs | 3 distinct rounded vertical modules (`border-radius: 18px`) containing modular subcards with pastel status badges (Yellow, Green, Blue, Pink). | **MATCH** |
| **Subcard Miniatures** | Geometric 3D vector cubes and data flow diagrams embedded in subcards | Multi-spectral 3D cube, sensor polyhedron, and spectral index tags (`NDWI`, `NDVI`, `MNDWI`). | **MATCH** |
| **Lower 25-30% Hero** | 3D Earth globe resting on a circular control console platform with rotary dials and sensor nodes | High-resolution 3D Wetland Earth Sphere on white circular console platform with illuminated nodes and dials. | **MATCH** |
| **Lower-Left QR Codes** | Vertical stack of 2 high-contrast scannable QR codes with top labels | Dual SVG QR codes linking to Copernicus Sentinel-2 Catalog and Mendeley Wetland Floristic Dataset. | **MATCH** |
| **Lower-Right Metrics** | Stack of metric callout cards on the right of the hero console | Stacked cards: `97.82 Hectares (OSAB)`, `1.2M+ Pixels`, and `10m Resolution`. | **MATCH** |
| **Bottom Footer** | Thin horizontal divider with symposium title, affiliations, and presentation ID | Clean divider with full conference attribution: *LAKE 2026: 15th Biennial Lake Conference &bull; Chanakya University &bull; IISc CES*. | **MATCH** |

---

## 3. Scientific Integrity & Rigour

1. **Cadastral vs Operational Boundary**:
   - The poster accurately reflects that Ankasamudra Bird Conservation Reserve holds a gazetted statutory area of **98.76 hectares** (Survey No. 203, FEE 04 FWL 2017, Ramsar Site No. 2535).
   - The **Operational Study-Area Boundary (OSAB v1.0, 97.82 ha)** reflects the physical tank-bed waterbody boundary, buffered by **>900 meters** from the Tungabhadra backwaters to prevent contamination from reservoir fluctuations.
2. **Scheduled Results Status (No Data Fabrication)**:
   - Module 07 in Column 3 is clearly styled with a gold alert badge stating:
     > **STATUS: RESULTS PENDING SATELLITE PROCESSING**
   - Outlines planned empirical panels (Inundation Trends, 10m Hydroperiod Grid, *Acacia nilotica* dynamics) without fabricating fictional numbers or trend lines.
3. **Reproducibility**:
   - Links provided to the official Copernicus Sentinel-2 Level-2A data catalog and Mendeley Floristic Inventory dataset (210+ vascular plant species across *Acacia nilotica* groves).

---

## 4. How to Print the Final Vector PDF

1. Open [`poster/working/LAKE2026_Ankasamudra_ReferenceMatched.html`](file:///d:/big%20data/poster/working/LAKE2026_Ankasamudra_ReferenceMatched.html) in Google Chrome, Microsoft Edge, or Mozilla Firefox.
2. Press **Ctrl + P** (Print).
3. In the Print Dialog:
   - **Destination**: *Save as PDF*
   - **Paper Size**: *A0* (or $841 \times 1189\text{ mm}$)
   - **Layout**: *Portrait*
   - **Margins**: *None* (or *Minimum*)
   - **Options**: Ensure **Background graphics** is **CHECKED**
4. Click **Save** and save to [`poster/final/LAKE2026_Ankasamudra_ReferenceMatched.pdf`](file:///d:/big%20data/poster/final/LAKE2026_Ankasamudra_ReferenceMatched.pdf).

