# iGaming Game Metadata Database & Data Quality Management

A practical data operations project simulating how an iGaming platform receives, validates, investigates and standardises game metadata from multiple game providers.

**Tools:** Microsoft Excel · Pivot Tables · Excel Formulas · Data Validation

**Dataset:** 100 synthetic game records across five game providers.

---

## Project Overview

Game aggregators and iGaming platforms work with metadata supplied by multiple game providers. This information must be accurate, consistent and properly structured before games can be integrated into a central database and made available to operators.

This project simulates a game metadata onboarding and data quality management workflow.

Starting with an incoming provider feed containing 100 game records, I performed data inspection, automated validation, discrepancy investigation, data cleaning and standardisation. I then prepared a central game master dataset and an exception queue for records requiring further investigation.

The project focuses on practical data operations rather than simply cleaning a spreadsheet.

## Project Objectives

- Inspect and understand incoming provider game data.
- Identify missing, duplicated, invalid and inconsistent metadata.
- Validate information against provider and market reference tables.
- Investigate discrepancies and document proposed corrections.
- Standardise provider names, game categories, identifiers and data formats.
- Implement repeatable Excel-based validation rules.
- Separate records ready for handover from records requiring investigation.
- Prepare a structured central game metadata dataset.

## Workflow

The project followed this workflow:

**Incoming Feed → Data Profiling → Validation → Issue Investigation → Data Cleaning → Revalidation → Exception Management → Game Master Dataset**

### 1. Data Inspection

Reviewed the incoming dataset structure, identified its 12 metadata fields and examined the distribution of game records across providers and game categories.

### 2. Data Quality Assessment

Implemented validation checks to identify:

- Duplicate game identifiers.
- Missing metadata.
- Inconsistent provider names.
- Provider and identifier mismatches.
- Invalid numerical formats.
- Invalid release dates.
- Unrecognised market codes.
- Inconsistent game categories.
- Invalid or unexpected categorical values.

### 3. Issue Investigation

Created an issue log to document each identified problem, including:

- Issue classification.
- Affected field and records.
- Investigation findings.
- Proposed corrective action.
- Current resolution status.

Used provider and market reference tables to investigate discrepancies and distinguish between confirmed errors and values requiring external verification.

### 4. Data Cleaning and Standardisation

Prepared a separate working dataset while preserving the original incoming feed.

Cleaning activities included:

- Standardising provider names.
- Investigating duplicate identifiers.
- Correcting inconsistent game category labels.
- Normalising RTP numerical representation.
- Converting valid release-date strings into proper Excel dates.
- Validating individual market codes.
- Preserving unresolved or unverified values rather than inventing corrections.

### 5. Automated Validation

Developed reusable Excel formulas to validate game metadata, including:

- `COUNTIF`
- `XMATCH`
- `FILTER`
- `TEXTSPLIT`
- `ISNUMBER`
- `ISTEXT`
- `IF` and `LET`

Used Pivot Tables to analyse missing values and compare data quality across providers.

### 6. Exception Management and Database Preparation

Created separate outputs for records requiring investigation and records eligible for handover.

Prepared a standardised Game Master Dataset containing 12 metadata fields.

---

## Key Data Quality Findings

The initial dataset contained several types of data-quality problems.

| Issue | Findings |
|---|---|
| Duplicate identifiers | Two different games shared the same game ID. |
| Missing RTP | 40 out of 100 records had blank RTP values. |
| Missing provider | One game had no provider name. |
| Missing volatility | One game had no volatility classification. |
| Missing game type | One game had no game-type classification. |
| Provider inconsistency | Provider naming and identifier mismatches were identified. |
| RTP format | One RTP value appeared to use decimal rather than percentage representation. |
| Invalid date | One release date was invalid. |
| Invalid market code | One game contained an unrecognised market code. |
| Category inconsistency | One game used an inconsistent game-type label. |

## Provider-Level RTP Completeness Analysis

A Pivot Table was used to investigate the distribution of missing RTP values across providers.

| Provider | Total Games | Missing RTP | Missing Rate |
|---|---:|---:|---:|
| Evolution | 20 | 20 | 100% |
| BGaming | 24 | 12 | 50% |
| Pragmatic Play | 16 | 8 | 50% |
| Hacksaw Gaming | 19 | 0 | 0% |
| Play'n GO | 20 | 0 | 0% |
| **Total** | **99** | **40** | — |

One record with a missing provider was excluded from this provider-level comparison.

**Key observation:** All 20 Evolution records in the synthetic dataset had missing RTP values. This highlights the importance of analysing data completeness by provider rather than relying only on overall missing-value counts.

---

## Results

### Initial automated validation

| Status | Records |
|---|---:|
| Passed | 56 |
| Held for review | 44 |
| **Total** | **100** |

### Final handover classification

| Classification | Records |
|---|---:|
| Ready for handover | 52 |
| Hold — Data quality | 44 |
| Hold — Verification | 4 |
| **Total** | **100** |

The 52 records passed the defined validation and handover rules used in the simulation. The remaining records were retained in an exception workflow.

A record could have multiple underlying issues; the handover categories represent mutually exclusive record-level classifications.

## Project Deliverables

The repository contains the following materials:

### Source Data
- [Incoming Provider Feed](02-source-data/incoming_provider_feed.csv)
- [Provider Reference](02-source-data/provider_reference.csv)
- [Market Reference](02-source-data/market_reference.csv)
- [Data Dictionary](02-source-data/data_dictionary.csv)

### Excel Workbook

[Download the Game Metadata Validation Workbook](03-excel-workbook/iGaming_Game_Metadata_Validation_Workbook.xlsx)

The workbook includes the original feed, reference tables, cleaned dataset, issue log, validation results, exception queue, data quality report and game master dataset.

### Project Documentation

[View the Data Quality Project Report (PDF)](04-documentation/iGaming_Game_Metadata_Project_Report.pdf)

---

## Skills Demonstrated

- iGaming game metadata management.
- Provider reference and market data validation.
- Data profiling and quality assessment.
- Duplicate detection and discrepancy investigation.
- Data cleaning and standardisation.
- Excel-based automated validation.
- Pivot Table analysis.
- Cross-field consistency checks.
- Issue logging and exception management.
- Data quality reporting.
- Database preparation and handover.

## Project Scope and Limitations

This is an independent training project using synthetic game records and simulated provider metadata.

Real provider names are used for illustrative purposes, but the game titles, identifiers, RTP values, market rules and metadata are not verified representations of actual provider catalogues or commercial integrations.

Proposed corrections requiring provider confirmation remain explicitly identified as provisional.

The project does not represent professional experience working directly with the named game providers or an operational iGaming platform.

---

## Author

Independent portfolio project developed to demonstrate practical data quality, game metadata management and data operations skills relevant to the iGaming industry.
