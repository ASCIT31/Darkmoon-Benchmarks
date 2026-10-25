# Contributing to Darkmoon-Benchmarks

This repository publishes benchmark records of autonomous AI penetration testing. Contributions are welcome when they make the records more **verifiable**: new reproducible runs, corrections, better analyses, or replications of an existing study.

## Ground rules

- **Named, public, authorized targets only.** Runs must target a public, intentionally vulnerable lab (OWASP Juice Shop, IoTGoat, DVWA, a published cloud lab, ...) or a system you own. Never submit results against third-party systems.
- **Conditions in the open.** State the tool and its version (commit or tag), the model and how it was reached (local or hosted), the target version or image digest, the date, the time budget, black-box or white-box, and how many runs you did. Unknown values are written as "not recorded", never guessed.
- **No selection.** Submit every run of a series, including failed and low-scoring ones, or state explicitly which runs are missing and why.
- **Evidence.** Link raw output or a full report for every number. Aggregates must be recomputable from the submitted data.
- **No accusations.** We do not claim that any tool cheats, and we do not accept submissions that do. Report conditions, not intentions.
- **Disclose your role.** If you build, sell or operate the tool you benchmark, say so (the Darkmoon team does so for every Darkmoon run in this repository).

## What never goes into a pull request

Secrets, API keys, tokens, `.env` files, database dumps, backup archives, raw traffic captures with payloads, prompts or transcripts that contain private data, personal data, internal IP addresses or hostnames, customer information. CI runs a secret scan on every push and pull request; a finding blocks the merge.

## Adding a run to the multi-surface leaderboard

Open a pull request that adds a row to [`runs/index.md`](runs/index.md) (and a run page under `runs/` if the raw output is not hosted elsewhere) with: tool name and version, run date, target, per-severity finding counts, exploited count, wall-clock time, LLM location (local or cloud), and a link to the raw output or report.

## Adding or extending a study

A study lives in `studies/<study-id>/` and follows the layout of [`studies/llm-pentest-juice-shop-2026`](studies/llm-pentest-juice-shop-2026/):

- `README.md` (question, scope, operator disclosure, results, limits), `methodology/`, `datasets/` (with `README.md`, `manifest.json` and a data licence), `results/`, `diagrams/`, `scripts/`, `reproducibility/README.md`;
- tables in Markdown are generated from the data between `<!-- BEGIN GENERATED:... -->` markers, never typed by hand;
- a `validate_results.py` that recomputes every score from the per-item data.

Before opening the pull request:

```bash
cd studies/llm-pentest-juice-shop-2026
python3 scripts/validate_results.py
python3 scripts/generate_tables.py --check
python3 diagrams/src/build_figures.py --check
```

## Licences

By contributing you agree that code and documentation are released under the repository licence (GPL-3.0) and that study datasets are released under the licence stated in their `datasets/` directory (CC BY 4.0 for `llm-pentest-juice-shop-2026`).

## Security

To report a security problem in this repository or in Darkmoon, follow the [ASC-IT security policy](https://github.com/ASCIT31/.github/blob/main/SECURITY.md); do not open a public issue.
