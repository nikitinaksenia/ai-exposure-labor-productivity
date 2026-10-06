# The Effect of Artificial Intelligence Exposure on Labor Productivity

**Kseniia Nikitina** · M.A. in Economics, New York University · 2026

📄 **[Read the paper (PDF)](Nikitina-AI-Exposure-Labor-Productivity.pdf)**

## Abstract

Does exposure to artificial intelligence raise labor productivity? I study 59 U.S. industries from
1997 to 2024, combining a time-varying measure of industry exposure to AI, built from occupational
ability scores and annual employment shares, with an economy-wide index of AI capability. In two-way
fixed-effects regressions, neither early-stage (2016–2019) nor generative-AI-era (2020–2024) exposure
has a statistically significant effect on labor productivity. The preferred estimate for the
generative-AI era is 0.023 (standard error 0.364), and the confidence intervals include both sizable
gains and sizable losses. Because most of the identifying variation comes from 2022–2024, the results
show that any productivity effect of generative AI was not yet detectable in industry data through
2024, not that no effect exists. Significant positive estimates appear only in specifications without
year fixed effects or with a lagged dependent variable, which I argue are not credible.

## Code

The analysis is written in R Markdown. Run the files in order from inside the `Code` folder; each
reads from and writes to `../Data/`.

| File | What it does |
|---|---|
| `1 Build employment panel.Rmd` | Builds an industry × occupation employment panel from BLS OEWS files |
| `2 AIOE and 2020 AIIE.Rmd` | Constructs the AI Occupational Exposure (AIOE) and AI Industry Exposure (AIIE) measures, including the language-modeling variant |
| `3 Merge Employment with AIIE panel.Rmd` | Combines employment shares with exposure scores into a time-varying AIIE panel |
| `4 Final Panel Merge.Rmd` | Merges productivity (KLEMS), capital and energy controls, and work-from-home measures into the final panel |
| `5 Final Model code.Rmd` | Estimates pooled OLS, first-difference, and one- and two-way fixed-effects models, with diagnostic tests |

**R packages:** tidyverse, readxl, haven, janitor, fixest, plm, lmtest, sandwich, car, broom,
modelsummary, kableExtra, ggplot2, ggrepel, scales.

## Data

All inputs come from public sources. The scripts expect this layout:

```
Data/
├── Source data/
│   ├── Employment source files/           BLS Occupational Employment and Wage Statistics (OEWS)
│   ├── AIOE and AIIE source files/        Felten, Raj & Seamans (2021) AI exposure files
│   ├── major-industry-total-factor-productivity-klems.xlsx   BLS/BEA KLEMS productivity
│   ├── Controls_Panel_1997_2022.xlsx      ICT, non-ICT capital and energy contributions
│   └── occupations_workathome.csv         Dingel & Neiman work-from-home classification
├── Intermediate data/                     created by scripts 1–4
└── Final Data Set/
    └── panel_mergedfinal.csv              used by script 5
```

## Citation

Nikitina, Kseniia. 2026. "The Effect of Artificial Intelligence Exposure on Labor Productivity."
Working paper, New York University.
