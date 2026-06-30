# _archive — NOT IN USE

Files in this folder are **archived and not part of the active dashboard**.

- The folder name begins with `_`, so Quarto **excludes it from rendering** (it is also absent from the `render:` list in `_quarto.yml`).
- Nothing here is `source()`-ed, read, or referenced by `index.qmd`, `sections/detect_tool_dashboard.qmd`, or any data-management pipeline script.
- Kept (rather than deleted) for reference/history. Safe to delete entirely if no longer wanted.

_Archived 2026-06-17._

## `r/` — unused helper functions (16)

These define functions that are **never called** by any `.qmd` in the project. Verified by
grepping every function name (not just filename) across `sections/`, `data_management/`,
and `index.qmd`, including transitive calls between `r/` files.

| File | Function(s) defined | Why archived |
|---|---|---|
| `add_shade_column.R` | `add_shade_column` | Superseded by the live `r/add_shade_column_x_rows.R` |
| `broad_check_message.R` | `broad_check_message` | No callers |
| `cont_stats.R` | `cont_stats` | Stats cluster — no external caller |
| `cont_stats_grouped.R` | `cont_stats_grouped` | Stats cluster — no external caller |
| `n_mean_ci.R` | `n_mean_ci` | Only called by archived `cont_stats*` |
| `n_mean_ci_grouped.R` | `n_mean_ci_grouped` | Only called by archived `cont_stats*` |
| `n_median_ci.R` | `n_median_ci` | Only called by archived `cont_stats*` |
| `n_median_ci_grouped.R` | `n_median_ci_grouped` | Only called by archived `cont_stats*` |
| `n_percent_ci.R` | `n_percent_ci` | No callers |
| `n_percent_ci_grouped.R` | `n_percent_ci_grouped` | No callers |
| `fact_reloc.R` | `fact_reloc` | No callers |
| `get_unique_value_summary.R` | `get_unique_value_summary` | No callers |
| `identify_codebook_variables_to_update.R` | `vars_to_update` | No callers |
| `missingness_pattern.R` | `missing_pattern` | No callers |
| `missingness_summary.R` | `missing_summary` | No callers |
| `variable_descriptions.R` | `var_descriptions` | No callers (the `variable_descriptions.RDS` **data** files are unrelated and still in use) |

## `sections/` — archived dashboard pages

| File | Why archived |
|---|---|
| `detect_tool_pilot_dashboard.qmd` | Not in the `_quarto.yml` `render:` list; only appeared as a commented-out navbar entry. References pilot data files that no longer exist in the repo (`detect_tool_pilot_cleaned.RDS`, `dashboard_prepped_data.RData`), so it cannot render as-is. No other file references it. Sourced only `r/add_shade_column_x_rows.R`, which stays in `r/` for the active dashboard. |

### Still-active `r/` files (left in place, for reference)
`add_shade_column_x_rows.R`, `data_cleaning_tools.R`, `nums_to_na.R`,
`recoding_factoring_relocating.R`, `month_name_year.R`, `color_alert.R`,
`format_table.R`, `time_series.R`, `gauge_chart.R`
