# Provenance, scope, and reproducibility

This portfolio project **reanalyzes published monthly and weekday aggregate counts** from Daniel Eniola's [Cyclistic analysis](https://rstudio-pubs-static.s3.amazonaws.com/1411490_e71e5ba643c44e6ea9333d53b9b1b9e6.html), published March 1, 2026. It does **not** claim independent processing of all individual trips.

The source reports 5,552,092 raw trips and excludes 148,401 rides shorter than one minute, leaving 5,403,691. These cleaning decisions were made and reported by the source analyst and were **not independently audited** here.

The source's prose and listed data files disagree about exact coverage dates. Consequently, the figures are described as **12 labeled months** without claiming a verified year window.

A trip is not a unique person. Journey counts cannot measure conversion, retention, motivations, or individual economics. Reported mean journey durations may be sensitive to outliers.

## Validation needed before claiming an independent original study
1. Obtain 12 contiguous monthly CSVs directly from [Divvy](https://divvybikes-marketing.lyft.net/system-data) and keep checksums.
2. Validate ride identifiers, dates, durations, missingness, and schema changes.
3. Document exclusions and compare means with medians.
4. Reproduce monthly/weekday summaries, graphics and recommendations.
5. Credit the data license: https://divvybikes.com/data-license-agreement

## Attribution
- Daniel Eniola (2026), *Cyclistic Bike-Share Analysis*, https://rstudio-pubs-static.s3.amazonaws.com/1411490_e71e5ba643c44e6ea9333d53b9b1b9e6.html
- Google Data Analytics Professional Certificate: Cyclistic Case Study 1.
