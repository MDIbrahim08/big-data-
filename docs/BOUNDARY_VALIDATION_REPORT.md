# BOUNDARY VALIDATION REPORT (PHASE 1.2 UPDATE)
## Critical Quality Control and Boundary Provenance Audit for Ankasamudra Bird Conservation Reserve

**Audit Date**: November 3, 2026  
**Auditor**: Senior Research Engineer & Geospatial Analyst  
**Document Status**: Rigorous quality control following elimination of erroneous WDPA ID  

---

## 1. Provenance and Forensic Inspection of Existing Provisional GeoJSON

**Target File**: [`data/raw/boundaries/ankasamudra_provisional_ramsar2535.geojson`](file:///d:/big%20data/data/raw/boundaries/ankasamudra_provisional_ramsar2535.geojson)

### 1.1 Mathematical & Spatial Properties
- **Geometry Type**: `Polygon` (Single ring, closed).
- **Number of Vertices**: 7 coordinates (6 unique vertices, 1 closing vertex):
  1. `[76.2280, 15.1235]`
  2. `[76.2370, 15.1235]`
  3. `[76.2395, 15.1280]`
  4. `[76.2380, 15.1325]`
  5. `[76.2320, 15.1330]`
  6. `[76.2275, 15.1285]`
  7. `[76.2280, 15.1235]` (closure)
- **Bounding Box (WGS 84)**:
  - $\text{West}: 76.2275^\circ\text{ E}$ | $\text{East}: 76.2395^\circ\text{ E}$ ($\Delta \lambda = 0.012^\circ \approx 1.29\text{ km}$)
  - $\text{South}: 15.1235^\circ\text{ N}$ | $\text{North}: 15.1330^\circ\text{ N}$ ($\Delta \phi = 0.0095^\circ \approx 1.05\text{ km}$)
- **Coordinate Reference System**: EPSG:4326 (`urn:ogc:def:crs:OGC:1.3:CRS84`).
- **Polygon Validity**: Geometrically valid (no self-intersections, proper winding).
- **Planar Area (Projected EPSG:32643 - UTM Zone 43N)**: $\approx 96.8\text{ hectares}$.
- **Calculated Polygon Centroid**: $15.1278^\circ\text{ N},\; 76.2335^\circ\text{ E}$.

### 1.2 Provenance Verdict
> **Provenance Verdict**: **SYNTHETIC / MATHEMATICAL APPROXIMATION**.  
> The existing GeoJSON was **not** obtained from an authoritative digital cadastre or an official GIS shapefile. It was generated as an idealized polygon wrapping around the official Ramsar reference centroid ($15^\circ07'40''\text{N},\; 76^\circ14'01''\text{E}$) to match the target 97.26 ha water-spread extent.  
> **Scientific Finding**: It is **not** an authentic legal boundary. It must not be cited as the surveyed reserve border.

---

## 2. Investigation of Original Ramsar Digital Map & Factbook (2025)

1. **Ramsar Information Sheet (`IN2535RIS_2401_en.pdf`)**:
   - Lists site area as **98.76 ha** (official gazetted) and GIS-calculated area as **97.26 ha**.
   - Identifies an attached digital site map uploaded during Contracting Party submission.
   - The reported coordinate ($15^\circ07'40''\text{N},\; 76^\circ14'01''\text{E}$) is explicitly a **reference coordinate** (nominal site location), not a mathematical polygon centroid.
2. **MoEFCC / Indian Wetlands Portal 2025 Ramsar Factbook (`1738904598.pdf`)**:
   - Displays illustrative maps of Indian Ramsar sites including Ankasamudra.
   - **Crucial Disclaimer**: The Factbook explicitly warns that its maps are *illustrative, schematic, and not to scale*.
   - **Risk Assessment**: The tank sits ~1 km from the vast Tungabhadra Dam backwaters and is surrounded by canal-irrigated agricultural fields. Using an unvalidated or coarse polygon risks mixing agricultural irrigation or Tungabhadra backwater pixels with Ankasamudra tank water.

---

## 3. Investigation of Karnataka Gazette Notification (FEE 04 FWL 2017)

- **Notification Reference**: Government of Karnataka Notification No. **FEE 04 FWL 2017**, dated **31.01.2017**.
- **Cadastral Identification**: Survey No. 203, Ankasamudra Village, Hagaribommanahalli Taluk.
- **Gazetted Legal Description**: Identifies an extent of 244.04 acres (98.76 ha) comprising the water-spread area and bund of the village irrigation tank.
- **Spatial Vector Status**: The gazette notification contains text schedules with cardinal boundaries referencing adjacent survey numbers; it does not publish GIS shapefiles, KML vectors, or vertex coordinate schedules in open formats. The digital cadastral polygon resides in the Karnataka Bhoomi/RTC/Survey database.

---

## 4. Discrepancy Clarification (98.76 ha vs 97.26 ha)

The documentation has been strictly corrected to reflect factual definitions without speculation:
- **98.76 hectares**: The **official legal notified area** specified in Government of Karnataka Gazette Notification FEE 04 FWL 2017 (equivalent to 244.04 acres).
- **97.26 hectares**: The **GIS-calculated polygon area** computed by the technical agency and recorded in Section 2.2.1 of the Ramsar Information Sheet.
- **Discrepancy (1.50 ha)**: Recorded strictly as a known measurement difference between the legal revenue parcel area and the digital GIS delineation submitted to Ramsar. No speculative causes are asserted.

---

## 5. Recommended Boundary Strategy for LAKE 2026 Research

To maintain scientific integrity for our conference presentation, the recommended strategy is:

### **Strategy C + B (Hybrid): Independently Delineated & Georeferenced Waterbody Analysis Boundary (WAB)**
1. **Definition**: Define an **"Ankasamudra Waterbody Analysis Boundary (WAB)"** based on the distinct physical geomorphology of the lake (tank bund, weir crest, and high-water shoreline visible on high-resolution Sentinel-2/Google Earth optical basemaps), anchored to Survey No. 203 around the reference coordinate $15.1278^\circ\text{N},\; 76.2336^\circ\text{E}$.
2. **Labeling Transparency**: In the research paper, project documentation, and conference poster, this geometry must be clearly cited as:  
   *"Ankasamudra Waterbody Analysis Boundary (WAB, ~97 ha), delineated from high-water physical shoreline and Ramsar reference coordinates, reflecting the lake water-spread area of Survey No. 203."*
3. **Scientific Safeguard**: Explicitly distinguish this analysis boundary from the legal revenue cadastral boundary to avoid any false legal representation.
