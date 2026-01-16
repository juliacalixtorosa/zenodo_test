# Refactoring Cortext Platform

Cortext was launched in 2008 by researchers in Science and Technology Studies. It provides computational methods for document analysis in the humanities and social sciences, serving over a thousand users across 50 countries each year, with roughly 44,000 analyses, most of which are carried out through the Cortext Manager application.

This package gathers the raw data from the analysis and metric collection before and after the refactoring of the Corpus Explorer method of the Cortext platform. This method is responsible for filtering database tables selected by users and generating visualizations of the filtered content.

## 1. Overview

This replication package contains all artifacts required to reproduce the quantitative results presented in the paper, derived from a case study on the refactoring of the **Corpus Explorer** method of the **Cortext Manager** platform.

Corpus Explorer is responsible for filtering database tables selected by users and generating visualizations of the filtered content.

The study evaluates the impact of systematic refactoring on **cyclomatic complexity**, **Halstead metrics**, **size metrics (LOC/SLOC/LLOC)**, and the **maintainability index**, comparing the system state **before and after** the refactoring process.

All data, reports, figures, and execution logs included here were generated through **controlled and documented automation**, following best practices in Software Engineering.


## 2. Package Contents

This replication package is organized as follows:

```
├── data.zip
├── reports.zip
├── figures.zip
├── RUN
├── corpus_explorer_refactoring.ods
└── README.md
```

## 2.1 `data.zip` — Raw Metrics

Contains the raw static analysis outputs collected with the [**Radon**](https://radon.readthedocs.io/en/latest/#) tool for both versions of the method, including:

- Cyclomatic Complexity  
- Halstead metrics  
- Maintainability Index  
- Raw size metrics (LOC, LLOC, SLOC)

The data correspond to two checkpoints:

| Label  | Commit hash | Python | Target path |
|-------|-------------|--------|-------------|
| before | [be0718bb3345c9d741f25273e013d372118dd637](https://gitlab.com/cortext/cortext-methods/corpus-explorer/-/commit/be0718bb3345c9d741f25273e013d372118dd637) | Python 2 | corpus_explorer |
| after  | [add1cfa62bb5a868fd29ee8979e39af0aa13e61d](https://gitlab.com/cortext/cortext-methods/corpus-explorer/-/commit/add1cfa62bb5a868fd29ee8979e39af0aa13e61d) | Python 3 | corpus_explorer |


## 2.2 `reports.zip` — Aggregated Results

Contains consolidated and comparative analyses derived from the raw metrics, including:

- aggregated metric values per checkpoint  
- before/after comparisons  
- textual summaries used to support the discussion presented in the paper


## 2.3 `figures.zip` — Visualizations

Contains all comparative before and after refactoring plots of the analyzed metrics, including:

- distribution of cyclomatic complexity ranks  
- comparative plots of the maintainability index  
- comparative Halstead metrics (bugs, difficulty, effort, and volume)  
- comparisons of code size metrics (LOC, LLOC, and SLOC) 


## 2.4 `RUN` — Execution Log

The `RUN` file is an automatically generated execution log that records:

- the executed pipeline steps (`collect` — Section 2.1, `summarize` — Section 2.2, `plots` — Section 2.3)  
- the arguments used in each execution  
- the chronological order of execution of the automated scripts

This file enables full auditing and traceability of the experimental procedure.


## 2.5 `corpus_explorer_refactoring.ods` — Refactoring Catalog

This spreadsheet documents the qualitative dimension of the study.

For each refactoring-related commit or code modification, it records:

- the refactoring technique applied  
- where it was applied in the codebase  
- and the rationale behind the change

The classification follows established refactoring nomenclature from the literature and supports the quantitative distributions reported in the paper

## 3. Metric Collection and Analysis Pipeline

All metric and analysis artifacts included in this replication package (data, reports, and figures) were generated using an automated pipeline developed by the authors and are publicly available, together with the scripts and documentation, in the cortext-usp/metrics repository at:

> [gitlab.com/cortext-usp/metrics](https://gitlab.com/cortext-usp/metrics)

The pipeline enforces:

- separation between metric collection and analysis  
- explicit version control of the analyzed code  
- reproducible execution environments  
- and methodological traceability

To support traceability and auditing of the experimental process, the RUN execution log records the executed pipeline stages (metric collection, result aggregation, and plot generation), the arguments used in each execution, and the chronological order in which the automated scripts were run.