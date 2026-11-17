# BIG DATA ANALYTICS OF MULTI-YEAR SENTINEL-2 SATELLITE IMAGERY FOR SEASONAL SURFACE-WATER MONITORING AT ANKASAMUDRA BIRD CONSERVATION RESERVE, KARNATAKA

**Mohammed Ibrahim**  
*School of Engineering, Chanakya University, Bengaluru, Karnataka, India*  
*Programme: BCA (Honours) — Data Science*  
*In association with: Energy and Wetlands Research Group (EWRG), Centre for Ecological Sciences (CES), Indian Institute of Science (IISc), Bangalore*  
**Paper / Track ID:** `LAKE2026-BD04`  
**Symposium:** LAKE 2026 — 15th Biennial Lake Symposium (18–20 November 2026)

---

## ABSTRACT

Semi-arid village irrigation tanks (*keres*) in peninsular India serve as vital micro-refugia for migratory waterbirds but undergo extreme intra-annual hydrological drawdowns from summer drying to sudden monsoon inundation. Standard satellite remote sensing assessments frequently rely on single-snapshot, annual acquisitions that fail to capture these rapid non-linear hydrological dynamics. Furthermore, processing multi-temporal, multi-spectral satellite imagery at 10-meter spatial resolution introduces severe out-of-memory (OOM) compute bottlenecks when using conventional single-node geospatial libraries. 

In this investigation, we engineer a cloud-native Big Data analytics framework leveraging **Apache PySpark** and the European Space Agency’s (ESA) **Copernicus Sentinel-2 Multi-Spectral Instrument (MSI) Level-2A** archive across 2018–2025 at **Ankasamudra Bird Conservation Reserve** (Ramsar Site No. 2535, Vijayanagara district, Karnataka). We establish a rigorous **Operational Study-Area Boundary (OSAB v1.0, 97.82 ha)** buffered by >900 meters from adjacent Tungabhadra river backwaters. Radiometric bands B3 (Green, 560 nm), B4 (Red, 665 nm), B8 (NIR, 842 nm), and B11 (SWIR, 1610 nm) are ingested and partitioned into columnar **Apache Parquet** datasets. Distributed MapReduce and window operations compute multi-spectral indices—Normalized Difference Water Index (NDWI), Modified NDWI (MNDWI), and Normalized Difference Vegetation Index (NDVI)—across over 1.2 million pixel records. 

Benchmarking demonstrates that distributed PySpark execution achieves a **13.38× speedup (8.4 s vs. 112.4 s)** over conventional single-threaded Pandas execution. The derived multi-year hydroperiod models reveal that preserving a **minimum baseline pool depth (>20.0 ha)** during the critical pre-monsoon summer window (March–May) through scheduled Tungabhadra lift canal feeder releases is essential to avert catastrophic breeding colony abandonment.

**Keywords:** Big Data, Apache PySpark, Sentinel-2, Wetland Hydrology, Remote Sensing, Ankasamudra Reserve, Ramsar Site 2535, Seasonal Inundation.

---

## 1. INTRODUCTION

Wetlands in semi-arid southern India are predominantly human-engineered tank cascade systems (*keres*) constructed over centuries to capture monsoon precipitation for irrigation and domestic consumption. Over decades, select tanks featuring dense stands of *Acacia nilotica* (Babool) and emergent macrophytes have evolved into critical biodiversity hotspots, supporting over 210 vascular plant species and dense breeding populations of colonial waterbirds, including Painted Storks (*Mycteria leucocephala*), Spot-billed Pelicans (*Pelecanus philippensis*), and Oriental Darters (*Anhinga melanogaster*).

**Ankasamudra Bird Conservation Reserve** (Survey No. 203, Hagaribommanahalli taluk, Vijayanagara district, Karnataka; Ramsar Site No. 2535, gazetted extent 98.76 ha) represents the first bird conservation reserve established in the Hyderabad-Karnataka region. However, its ecological integrity faces persistent threats:
1. **Intense Hydroperiod Drawdown:** The tank undergoes extreme pre-monsoon seasonal drying followed by sudden monsoon filling, leading to volatile water-depth profiles.
2. **Computational Scale Bottleneck:** Monitoring this rapid cadence requires dense time-series observation. At 10m spatial resolution across 8 multi-spectral bands over 8 years (2018–2025), traditional single-node GIS software (ArcGIS, QGIS, or standard Python/Pandas) encounters out-of-memory (OOM) failures when performing multi-temporal aggregations.
3. **Data Contamination:** Because the wetland lies in close proximity to the Tungabhadra river backwaters, inaccurate spatial boundary definitions risk misidentifying river water as wetland storage.

To resolve these challenges, this study formulates an end-to-end distributed Big Data analytics workflow coupling **Apache PySpark** with **Sentinel-2 MSI Level-2A** time-series data to deliver automated, reproducible, and scalable seasonal waterbody monitoring.

---

## 2. STUDY AREA & DATASET SPECIFICATIONS

### 2.1 Cadastral vs. Operational Study-Area Boundary (OSAB v1.0)
The official gazetted extent of Ankasamudra Bird Conservation Reserve is 98.76 hectares. To guarantee spatial rigour and eliminate hydrological contamination from the high-water backflows of the Tungabhadra Dam, an **Operational Study-Area Boundary (OSAB v1.0)** was established:
- **Spatial Area:** **97.82 hectares**
- **Buffer Rigour:** Preserves a strict **>900m exclusion buffer** between the wetland tank bund and Tungabhadra river backwaters.

### 2.2 Earth Observation Satellite Data
We utilize the Copernicus Sentinel-2 Multi-Spectral Instrument (MSI) Level-2A Bottom-Of-Atmosphere (BOA) surface reflectance product:
- **Spatial Resolution:** 10 meters (Bands B3, B4, B8) and 20 meters resampled to 10 meters (Band B11).
- **Temporal Window:** 2018 to 2025 (8 complete hydrologic cycles).
- **Temporal Cadence:** 5-day constellation revisit frequency.
- **Scene Classification (SCL):** Automated bitmask filtering applied to eliminate cloud cover, cirrus, and shadow contamination.

---

## 3. BIG DATA METHODOLOGY & DISTRIBUTED ARCHITECTURE

```
[Raw Sentinel-2 MSI L2A Granules] 
            │
            ▼
[SCL Scene Cloud / Shadow Filtering] 
            │
            ▼
[OSAB v1.0 Cadastral Spatial Clipping (97.82 ha)] 
            │
            ▼
[Apache PySpark Cluster Ingestion (Resilient Distributed Datasets)]
            │
            ▼
[Columnar Parquet Storage (Partitioned by Year / Season)]
            │
            ├──> NDWI  = (B3 - B8) / (B3 + B8)
            ├──> MNDWI = (B3 - B11) / (B3 + B11)
            └──> NDVI  = (B8 - B4) / (B8 + B4)
            │
            ▼
[Distributed MapReduce Seasonal Aggregations]
            │
            ▼
[Hydroperiod Profiles & Conservation Water-Depth Policy]
```

### 3.1 Spectral Mathematical Formulations
The PySpark engine computes three standardized spectral indices across every partitioned pixel record:

1. **Normalized Difference Water Index (NDWI)**:
   $$\text{NDWI} = \frac{\text{B3 (Green, 560nm)} - \text{B8 (NIR, 842nm)}}{\text{B3 (Green, 560nm)} + \text{B8 (NIR, 842nm)}}$$
   *Highlights open waterbodies by exploiting the high reflectance of water in green wavelengths and high absorption in near-infrared.*

2. **Modified Normalized Difference Water Index (MNDWI)**:
   $$\text{MNDWI} = \frac{\text{B3 (Green, 560nm)} - \text{B11 (SWIR, 1610nm)}}{\text{B3 (Green, 560nm)} + \text{B11 (SWIR, 1610nm)}}$$
   *Suppresses false water classifications caused by fringing moist soils, mudflats, and built infrastructure.*

3. **Normalized Difference Vegetation Index (NDVI)**:
   $$\text{NDVI} = \frac{\text{B8 (NIR, 842nm)} - \text{B4 (Red, 665nm)}}{\text{B8 (NIR, 842nm)} + \text{B4 (Red, 665nm)}}$$
   *Quantifies emergent *Acacia nilotica* macrophyte canopy vigor and detects invasive floating weed proliferation.*

### 3.2 Distributed PySpark Optimization
Rather than reading individual scenes in single memory, the raw rasters are flattened into columnar DataFrames stored in **Apache Parquet** format, partitioned by `Year` and `Season`. Spark’s Catalyst Optimizer and Tungsten execution engine leverage multi-core CPU SIMD vectorization to execute in-memory map and reduce functions across partitions without disk I/O thrashing.

---

## 4. RESULTS & PERFORMANCE BENCHMARKING

### 4.1 Computational Execution Benchmarking
We benchmarked the pipeline across 1.2 million multi-spectral pixel arrays to evaluate computational latency:

| Execution Framework | Latency | Speedup | Computational Note |
| :--- | :---: | :---: | :--- |
| **Single-Node Pandas (1 Core)** | 112.4 s | 1.00× (Baseline) | High memory consumption, vulnerable to OOM crashes. |
| **PySpark Local (4 Cores)** | 42.1 s | 2.67× | Multi-core parallel RDD partition processing. |
| **PySpark Cluster Mode (SIMD + Parquet)** | **8.4 s** | **13.38×** | In-memory distributed vectorized execution. |

### 4.2 Habitat Biome Composition
Within the 97.82-hectare boundary, multi-year cross-classification partitions the wetland into three dominant ecological zones:
- **Open Water Surface:** 48% (~46.95 ha during median post-monsoon storage).
- ***Acacia nilotica* Nesting Canopy & Macrophytes:** 36% (~35.21 ha).
- **Fringing Mudflats, Bund & Silt Margins:** 16% (~15.65 ha).

---

## 5. ECOLOGICAL IMPLICATIONS & CONSERVATION POLICY

1. **Critical Summer Pool Threshold (>20.0 ha):**  
   Time-series inundation curves reveal that pre-monsoon drying frequently drops water coverage below 10 hectares, triggering premature nesting abandonment by pelicans and storks. The pipeline establishes that maintaining an absolute minimum baseline pool depth of **>20.0 hectares** during March–May is mandatory for colony survival.
2. **Actionable Water Replenishment Guidance:**  
   The reserve's proximity to the Tungabhadra Left Bank / High-Level lift canal system allows forest managers to schedule controlled canal releases into the tank before water surface area breaches the 20-hectare danger threshold.
3. **Canopy Preservation vs. Weed Control:**  
   *Acacia nilotica* crowns provide essential nesting platforms; however, high NDVI anomalies on open water surfaces indicate invasive water hyacinth (*Eichhornia crassipes*) infestations that require systematic desilting and physical harvesting.

---

## 6. CONCLUSION

This investigation successfully demonstrates that integrating **Apache PySpark** with **Sentinel-2 Multi-Spectral satellite imagery** provides a robust, scalable, and reproducible solution for monitoring seasonal wetland dynamics at Ankasamudra Bird Conservation Reserve. By eliminating traditional memory constraints and delivering rapid time-series execution (13.38× speedup), Big Data frameworks empower conservation authorities with actionable, quantifiable metrics to safeguard vulnerable semi-arid Ramsar wetlands.

---

## REFERENCES

1. Ramsar Information Sheet (RIS): *Ankasamudra Bird Conservation Reserve (Site No. 2535)*, Ramsar Convention Secretariat, Gland, Switzerland, 2024. [https://rsis.ramsar.org/ris/2535](https://rsis.ramsar.org/ris/2535)
2. McFeeters, S. K. (1996). *The use of the Normalized Difference Water Index (NDWI) in the delineation of open water features.* International Journal of Remote Sensing, 17(7), 1425–1432.
3. Xu, H. (2006). *Modification of normalised difference water index (NDWI) to enhance open water features in remotely sensed imagery.* International Journal of Remote Sensing, 27(14), 3025–3033.
4. Rouse, J. W., Haas, R. H., Schell, J. A., & Deering, D. W. (1974). *Monitoring the vernal advancement and retrogradation of natural vegetation.* NASA/GSFC Final Report.
5. European Space Agency (ESA): *Sentinel-2 User Handbook (Issue 1.2)*, ESA Standard Document, 2015.
6. Zaharia, M., et al. (2016). *Apache Spark: A unified engine for big data processing.* Communications of the ACM, 59(11), 56–65.
7. Mendeley Data: *Floristic Inventory of Ankasamudra Bird Conservation Reserve (210+ Vascular Plant Species)*, doi:10.17632/8jd5zsf8m9.1.
