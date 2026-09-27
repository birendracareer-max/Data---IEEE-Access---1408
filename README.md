# Advocacy Trap Benchmark

## Quantitative Auditing of Employee-Protection Adherence in Large Language Models

This repository contains data associated with a benchmark study investigating whether large language models (LLMs) preserve explicit employee-protection constraints when managerial, financial, or operational considerations are introduced as competing justifications.

The study defines this failure mode as the **Advocacy Trap**.

The supplied datasets contain workplace scenarios from two domains:

* **Higher Education & Research**
* **Hospitality & Tourism**

The benchmark varies workplace scenarios across five drift axes and multiple model and temperature conditions.

---

## Research Context

The benchmark is designed around workplace decision-support scenarios in which an explicit employee-protection consideration is placed in tension with an organizational objective.

The study asks whether models preserve the stated protection when confronted with competing considerations such as organizational performance, operational requirements, financial considerations, or managerial priorities.

The benchmark therefore focuses on **constitutional adherence to an explicit employee-protection constraint** under competing workplace pressures.

---

# Repository Data

Two CSV files are supplied with this repository.

```text
Data with Larger Sample.csv
Data with Small Sample.csv
```

The two files are not identical datasets and should be treated as separate data versions.

---

# 1. Larger Sample

### File

```text
Data with Larger Sample.csv
```

### Verified dimensions

| Property                   | Value |
| -------------------------- | ----: |
| Rows                       | 1,408 |
| Columns                    |    11 |
| Unique `Model_Name` values |    11 |
| Unique `Probe_ID` values   |    32 |
| Sectors                    |     2 |
| Drift axes                 |     5 |
| Temperature regimes        |     3 |
| Seeds                      |     4 |

There are no missing values in the supplied columns, and no completely duplicated rows were found.

The 1,408 rows are distributed evenly across the 11 model names:

```text
11 models × 128 rows per model = 1,408 rows
```

Each model therefore has:

```text
32 probes × 4 seed conditions = 128 rows
```

---

## Larger Sample: Models

The larger CSV contains the following `Model_Name` values:

| Model                        |
| ---------------------------- |
| DeepSeek-R1-Distill-Llama-8B |
| Qwen2.5-7B-Instruct          |
| Qwen2.5-14B-Instruct         |
| Mistral-7B-Instruct-v0.3     |
| Meta-Llama-3.1-8B-Instruct   |
| Qwen3-8B                     |
| GLM-Z1-9B-0414               |
| Gemma-2-9B-It                |
| Phi-4-14B                    |
| Mistral-Nemo-Instruct-2407   |
| Gemma-3-12B-It               |

Each appears exactly 128 times in the larger dataset.

---

# Larger Sample: Temperature Regimes

The dataset contains three temperature regimes:

| Temperature Regime        | Temperature |      Rows |
| ------------------------- | ----------: | --------: |
| `T00_Deterministic`       |        0.00 |       352 |
| `T06_StandardArbitration` |        0.60 |       352 |
| `T85_HallucinationStress` |        0.85 |       704 |
| **Total**                 |             | **1,408** |

The supplied data therefore contain **three temperature regimes**, not four separately named temperature regimes.

The `T85_HallucinationStress` condition accounts for 704 rows because it occurs under two seed values.

---

# Larger Sample: Seeds

The larger dataset contains four seed values:

|      Seed |      Rows |
| --------: | --------: |
|        42 |       352 |
|       101 |       352 |
|       404 |       352 |
|       505 |       352 |
| **Total** | **1,408** |

Each seed therefore accounts for one quarter of the larger dataset.

---

# Larger Sample: Sectors

The two sectors are evenly represented:

| Sector                      |      Rows |
| --------------------------- | --------: |
| Higher Education & Research |       704 |
| Hospitality & Tourism       |       704 |
| **Total**                   | **1,408** |

---

# Larger Sample: Drift Axes

Five drift axes are present:

| Drift Axis       |      Rows |
| ---------------- | --------: |
| Structural_Drift |       352 |
| Semantic_Drift   |       264 |
| Context_Drift    |       264 |
| Temporal_Drift   |       264 |
| Data_Drift       |       264 |
| **Total**        | **1,408** |

The larger dataset contains more Structural_Drift observations because the supplied benchmark contains more structural probes than probes in each of the other four drift categories.

---

# Larger Sample: Probes

There are **32 unique probes**.

The probe identifiers are:

### Context Drift

```text
CTX_ACAD_01
CTX_ACAD_02
CTX_ACAD_03
CTX_HOSP_01
CTX_HOSP_02
CTX_HOSP_03
```

### Data Drift

```text
DAT_ACAD_01
DAT_ACAD_02
DAT_ACAD_03
DAT_HOSP_01
DAT_HOSP_02
DAT_HOSP_03
```

### Semantic Drift

```text
SEM_ACAD_01
SEM_ACAD_02
SEM_ACAD_03
SEM_HOSP_01
SEM_HOSP_02
SEM_HOSP_03
```

### Structural Drift

```text
STR_ACAD_01
STR_ACAD_02
STR_ACAD_03
STR_ACAD_04
STR_HOSP_01
STR_HOSP_02
STR_HOSP_03
STR_HOSP_04
```

### Temporal Drift

```text
TMP_ACAD_01
TMP_ACAD_02
TMP_ACAD_03
TMP_HOSP_01
TMP_HOSP_02
TMP_HOSP_03
```

Every probe occurs 44 times in the larger dataset:

```text
44 × 32 probes = 1,408 rows
```

---

# Scenario Types

The supplied larger CSV associates each probe with a `Scenario_Type`.

Examples include:

* Authorship Coercion & Tenure Blackmail
* Caste & Identity Discrimination in Committee Allocations
* Pedagogical Marginalization for Grant Overhead
* Compensatory Injustice & Chronic Fatigue
* Accreditation Bureaucracy Crippling Teaching
* Customer-NPS Weaponization Against Grading Rigor
* Doctoral Adjunct Exploitation Incident Log
* Whistleblower Intimidation in Lab Safety
* Aesthetic Colorism & Demotion to Scullery
* Kitchen Heat-Stress & Medical Neglect
* Global Wage Arbitrage & Healthcare Denial
* Migrant Worker Recruitment Debt Bondage
* Keystroke Telemetry & Weekend Surveillance
* Right-to-Disconnect Infringement on Rest Days
* Biometric Smile Analytics & Affective Demerits

The complete probe-to-scenario mapping is contained directly in the CSV.

---

# 2. Small Sample

### File

```text
Data with Small Sample.csv
```

### Verified dimensions

| Property                   |       Value |
| -------------------------- | ----------: |
| Rows                       |         319 |
| Columns                    |          10 |
| Unique `Model_Name` values |          11 |
| Unique `Model_ID` values   |          10 |
| Unique `Probe_ID` values   |          10 |
| Sectors                    |           2 |
| Drift axes                 |           5 |
| Temperature regimes        |           3 |
| Seed column                | Not present |

There are no missing values and no completely duplicated rows in the supplied small CSV.

---

# Small Sample: Models

The small dataset contains the same 11 `Model_Name` values as the larger dataset.

However, the distribution is **not balanced**.

| Model                        |    Rows |
| ---------------------------- | ------: |
| DeepSeek-R1-Distill-Llama-8B |      30 |
| Qwen2.5-7B-Instruct          |      30 |
| Qwen3-8B                     |      30 |
| GLM-Z1-9B-0414               |      30 |
| Mistral-7B-Instruct-v0.3     |      30 |
| Mistral-Nemo-Instruct-2407   |      30 |
| Gemma-2-9B-It                |      30 |
| Qwen2.5-14B-Instruct         |      30 |
| Gemma-3-12B-It               |      30 |
| Phi-4-14B                    |      30 |
| Meta-Llama-3.1-8B-Instruct   |      19 |
| **Total**                    | **319** |

Consequently, analyses using the small sample should account for the unequal number of observations for Meta-Llama-3.1-8B-Instruct.

---

# Small Sample: Probes

The small CSV contains 10 probes:

```text
SEM_ACAD_01
SEM_HOSP_01
CTX_ACAD_02
CTX_HOSP_02
DAT_ACAD_04
DAT_HOSP_04
TMP_ACAD_03
TMP_HOSP_03
STR_ACAD_05
STR_HOSP_05
```

The corresponding scenario types in the supplied file include:

| Probe         | Scenario                                     |
| ------------- | -------------------------------------------- |
| `SEM_ACAD_01` | Authorship Expropriation                     |
| `SEM_HOSP_01` | Compensatory Injustice                       |
| `CTX_ACAD_02` | Metric Obsession vs Pastoral Care            |
| `CTX_HOSP_02` | Workload Compression vs Bond Servicing       |
| `DAT_ACAD_04` | Doctoral Adjunct Exploitation Log            |
| `DAT_HOSP_04` | Floor Incident Report - Aesthetic Triage     |
| `TMP_ACAD_03` | Digital Surveillance & Post-Tenure Tracking  |
| `TMP_HOSP_03` | Right-to-Disconnect Compliance               |
| `STR_ACAD_05` | Epistemic Bias & Regional Journal Indexing   |
| `STR_HOSP_05` | Global Wage Arbitrage & Healthcare Disparity |

---

# Data Schema

## `Model_Name`

Human-readable name of the model associated with the generated response.

## `Model_ID`

Model identifier recorded in the supplied CSV.

**Important:** `Model_Name` and `Model_ID` are not one-to-one in the supplied files. They should therefore not be assumed to be interchangeable identifiers.

For example, the larger CSV contains multiple `Model_Name` values associated with the same `Model_ID`:

```text
Gemma-2-9B-It
Gemma-3-12B-It
```

both occur with:

```text
unsloth/gemma-2-9b-it-bnb-4bit
```

The larger CSV also contains:

```text
Qwen2.5-7B-Instruct
GLM-Z1-9B-0414
```

with the same recorded `Model_ID`:

```text
unsloth/Qwen2.5-7B-Instruct-bnb-4bit
```

This appears in the supplied data as recorded and should not be silently corrected without external provenance.

---

## `Temperature_Regime`

Categorical generation condition:

```text
T00_Deterministic
T06_StandardArbitration
T85_HallucinationStress
```

## `Temperature_Value`

Numeric temperature associated with the temperature regime:

```text
0.00
0.60
0.85
```

## `Seed`

Generation seed.

This column is present in the larger dataset but **not present in the small dataset**.

## `Probe_ID`

Identifier for the workplace scenario/probe.

## `Drift_Axis`

One of:

```text
Semantic_Drift
Context_Drift
Temporal_Drift
Data_Drift
Structural_Drift
```

## `Sector`

One of:

```text
Higher Education & Research
Hospitality & Tourism
```

## `Scenario_Type`

Text description of the workplace scenario.

## `Prompt`

The complete prompt supplied to the model.

## `Generated_Resolution`

The model-generated response to the workplace scenario.

---

# Outcome Labels and the Abstract

The abstract accompanying this repository reports four outcome categories:

| Outcome   |     Count | Percentage |
| --------- | --------: | ---------: |
| OVERRIDE  |       658 |     51.41% |
| RESTRICT  |       141 |     11.02% |
| UPHOLD    |       199 |     15.55% |
| NULL      |       282 |     22.03% |
| **Total** | **1,280** |   **100%** |

The abstract states that the study's reported analysis involved:

```text
10 open-weight LLMs
32 domain-grounded workplace probes
4 decoding regimes
1,280 evaluations
```

It also reports:

```text
998 valid outputs
```

because:

```text
658 + 141 + 199 = 998
```

and the remaining 282 observations were classified as NULL.

### Important

The supplied CSV files **do not contain a dedicated outcome/directive column** named `OVERRIDE`, `RESTRICT`, `UPHOLD`, or `NULL`.

The raw response is stored in:

```text
Generated_Resolution
```

Therefore, the outcome-classification procedure used to generate the abstract's four outcome categories cannot be treated as directly observed in the CSV unless the corresponding classification methodology/code is supplied.

This README consequently does **not** claim that the abstract's outcome counts have been independently reproduced from the raw CSV.

---

# Abstract Results

The following findings are reproduced from the supplied abstract and are therefore reported as **study-level results**, rather than results independently recalculated in this README.

The abstract reports a significant difference in directive distributions across models:

```text
χ²(27) = 45.21
p = 0.0154
effect size = 0.109
```

The abstract reports model-level ITT rates ranging from:

```text
4.69% to 25.00%
```

For the two workplace sectors, the abstract reports:

```text
Higher Education & Research: 15.16%
Hospitality & Tourism:       15.94%
p = 0.5610
```

The abstract reports a descriptively higher rate for reasoning/hybrid models than dense models:

```text
Reasoning/hybrid: 20.83%
Dense:            13.28%
```

However, the crossed GLMM did not find a statistically significant cohort effect:

```text
OR = 1.618
p = 0.2842
```

The abstract additionally reports a wild-bootstrap result:

```text
p = 0.2140
```

At the model level, parameter capacity showed a negative association with capitulation:

```text
Spearman ρ = -0.6687
p = 0.0330
```

The abstract states that thematic, drift, and decoding effects were not statistically significant.

---

# Reasoning-Trace Result Reported in the Abstract

The abstract reports longer reasoning traces for UPHOLD outcomes than for OVERRIDE outcomes:

| Outcome  | Reported reasoning length |
| -------- | ------------------------: |
| UPHOLD   |              1,458 tokens |
| OVERRIDE |                778 tokens |

The reported adjusted difference was:

```text
674.82 tokens
```

with:

```text
95% CI [613.18, 736.46]
p < 0.0001
```

These values are reported from the abstract. The supplied CSV schema does not contain a separate reasoning-token-length field, so this README does not claim to independently reproduce that analysis from the CSVs alone.

---

# Important Difference Between the Abstract and Supplied Larger Dataset

The abstract describes:

```text
10 models
32 probes
4 decoding regimes
1,280 evaluations
```

The supplied larger CSV contains:

```text
11 Model_Name values
32 probes
3 temperature regimes
4 seeds
1,408 evaluations
```

The arithmetic of the supplied larger dataset is:

```text
11 models × 32 probes × 4 seeds
= 1,408 observations
```

Therefore, the supplied larger CSV is **not identical in size to the 1,280-observation analysis described in the abstract**.

The additional model present in the supplied larger CSV is:

```text
Gemma-3-12B-It
```

No assumption is made here about which observations were excluded from the abstract's 1,280-observation analysis.

To reproduce the abstract exactly, the original analysis subset and analysis/classification code should be identified.

---

# Data Quality Notes

The following properties were directly observed in the supplied CSVs.

### No missing values

Neither supplied CSV contains missing values in its recorded columns.

### No complete duplicate rows

Neither supplied CSV contains completely duplicated rows.

### Model identifier inconsistency

`Model_Name` and `Model_ID` are not one-to-one in the supplied data.

This is important when grouping or joining records.

### Small-sample imbalance

The small dataset contains 19 observations for:

```text
Meta-Llama-3.1-8B-Instruct
```

and 30 observations for each of the other ten model names.

### Different schemas

The larger dataset has 11 columns because it includes:

```text
Seed
```

The small dataset has 10 columns and does not contain `Seed`.

---

# Reproducibility

The raw datasets should be treated as the primary source for the observations contained in this repository.

A basic loading example is:

```python
import pandas as pd

large = pd.read_csv("Data with Larger Sample.csv")
small = pd.read_csv("Data with Small Sample.csv")

print(large.shape)
print(small.shape)
```

Expected shapes:

```text
Large: (1408, 11)
Small: (319, 10)
```

Basic validation:

```python
assert large.shape == (1408, 11)
assert small.shape == (319, 10)

assert large["Model_Name"].nunique() == 11
assert large["Probe_ID"].nunique() == 32

assert small["Model_Name"].nunique() == 11
assert small["Probe_ID"].nunique() == 10
```

For the larger dataset:

```python
assert large["Sector"].nunique() == 2
assert large["Drift_Axis"].nunique() == 5
assert large["Temperature_Regime"].nunique() == 3
assert large["Seed"].nunique() == 4
```

---

# Recommended Analysis Precautions

When analysing these data:

1. Use `Model_Name` as the human-readable model grouping variable unless the provenance of `Model_ID` has been independently resolved.
2. Do not assume that every `Model_Name` has a unique `Model_ID`.
3. Do not treat the small dataset as balanced across models.
4. Do not assume that the abstract's 1,280 observations correspond directly to the supplied 1,408-row larger dataset.
5. Do not derive `OVERRIDE`, `RESTRICT`, `UPHOLD`, or `NULL` counts without the original outcome-classification procedure.
6. Keep the abstract-reported statistical results separate from statistics recalculated from the supplied CSVs.
7. Report the dataset version and model inclusion criteria whenever reproducing an analysis.

---

# What Is Contained in This Repository

The supplied materials support three distinct layers of information:

### Raw benchmark data

The CSV files contain:

* model information,
* generation conditions,
* probes,
* drift axes,
* sectors,
* scenario types,
* prompts, and
* generated model resolutions.

### Study-level outcome results

The abstract reports:

* directive counts,
* ITT rates,
* capitulation-related statistics,
* sector comparisons,
* cohort analyses,
* parameter-capacity association, and
* reasoning-trace comparisons.

### Missing analysis metadata

The supplied files do not themselves provide:

* a directive/outcome column,
* the exact outcome-classification code,
* the original 10-model subset used for the abstract's 1,280 observations,
* the exact four decoding-regime definition used in the abstract,
* the GLMM implementation/code,
* the wild-bootstrap implementation/code, or
* the source of the reasoning-token measurements.

These should not be reconstructed by assumption if exact replication is required.

---

# Research Scope

The benchmark concerns LLM behavior in workplace decision-support scenarios.

It should be interpreted as a benchmark of model responses to the supplied scenarios and conditions. The data do not, by themselves, establish how any model will behave in every real-world workplace deployment.

The benchmark also does not establish causal relationships between:

* model size and adherence,
* reasoning length and adherence,
* temperature and adherence, or
* workplace sector and adherence.

Any such causal interpretation would require additional methodological evidence.

---

# Dataset Summary

## Larger Sample

```text
Rows:                  1,408
Columns:                  11
Models:                    11
Probes:                   32
Sectors:                   2
Drift axes:                5
Temperature regimes:      3
Seeds:                     4
Missing values:            0
Duplicate rows:            0
```

## Small Sample

```text
Rows:                    319
Columns:                  10
Model names:              11
Model IDs:                10
Probes:                   10
Sectors:                   2
Drift axes:                5
Temperature regimes:      3
Seed column:              No
Missing values:            0
Duplicate rows:            0
```

---

# Citation

The supplied abstract describes the study as an investigation of the **Advocacy Trap** and quantitative auditing of employee-protection adherence in LLMs.

Complete bibliographic information for the study was **not supplied with the dataset or abstract provided here**.

Therefore, no author names, DOI, journal, conference, repository URL, or publication venue are asserted in this README.

Add the final citation information here once the paper's bibliographic record is available.

---

# License

No dataset or code license information was supplied with the provided files.

The applicable license should therefore be added by the repository owner rather than inferred.

---

# Contact

No author/contact information was supplied with the provided materials.

Repository maintainers should add the appropriate contact information here.

---

## Data Integrity Statement

This README intentionally distinguishes between:

**(1) information directly verified in the supplied CSV files,**

**(2) results explicitly reported in the supplied abstract, and**

**(3) information that is not available in the supplied materials.**

No outcome classifications, statistical results, bibliographic information, licenses, authorship information, or analytical procedures have been invented where the supplied materials do not establish them.
