# 2026 ASA DataQuest: UN World Population Prospects 2024 EDA

Comprehensive exploratory data analysis, data cleaning pipeline, and research questions for the United Nations World Population Prospects (WPP 2024) dataset across 237 countries and areas (1950–2100).

---

## 📁 Repository Structure

```
├── data/
│   ├── WPP2024_Demographic_Indicators_Medium_csv.gz  # Raw UN Medium variant dataset
│   ├── WPP2024_Supplement_Births_and_LE60.csv        # UN Supplement (Births by sex, LE60)
│   ├── WPP2024_Demographic_Indicators_notes.csv      # Codebook & metadata
│   └── clean/                                        # Generated cleaned datasets
│       ├── wpp2024_countries_clean.csv               # 237 countries x 151 years (1950-2100)
│       ├── country_regions.csv                       # Master Region / SubRegion lookup
│       ├── wpp2024_aggregates.csv                    # Separated regional/global aggregates
│       └── pop_2101_lookup.csv                       # Year 2101 population reference
├── eda/
│   ├── EDA_REPORT.md                                 # Full written EDA Report & 10 Research Questions
│   ├── 01_clean_data.py                              # Automated data cleaning pipeline
│   ├── 02_eda_analysis.py                            # Statistical analysis & visualization generator
│   ├── region_mapping.py                             # Alias mapping & UN hierarchy resolution
│   ├── figures/                                      # 20 publication-quality PNG figures (f01-f20)
│   └── tables/                                       # 13 summary CSV/JSON tables & cleaning audits
└── WPP2024_EDA_Deliverables.zip                      # Standalone deliverable bundle (clean data + eda)
```

---

## 🚀 Key Highlights & Findings

1. **Double-Counting Disentangled:**
   - Raw WPP file mixes 237 sovereign nations with 318 aggregate groupings (regional, income, ad-hoc alliances). Naively summing all rows inflated global population to **44.8×** reality.
   - Cleaned panel strictly isolates the **237 countries**, reconciling with UN global totals with $< 3.63 \times 10^{-7}$ error.
2. **Global Turning Points:**
   - Global population peaks at **10.29 billion in 2084**, up from 2.47B (1950) and 8.06B (2023).
   - Africa's share of world population expands from **9.1% (1950) $\rightarrow$ 37.4% (2100)**; Europe contracts from **22.1% $\rightarrow$ 5.8%**.
3. **Sub-Replacement Timing:**
   - In 2023, 130 countries (67.3% of world population) are below replacement ($TFR < 2.1$). By 2100, 224 countries (87.0% of world population) are sub-replacement.
4. **Statistical Break (2023 / 2024):**
   - Estimates (1950–2023) contain stochastic empirical noise ($\text{median } |\Delta LEx| = 0.29$ yr/yr), whereas UN projections (2024–2100) are deterministic and smoothed ($\text{median } |\Delta LEx| = 0.16$ yr/yr, $p < 10^{-120}$).

---

## 📑 Detailed Report & Proposed Research Questions
Read the full analysis and the 10 proposed research questions in [eda/EDA_REPORT.md](eda/EDA_REPORT.md).
