# Protromics-data-analysis: iPOP Study- Patient Z
This project explores proteomics data from the Integrated Personal Omics Profiling (iPOP) study conducted at Stanford University. The iPOP study is a pioneering effort in longitudinal omics profiling aimed at personalizing precision medicine. Here, we focus specifically on Patient Z, analyzing protein abundance patterns during an infection and recovery phase.

## Background
The iPOP study tracks 106 individuals over several years, capturing biological samples at multiple timepoints across states of health and disease. Many participants, including Patient Z, are pre-diabetic, enabling insights into disease progression and immune response. This analysis focuses on proteomics data during a known infection period for Patient Z, helping us understand molecular changes during illness and recovery.

## Dataset
**File:** `abundance.csv`

- **Dimensions:** 950 samples × 302 proteins  
- **Columns:** Protein names  
- **Rows:** Timepoints (named or numerical) when samples were taken  

**Focus Timepoints:**

- `Infection_Early`  
- `Infection_Middle`  
- `Infection_Late`  
- `Infection_Recovery_Early`  
- `Infection_Recovery_Late`  

---

## Methods

### 1. Data Loading & Sanity Check

- Loaded proteomics abundance data using `pandas`.
- Verified most abundant protein in each infection stage sample:
  - **Albumin (ALB)** was the most abundant protein — biologically expected, as it's the most abundant protein in human blood.

---

### 2. Normalization: Relative Abundance

- Scaled each protein’s values between 0 and 1:
  - Subtracted the minimum abundance
  - Divided by the protein’s range (max - min)

```python
relative = (data - data.min()) / (data.max() - data.min())
```

### 3. Visualization: Heatmap

- Plotted a **Seaborn heatmap** for the **first 20 proteins** across the 5 infection-related samples.
- The heatmap visually reveals changes in protein abundance during the infection and recovery timeline.

---

### Observations

- The **infection recovery phase** shows a clear shift in protein abundance profiles.
- **CFD (Complement Factor D)** exhibited:
  - **Low abundance** during the infection.
  - **Increased abundance** during recovery.

>  *Clinical Insight:*  
CFD deficiency is associated with recurrent bacterial infections — this observed pattern aligns with known immune response dynamics during recovery.

## References

Chen, R., et al. (2012). *Personal Omics Profiling Reveals Dynamic Molecular and Medical Phenotypes*. **Cell**, 148(6), 1293–1307. https://doi.org/10.1016/j.cell.2012.02.009


