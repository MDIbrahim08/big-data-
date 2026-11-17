# POSTER DESIGN SPECIFICATION — LAKE 2026
## 15th Biennial Lake Symposium: Conservation of Wetlands, Traditional Knowledge with Innovative Nature-Based Technologies for Viksit Bharat

**Organizers**: Chanakya University and Energy and Wetlands Research Group (EWRG), Centre for Ecological Sciences, Indian Institute of Science (IISc), Bengaluru  
**Symposium Theme**: Monitoring of ecosystems using Big Data, Remote Sensing, Artificial Intelligence, Machine Learning and Deep Learning  
**Working Research Title**: *"Big Data Analytics of Multi-Year Sentinel-2 Satellite Imagery for Seasonal Surface-Water Monitoring at Ankasamudra Bird Conservation Reserve, Karnataka"*  
**Document ID**: `docs/POSTER_DESIGN_SPECIFICATION.md`  
**Date**: November 3, 2026  

---

## 1. Verified Conference Poster Sizes & Dimension Specifications

The official LAKE 2026 Symposium guidelines provide layout configurations across five standard academic presentation dimensions:

| Template Option | Format / Size | Width × Height (Inches) | Width × Height (mm) | Aspect Ratio | Standard Usage |
|---|---|---|---|---|---|
| **Option 1 (Official Master)** | **A0 Standard (Portrait)** | **33.11″ × 46.81″** | **841 mm × 1189 mm** | **1 : 1.414 ($\sqrt{2}$)** | **Standard IISc Lake Symposium Board (RECOMMENDED)** |
| **Option 2** | Arch E Large (Portrait) | 36.00″ × 48.00″ | 914 mm × 1219 mm | 3 : 4 | Extended symposium board |
| **Option 3** | Arch E (Landscape) | 48.00″ × 36.00″ | 1219 mm × 914 mm | 4 : 3 | Wide horizontal display board |
| **Option 4** | A1 Standard (Portrait) | 23.39″ × 33.11″ | 594 mm × 841 mm | 1 : 1.414 | Compact student presentation |
| **Option 5** | 36″ × 42″ (Portrait) | 36.00″ × 42.00″ | 914 mm × 1067 mm | 6 : 7 | Conventional poster stand |

### Selected Presentation Format:
**Option 1: International Standard A0 Portrait ($841\text{ mm} \times 1189\text{ mm}$ / $33.11'' \times 46.81''$)**  
*Rationale*: A0 Portrait is the primary standard across IISc Energy and Wetlands Research Group Lake symposia and fits the physical easel boards allocated at Chanakya University.

---

## 2. Institutional Branding & Logo Architecture

The poster header strictly positions the official conference and institutional emblems without distortion or synthetic redesign:

```
+---------------------------------------------------------------------------------------------------+
|  [LOGO 1: Chanakya Univ]       LAKE 2026: 15th BIENNIAL LAKE SYMPOSIUM        [LOGO 2: IISc / EWRG]|
|                               School of Engineering, Chanakya University                          |
|                                                                                                   |
|     BIG DATA ANALYTICS OF MULTI-YEAR SENTINEL-2 SATELLITE IMAGERY FOR SEASONAL                   |
|     SURFACE-WATER MONITORING AT ANKASAMUDRA BIRD CONSERVATION RESERVE, KARNATAKA                  |
|                                                                                                   |
|                    Author: [Presenter Name / Student ID: BCA (Hons) Data Science]                |
|                    Faculty Guide / Affiliation: School of Engineering, Chanakya University        |
+---------------------------------------------------------------------------------------------------+
```

- **Top Left**: Official Chanakya University Emblem (Transparent PNG / High-res SVG).
- **Top Right**: Indian Institute of Science (IISc) / Energy and Wetlands Research Group (EWRG) Crest.
- **Center Header**: Official LAKE 2026 Symposium insignia and subtitle banner.
- **Proportions Rule**: Logo aspect ratios locked; strictly 0% distortion.

---

## 3. Grid, Layout & Typography Hierarchy (A0 Portrait)

### 3.1 Three-Column Structural Grid
- **Slide Dimensions**: $84.1\text{ cm} \times 118.9\text{ cm}$
- **Outer Margins**: Top: $2.5\text{ cm}$ | Bottom: $2.5\text{ cm}$ | Left: $2.5\text{ cm}$ | Right: $2.5\text{ cm}$
- **Column Structure**: 3 balanced vertical columns (Width: $\approx 24.5\text{ cm}$ each; Gutter: $2.0\text{ cm}$)
  - **Column 1**: 
    1. Introduction & Wetland Significance
    2. Study Area (Ankasamudra Reserve & OSAB v1.0 Operational Mask)
    3. Research Objectives
    4. Satellite Data Sources (Sentinel-2 Harmonized L2A)
  - **Column 2**:
    5. Big Data Methodology & Processing Workflow
    6. Mathematical Formulation (NDWI, NDVI, MNDWI, SCL Masking)
    7. Apache PySpark Distributed Processing Pipeline
  - **Column 3**:
    8. Analytical Framework & Planned Results Panels (Strictly labeled as *Planned Analytical Outputs*)
    9. Environmental Conservation & Management Recommendations
    10. References & Institutional Acknowledgments

### 3.2 Typography Hierarchy
- **Poster Title**: 72–78 pt (Bold, Navy Blue `#0f172a` / Deep Teal `#0f766e`, Title Case, High-Contrast)
- **Author & Affiliations**: 28–32 pt (Medium, `#334155`)
- **Section Headings**: 38–44 pt (Bold, Banner style with subtle colored accent bar `#0284c7`, White text or Dark Slate on Light Blue)
- **Subheadings**: 24–28 pt (Semi-bold, `#0369a1`)
- **Body Text**: 20–22 pt (Regular, `#1e293b`, 1.25 line spacing, fully readable from 1.5–2 meters)
- **Captions, Equations & References**: 14–16 pt (`#475569`, consistent IEEE / APA format)

---

## 4. Scientific Content Specifications

### 4.1 Section Texts
- **Introduction**: Wetland ecosystem services, hydrological fluctuations in semi-arid Karnataka, and the need for scalable Big Data remote-sensing analytics.
- **Study Area**: Ankasamudra Bird Conservation Reserve (Vijayanagara District, Sy. No. 203, Ramsar Site No. 2535, $15^\circ07'40''\text{N},\; 76^\circ14'01''\text{E}$). The boundary is explicitly described as the *Operational Study-Area Boundary (OSAB v1.0, 97.8 ha)*.
- **Methodology**: Detailed flow from Copernicus S2_SR_HARMONIZED $\to$ SCL cloud filtering $\to$ spectral indices $\to$ Parquet storage $\to$ PySpark DataFrame temporal aggregation.
- **PySpark Architecture**: Explanation of distributed Spark SQL execution, partitioned columnar reading, and scalable pixel time-series calculation.
- **Results Panels**: Visually structured reserved panels with high-contrast scientific diagrams clearly labeled as:
  > *"Results pending full multi-year satellite-data processing — Planned analytical outputs"*
- **Conservation Recommendations**: Invasive macrophyte management (*Acacia nilotica* / water hyacinth), minimum ecological pool depth maintenance during pre-monsoon, and community-based monitoring.

---

## 5. Printing & Quality Control Standards
- **Vector Preservation**: Native shapes, text boxes, and SVG elements preserved without flattening.
- **Raster Resolution**: 300 DPI for all embedded maps and diagrams.
- **Color Model**: High-contrast, accessibility-tested palette (Slate `#0f172a`, Deep Cyan `#0284c7`, Forest Green `#15803d`, Earthen Gold `#d97706`).
- **Camera-Ready Formats**:
  - `poster/working/LAKE2026_Ankasamudra_Poster_Draft.pptx`
  - `poster/working/LAKE2026_Ankasamudra_Poster_Preview.pdf`
  - `poster/working/LAKE2026_Ankasamudra_Poster_Preview.png`

