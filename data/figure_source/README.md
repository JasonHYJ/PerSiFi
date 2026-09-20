# Figure source data

These files preserve the available numerical inputs and derived plotting summaries for Figures 5 and 7. They are not raw traffic traces or per-sample prediction logs. No additional experimental observations have been generated for this release.

## Figure 5

- `Figure5_checkpoint_selection_revised_source.csv`: 80 entries in their existing source order.
- `Figure5_checkpoint_selection_revised_curve.csv`: 2,000 sampled points of the density curve.
- `Figure5_checkpoint_selection_revised_audit.json`: density-estimation settings and source-record counts.

### Period-entry fields

| Field | Meaning | Unit / values |
| --- | --- | --- |
| `source_entry_id` | Sequential position in the supplied figure data; not a device identifier | Integer |
| `raw_period` | Original period value or lower-bound notation | Seconds, or `>7200` |
| `exact_period_s` | Exact period, when available | Seconds; blank for a lower-bound-only entry |
| `lower_bound_s` | Recorded lower bound, when available | Seconds; blank for an exact entry |
| `record_status` | Type of record | `exact_value` or `lower_bound_only` |
| `used_in_kde` | Whether the entry contributes to the density estimate | `1` or `0` |

The density uses the 73 exact values, a Gaussian kernel, reflection at zero and a robust Silverman bandwidth of approximately 322.344 s. The seven entries recorded only as `>7200` are retained in the source CSV but excluded from the estimate. The exact value 7,877 s is included; the seven lower-bound entries must not be interpreted as all entries exceeding 7,200 s.

The curve fields are `maximum_reliable_period_s` (seconds) and `density_per_s` (inverse seconds). The plotted ordinate multiplies `density_per_s` by 1,000, as indicated by the figure's axis units. The curve describes the exact-value subset and is not a censoring-adjusted estimate of all 80 entries.

The available figure-source file does not contain device identifiers, run identifiers or enrollment/validation membership. Those mappings cannot be recovered from these figure files alone.

## Figure 7

`Figure7_continuous_identification_source.csv` contains checkpoint-level counts and proportions for 885 observation records.

| Field | Meaning | Unit / values |
| --- | --- | --- |
| `checkpoint_s` | Observation checkpoint | Seconds; the final text-valued row is an abstention summary |
| `first_identified_n` | Number first assigned an identity at this checkpoint | Records |
| `first_identification_increment_pct` | First-identification count divided by 885 | Percent, on a 0-100 scale |
| `cumulative_identified_n` | Cumulative number assigned an identity | Records |
| `cumulative_coverage_pct` | Cumulative identification count divided by 885 | Percent, on a 0-100 scale |
| `total_samples_n` | Number of observation records | 885 |

The final row, `unresolved_after_7200_s`, records 37 final abstentions (4.180791%); it is not another observation checkpoint or first-identification event. Its cumulative fields are blank. Across the seven checkpoints, 848 records receive an identity. Counts include both correct and incorrect identity assignments. This CSV does not contain checkpoint-level correctness labels or independent repeated-run results.

## Integrity

The CSV and JSON files are copied unchanged from the available figure outputs. [The repository manifest](../../MANIFEST.csv) provides file sizes and SHA-256 checksums. Blank fields represent unavailable or inapplicable values, not zeros.
