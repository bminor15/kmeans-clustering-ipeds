# kmeans-clustering-ipeds

This project applies K-Means clustering to 2023–24 IPEDS data to find data-driven groups of U.S. colleges and universities based on resources, tuition, and student outcomes. The goal is to build a clean, reproducible pipeline that shows how institutions cluster when you focus strictly on measurable indicators instead of preset labels like control or Carnegie type.

The workflow covers:

- pulling and merging multiple IPEDS components  
- cleaning, aligning, and creating per-FTE financial metrics  
- standardizing and Winsorizing variables  
- running K-Means with Elbow and Silhouette checks  
- interpreting the final cluster profiles  
- visualizing results with PCA and diagnostic plots  
- generating a full Quarto report and slide deck

---

## Project Structure

```text
.
├── data/                # Raw IPEDS files
├── docs/                # Rendered HTML report for GitHub Pages
├── index.qmd            # Full capstone report
├── slides.qmd           # Presentation slides
├── literature.qmd       # Literature review page
├── references.bib       # BibTeX references
├── _quarto.yml          # Site configuration
└── README.md
```



Live report:  
**https://bminor15.github.io/kmeans-clustering-ipeds/**

---

## Methods (quick summary)

- Standardized all continuous variables (z-score)
- Winsorized the 1st and 99th percentiles to reduce skew
- Used five features: revenue per FTE, instructional expense per FTE, tuition, completion rate, retention rate
- Ran K-Means with `nstart = 25` and a fixed seed
- Selected \(k = 4\) using the Elbow and Silhouette methods
- Visualized cluster separation with PCA (for interpretation only)

---

## Requirements

Core R packages:

```r
tidyverse
janitor
gt
cluster
corrr
GGally
patchwork
here


