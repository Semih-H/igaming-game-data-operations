# Excel Workbook

This folder contains the working Excel file for the iGaming game metadata validation project.

## Workbook

`iGaming_Game_Metadata_Validation_Workbook.xlsx`

## Workbook contents

The workbook is organised into worksheets covering the following functions:

- **Incoming Feed** — original 100-record source dataset, retained without cleaning changes.
- **Provider Reference** — provider names, codes and aliases used in the exercise.
- **Market Reference** — accepted market codes for the simulation.
- **Data Dictionary** — definitions of the incoming metadata fields.
- **Cleaned Dataset** — working copy with proposed corrections and validation helper columns.
- **Issue Log** — identified issues, affected fields and records, investigation notes, proposed actions and statuses.
- **Validation Summary** — summary of checks and their outcomes, where retained in the final workbook.
- **Data Quality Report** — overview, validation results, key findings, outstanding actions and provider-level RTP completeness analysis.
- **Exception Queue** — records held for further investigation or verification.
- **Game Master Dataset** — standardised output containing records eligible for handover under the exercise's rules.

## How to review the workbook

Start with **Data Quality Report** for the overall findings. Then inspect **Issue Log** for the investigation trail, **Cleaned Dataset** for proposed corrections and validation results, and **Exception Queue** for unresolved records. The **Incoming Feed** remains the source-of-truth copy for this exercise.

## Important interpretation

A record passing an Excel validation rule does not prove that its metadata is correct in a provider's system. Corrections inferred from identifiers or reference tables remain provisional until confirmed against an authoritative source. The Game Master Dataset is therefore a simulated handover output, not a production-approved catalogue.
