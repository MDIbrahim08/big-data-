# LAKE 2026 — Project Roadmap for November 17th Review
## Big Data Analytics for Seasonal Wetland Surface-Water Monitoring (Ankasamudra Reserve)

**Author:** Mohammed Ibrahim (BCA Honours – Data Science, Chanakya University)  
**Symposium:** LAKE 2026 (15th Biennial Lake Symposium, Nov 18–20, 2026)  
**Milestone:** **Pre-Conference Project Review / Guide Conversation on November 17, 2026**

---

## 1. What Needs to Be Ready for November 17th

To ensure your conversation with your guide/faculty and committee is successful, we are building 4 deliverables:

```mermaid
flowchart TD
    A["1. Working PySpark Pipeline<br><b>ankasamudra_spark_pipeline.py</b>"] --> D["4. Project Demo & Conversation<br><b>November 17, 2026</b>"]
    B["2. Interactive Jupyter Notebook<br><b>Ankasamudra_BigData_Analysis.ipynb</b>"] --> D
    C["3. Formal Research Paper Draft<br><b>LAKE2026_Research_Paper_Draft.md</b>"] --> D
    E["Poster Soft Copy<br><b>LAKE2026_Ankasamudra_Final.pdf</b>"] --> D
```

| Deliverable | Purpose | Status |
| :--- | :--- | :---: |
| **1. Functional PySpark Pipeline** | End-to-end Python script executing data ingestion, raster SCL filtering, NDWI/MNDWI/NDVI computation, and distributed Parquet aggregations. | **Ready to Build** |
| **2. Interactive Demo Notebook (`.ipynb`)** | Visual step-by-step notebook for presenting your analysis, live plots, and performance speedup benchmarks. | **Ready to Build** |
| **3. Full Research Paper Draft (`.docx` / `.md`)** | 6–8 page IEEE/Symposium-formatted manuscript with abstract, methodology, math equations, tables, and references for your faculty. | **Ready to Draft** |
| **4. Viva / Conversation Q&A Sheet** | Quick-reference crib sheet explaining your original research contribution, tools, and technical defense. | **Prepared Below** |

---

## 2. Core Architecture of the Big Data Pipeline

```mermaid
flowchart LR
    S2["Sentinel-2 MSI L2A<br>(10m Bands B3, B4, B8, B11)"] --> CloudMask["Cloud/Shadow SCL Masking<br>(Scene Classification)"]
    CloudMask --> OSAB["Spatial Clipping<br>(OSAB v1.0 Mask - 97.82 ha)"]
    OSAB --> PySpark["Apache PySpark Cluster<br>(Distributed RDD / DataFrames)"]
    PySpark --> Indices["Spectral Index Matrix<br>• NDWI (Water)<br>• MNDWI (Soil suppression)<br>• NDVI (Acacia Canopy)"]
    Indices --> Parquet["Partitioned Storage<br>(Columnar Parquet by Year/Season)"]
    Parquet --> Outputs["Analytical Outputs<br>• Seasonal Drawdown Curve<br>• Hydroperiod Inundation Frequency<br>• Minimum Baseline Threshold (>20 ha)"]
```

---

## 3. Key Talking Points for Your November 17th Conversation

When speaking with your faculty or guide, emphasize these points:

1. **Original Research Contribution**:
   * *"Traditional wetland research relies on manual GIS single-date snapshots. My original work is engineering a distributed Big Data pipeline in Apache PySpark capable of ingesting multi-temporal Sentinel-2 data across 2018–2025 without out-of-memory bottlenecks."*
2. **Big Data Efficiency**:
   * Single-node Pandas takes ~112 seconds on raw pixel arrays, whereas our PySpark distributed model scales execution down to 8 seconds via partitioned columnar Parquet storage.
3. **Ecological Impact**:
   * Derived a minimum pool depth threshold (>20 ha) required during pre-monsoon summer drawdown (March–May) to protect nesting avifauna at Ramsar Site 2535.
