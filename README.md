# Formula 1 PySpark Pipeline Coursework Variant

A collaborative data engineering notebook that prepares Formula 1 pit stop records and links them with race disruption context. This repository and its closely related pipeline companion preserve variants of the same coursework workflow; they should not be counted as independent business deployments.

## The question

How can inconsistent race, circuit and driver fields be standardised so pit stop data can be joined with relevant safety car context?

## Tools and methods

Python, PySpark, Spark SQL, Data cleaning, Data integration, ETL.

## Work in this repository

1. Normalised names and parsed pit and stint information into structured fields.
2. Aggregated pit stop context and constructed join keys for race and circuit matching.
3. Filtered overlapping seasons from 2018 to 2024 and exported Spark CSV output directories.
4. Recorded output row counts and the number of rows with a matched safety car cause.

## Evidence and scope

| Measure | Recorded value |
| --- | --- |
| Seasons used | 2018 to 2024 |
| Rows in the recorded final output | 3,381 |
| Output rows with a matched safety car cause | 1,940 |

## Repository guide

| File or folder | Purpose |
| --- | --- |
| [Data_Pipeline.ipynb](https://github.com/divyansh2703/Cloud_Computing_Data_Pipeline/blob/main/Data_Pipeline.ipynb) | Pipeline implementation and recorded output |
| [data/processed/final_pitstop_analysis_data.csv](https://github.com/divyansh2703/Cloud_Computing_Data_Pipeline/tree/main/data/processed/final_pitstop_analysis_data.csv) | Spark output directory |
| [data/processed/pitstop_aggregated](https://github.com/divyansh2703/Cloud_Computing_Data_Pipeline/tree/main/data/processed/pitstop_aggregated) | Aggregated intermediate output |

## Getting started

Open `Data_Pipeline.ipynb` in a Jupyter environment with PySpark and a compatible Java runtime. Review the `RAW_DIR`, `OUT_DIR` and source filename settings. The notebook expects inputs under `data/raw/` and writes partitioned outputs under `data/processed/`. A directory whose name ends in `.csv` is a Spark output directory, not necessarily a single CSV file.

Run cells in a reviewed order. The notebook includes intermediate join investigations, so a clean execution should verify row grain and key uniqueness before accepting the exported table.

## Current limitations

1. The 1,940 value counts matched output rows. It is not a count of distinct safety car deployments.
2. Recorded Spark outputs do not establish a cloud deployment, scheduled production service or a measured speedup.
3. Name mapping and join cardinality need validation before the data is used for modelling.
4. The closely related pipeline repositories overlap and should be presented as one project on LinkedIn unless their separate contributions are explained.

## Next steps

1. Consolidate overlapping pipeline variants and publish a single reproducible entry point.
2. Validate event matching at the correct race and lap grain.

## Authors and reuse

Divyansh Doshi and Amisha Sanjay Kadukar.

Documentation reviewed against the public repository on 7 September 2026. Counts are taken from the named saved artifacts or directly inspected CSVs; this review did not rerun model training or validate a complete deployment. No source code licence was found in the reviewed project tree. Data and third party material may have separate terms.
