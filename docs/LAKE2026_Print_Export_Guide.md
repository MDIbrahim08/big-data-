# LAKE 2026 Poster: High-Resolution Print & PDF Export Guide

This document details the configuration for generating high-fidelity print files (PDF/TIFF) for the **LAKE 2026** presentation.

---

## 1. Poster File Specifications
- **Source File**: `D:\big data\poster\final\LAKE2026_Ankasamudra_Final.html`
- **Aspect Ratio**: **3:4 Portrait** (Standard $36 \times 48\text{ in}$ / $91.44 \times 121.92\text{ cm}$)
- **Target Sizes**:
  - **Standard Symposium Board**: $36 \times 48\text{ inches}$
  - **ISO A0**: $841 \times 1189\text{ mm}$ (Scales proportionally)
  - **ISO A1**: $594 \times 841\text{ mm}$ (Faculty evaluation proofs)
  - **ISO A3 / A4**: Presentation hand-outs

---

## 2. One-Click Browser Export Instructions (Chrome / Edge)

1. Open [`LAKE2026_Ankasamudra_Final.html`](file:///d:/big%20data/poster/final/LAKE2026_Ankasamudra_Final.html) in your browser.
2. Press **`Ctrl + P`** (Print).
3. Set the print dialog options:
   - **Destination**: `Save as PDF` / `Microsoft Print to PDF`
   - **Layout**: `Portrait`
   - **Paper Size**: `Custom` ($36 \times 48\text{ in}$), `A0`, `A1`, or `A3`
   - **Margins**: `None`
   - **Scale**: `100%` (or `Fit to paper`)
   - **Options**:
     - Check **"Background graphics"** (Essential for pastel card tints and background styling)
     - Uncheck **"Headers and footers"** (Removes date/URL stamps)
4. Click **Save** $\rightarrow$ `LAKE2026_Ankasamudra_Final_PrintReady.pdf`.

---

## 3. Print-Optimization Rules in CSS
The stylesheet in `LAKE2026_Ankasamudra_Final.html` includes:
- `-webkit-print-color-adjust: exact !important;` to ensure pastel card tints (`#DCEBFA`, `#E3F0C8`, `#FBE3D0`) retain full saturation.
- `@page { size: 1200px 1600px; margin: 0; }` to eliminate unwanted page splits or margins.
- Resolution-independent SVG vectors for circuit lines, 3D pie charts, performance bars, and curves.
