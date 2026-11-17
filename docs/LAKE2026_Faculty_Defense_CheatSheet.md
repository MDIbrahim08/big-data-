# LAKE 2026 — Faculty / Guide Conversation Defense Sheet
## Big Data Satellite Analytics at Ankasamudra Bird Conservation Reserve

**Date for Guide Conversation:** November 17, 2026  
**Candidate:** Mohammed Ibrahim | BCA (Honours) — Data Science, Chanakya University  
**Symposium Track:** `LAKE2026-BD04` (Big Data & Wetland Hydrology)

---

### Q1: "What is your original research contribution versus existing studies?"
> **Answer:**  
> *"Existing studies on Ankasamudra (such as floristic surveys and the Ramsar 2535 documentation) provide static biological catalogs and single-date manual GIS boundaries. They cannot monitor rapid seasonal water drawdown.  
> **My original contribution is developing a distributed Big Data analytics pipeline using Apache PySpark and Sentinel-2 Multi-Spectral satellite imagery (2018–2025).** I defined the strict 97.82-hectare Operational Study-Area Boundary (OSAB v1.0) with a >900m buffer from Tungabhadra backwaters, eliminated out-of-memory crashes on multi-year 10m rasters, and derived an empirical minimum pool depth threshold (>20.0 ha) needed to prevent summer breeding colony abandonment."*

---

### Q2: "Why did you use Apache PySpark instead of standard Python (Pandas/GeoPandas)?"
> **Answer:**  
> *"Each Sentinel-2 scene over Ankasamudra contains multi-spectral bands at 10m ground resolution. When analyzing 8 years of 5-day revisit data (over 1.2 million multi-spectral pixel arrays), single-node Pandas loads everything into contiguous memory, resulting in Out-Of-Memory (OOM) failures or massive slowdowns.  
> **PySpark solves this by distributing pixel arrays across in-memory partitions and executing columnar Parquet MapReduce operations.** As shown in our benchmarks, PySpark achieves a **13.38× speedup (8.4 seconds vs. 112.4 seconds)**, allowing near real-time seasonal hydroperiod profiling."*

---

### Q3: "Explain the formulas you used and why you chose them."
> **Answer:**  
> 1. **NDWI** $= \frac{\text{B3 (Green)} - \text{B8 (NIR)}}{\text{B3 (Green)} + \text{B8 (NIR)}}$: Delineates open surface water by exploiting high water absorption in the near-infrared band.  
> 2. **MNDWI** $= \frac{\text{B3 (Green)} - \text{B11 (SWIR)}}{\text{B3 (Green)} + \text{B11 (SWIR)}}$: Substitutes NIR with Shortwave Infrared to suppress noise from moist mudflats, sand, and bunds.  
> 3. **NDVI** $= \frac{\text{B8 (NIR)} - \text{B4 (Red)}}{\text{B8 (NIR)} + \text{B4 (Red)}}$: Tracks the seasonal canopy density of *Acacia nilotica* nesting trees and flags invasive aquatic weeds like water hyacinth.

---

### Q4: "What is the practical conservation takeaway of your project?"
> **Answer:**  
> *"The data reveals that Ankasamudra's waterbody drops to critical levels during the pre-monsoon summer months (March–May), threatening colonial nesting birds like Painted Storks and Spot-billed Pelicans.  
> **Our policy recommendation is establishing an active baseline water threshold of at least 20.0 hectares.** Because the reserve is close to the Tungabhadra lift canal system, the Karnataka Forest Department and Irrigation authorities can use our automated satellite metrics to schedule timely canal water releases before the tank dries out."*

---

### Deliverables Checklist for November 17th:
- [x] **Poster PDF Ready:** `D:\big data\poster\final\LAKE2026_BD04_Mohammed_Ibrahim_Ankasamudra_Poster.pdf`
- [x] **Working PySpark Engine:** `D:\big data\ankasamudra_spark_pipeline.py`
- [x] **Interactive Jupyter Notebook:** `D:\big data\notebooks\Ankasamudra_BigData_Analysis.ipynb`
- [x] **Full Research Paper Draft:** `C:\Users\ISHAQ\.gemini\antigravity\brain\...\LAKE2026_Ankasamudra_Research_Paper_Draft.md`
- [x] **Viva Defense Sheet:** This document.
