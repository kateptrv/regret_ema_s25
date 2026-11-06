# Regret life-domain coding

Qualitative coding of the life domain of each regret participants wrote about in the EMA.

## Files

- `codebook.md`: categories, definitions, examples and decision rules.
- `regret_domain_codes.csv`: one row per regret episode, keyed by the Qualtrics
  `ResponseId` of the ping where the regret was first reported. `PID`, `regret_id` and
  `regret_text` are there for reference while coding. The merge only uses `ResponseId`,
  so it doesn't matter if episode numbering changes when the data are reprocessed.
- `uncoded_regrets.csv`: written by `code/domain_coding.R` if any regret in the current
  processed data has no code yet (e.g., after reprocessing adds new valid pings).

## Workflow

1. Run `code/processing.Rmd` to build `data/processed_merged.csv`.
2. Run `code/domain_coding.R`. It checks `regret_domain_codes.csv` against the codebook
   (valid codes, no duplicates, every regret coded) and writes any uncoded regrets to
   `uncoded_regrets.csv`.
3. Code any new rows following `codebook.md` and append them to
   `regret_domain_codes.csv`, then delete `uncoded_regrets.csv`.
4. Rerun `code/processing.Rmd`. It joins `regret_domain` and `regret_domain_secondary`
   onto every ping of each episode (non-regret pings are `NA`).

To change a code, edit `regret_domain_codes.csv` and rerun `processing.Rmd`.
