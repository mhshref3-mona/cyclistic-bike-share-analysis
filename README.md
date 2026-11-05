# Cyclistic Bike-Share | Google Data Analytics Capstone

**How do annual members and casual riders use bicycles differently?**

> **Transparency / attribution:** This educational project **reanalyzes published aggregate tables** from an independently authored Cyclistic/Divvy analysis; it is **not** an original processing of the complete individual-trip dataset. The underlying aggregation and exclusions have not been independently verified against the source CSV files. Please read the [methodology and provenance note](documentation/PROVENANCE.md) before interpreting or sharing the results.

[**Read the English case-study report (PDF)**](reports/Cyclistic_Case_Study_EN.pdf) · [Arabic report (PDF)](reports/Cyclistic_Case_Study_AR.pdf) · [Python notebook](notebooks/Cyclistic_Analysis.ipynb)

## Business problem

Cyclistic's marketing team wants to understand how **annual members** and **casual riders** use bike-share differently. These patterns can guide *testable* membership-conversion campaigns. The case asks for a clear business question, source description, cleaning documentation, analysis, visualizations, and three recommendations.

## Key results from the credited published sample

| Measure | Annual members | Casual riders |
| --- | ---: | ---: |
| Trips | 3,482,719 | 1,920,972 |
| Share of trips | 64.5% | 35.5% |
| Average trip duration | 12.7 min | 23.5 min |
| Trips on weekends, within group | 23.3% | 37.2% |
| Trips in June–September, within group | 48.7% | 60.8% |

These are **trip counts, not unique rider counts**. Patterns are consistent with more leisure-oriented casual usage but **do not establish why individual riders behave this way**, nor the probability of converting to annual membership. The third-party source has contradictory start/end-date descriptions; avoid presenting these 12 monthly labels as a independently verified calendar-year series.

## Visualizations

![Trips by rider group](figures/fig1_rider_mix.png)

![Mean trip duration](figures/fig2_duration.png)

![Weekend share](figures/fig5_weekend_share.png)

![Trips by weekday](figures/fig3_weekday_volume.png)

![Monthly ride patterns](figures/fig4_monthly_volume.png)

## Workflow (Ask → Prepare → Process → Analyze → Share → Act)

1. **Ask:** Compare members and casual users in order to propose membership marketing experiments.
2. **Prepare:** Credit the Divvy trip-data owner and the third-party aggregate analysis used for this project.
3. **Process:** Recalculate category totals and shares; verify agreement between published monthly and weekday tables. **No primary trip-level cleaning is claimed.**
4. **Analyze:** Examine trip share, mean ride length, weekend usage, and monthly/weekday patterns.
5. **Share:** Present five plots plus a clearly sourced report.
6. **Act:** Recommend three *controlled tests*, not unverified claims about marketing uplift.

## Three testable business recommendations

- **Weekend conversion messaging:** A/B-test an annual-plan break-even message around high-volume weekends. Use *actual* membership prices, and track incremental paid memberships and net contribution.
- **Seasonal offers:** Test pre-summer sign-up messages with a holdout/control group. Track 30/90-day retention and net incremental margin.
- **Everyday mobility messaging:** Test short-trip convenience and fare-comparison messages without assuming all casual trips are commutes. Measure qualified engagement and confirmed sign-ups.

These are **hypotheses to test**, not measured campaign outcomes.

## Reproduce the aggregate-based calculations

Install Python and dependencies:

```bash
python -m pip install -r requirements.txt
```

Open `notebooks/Cyclistic_Analysis.ipynb` in Jupyter or Kaggle, and **run all cells**. It contains the cited aggregate counts and recomputes selected summaries and plots. The notebook's *optional raw-data pipeline is commented out and has not been executed or validated on 12 months of original trip files*.

The CSV tables in `data/` are **transcriptions of published aggregates**, not original individual-trip extracts. Do not merge them with a single-month raw CSV and represent the result as a 12-month original analysis.

## Project structure

```text
Cyclistic_GitHub_Portfolio/
├── README.md
├── requirements.txt
├── .gitignore
├── documentation/
│   └── PROVENANCE.md
├── reports/
│   ├── Cyclistic_Case_Study_EN.pdf
│   └── Cyclistic_Case_Study_AR.pdf
├── notebooks/
│   └── Cyclistic_Analysis.ipynb
├── figures/
│   └── [5 data figures]
└── data/
    └── [3 published-aggregate CSV tables]
```

## Data source and credit

- **Primary trip-data owner:** [Divvy / Lyft system data](https://divvybikes-marketing.lyft.net/system-data) · [Data License Agreement](https://divvybikes.com/data-license-agreement).
- **Published analytical tables:** Daniel Eniola (2026, March 1), [*Cyclistic Bike-Share Analysis*](https://rstudio-pubs-static.s3.amazonaws.com/1411490_e71e5ba643c44e6ea9333d53b9b1b9e6.html), R Markdown report.
- **Educational task:** Google Data Analytics Professional Certificate, *Cyclistic Case Study 1: How does a bike-share navigate speedy success?*

**Public release note:** Do not upload private data, rider identifiers, or unlicensed raw Divvy datasets. Attribute the prior analyst and preserve the stated uncertainty. For a fully independent portfolio project, repeat the pipeline on a selected and audited 12-month window of official trip CSVs and update the report and notebook accordingly.