# Source Data

This folder contains the synthetic input files used in the iGaming game metadata data-quality exercise.

| File | Description |
|---|---|
| `incoming_provider_feed.csv` | Original feed containing 100 simulated game records and 12 metadata fields. |
| `provider_reference.csv` | Reference list of provider names, provider codes and aliases used during the exercise. |
| `market_reference.csv` | Reference list of market codes accepted by the simulation. |
| `data_dictionary.csv` | Field definitions and expected data characteristics used to guide validation. |

## How the files are used

The incoming feed is treated as the source dataset and is preserved unchanged. Reference files are used to investigate and validate values; they are not treated as proof of actual provider or market approvals.

## Data disclaimer

All records and reference rules are synthetic training examples. Provider names are included for illustrative purposes only. This folder does not contain actual provider feeds, confidential information or verified commercial data.
