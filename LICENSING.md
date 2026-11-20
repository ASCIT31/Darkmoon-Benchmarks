# Licensing

## Darkmoon-Benchmarks: AGPL-3.0

From 20 November 2026 onwards, the code and documentation of this repository (validation, table and figure scripts, methodology and result pages) are free software licensed under the [GNU Affero General Public License v3.0](LICENSE) (SPDX: `AGPL-3.0-only`), the same licence as [Darkmoon Community](https://github.com/ASCIT31/Dark-Moon/blob/master/LICENSING.md).

In short (the [LICENSE](LICENSE) text is what applies):

- **Use it, study it, change it, share it.**
- **If you distribute it**, modified or not, you distribute the corresponding source under the AGPL-3.0.
- **If you run a modified version as a network service** (users interact with it remotely), you must offer those
  users the corresponding source of your modified version (AGPL-3.0, section 13).
- The AGPL-3.0 does not restrict who may use the software or for what; it requires reciprocity.

## Benchmark data: CC BY 4.0 (unchanged)

The study datasets keep the licence stated in their own `datasets/` directory. For
`studies/llm-pentest-juice-shop-2026/datasets/` that is **Creative Commons Attribution 4.0 International (CC BY 4.0)**,
see its [notice](studies/llm-pentest-juice-shop-2026/datasets/LICENSE). Third-party facts in the data (OWASP Juice Shop
challenge keys, names, categories and difficulty ratings) stay under the Juice Shop MIT licence. Recorded values such
as the `license` column of `context/tool_popularity_snapshot.csv` describe the state at the date of the snapshot and are
not changed.

## What stays under the previous licence

**Earlier versions.** Every version of this repository (code and documentation; the datasets were and stay CC BY 4.0) published up to commit `ce15f49` (20 November 2026) was licensed under the [GNU General Public License v3.0](LICENSES/GPL-3.0.txt) (the `LICENSE` file then held a one-line reference to the GPL-3.0 instead of the licence text; the full text is now in [LICENSES/GPL-3.0.txt](LICENSES/GPL-3.0.txt)). Those versions stay available under that licence; the change does not withdraw any right already granted.

**Earlier outside contributions.** None found. At the time of the change, the GitHub contributors API and the git history list only MBK-fr, asc-it and darkmoonX (ASC-IT accounts). Pull requests #1 and #2 were opened by MBK-fr. There is therefore no contribution by a person outside ASC to keep under the previous licence.

If an outside contribution is found later, it stays under the GNU GPL v3.0 and is not relicensed: it remains in this
repository, combined with the AGPL-3.0 code, as section 13 of the GNU GPL v3.0 and section 13 of the GNU AGPL v3.0
expressly allow, and it will be listed here.

If you contributed to this repository and are not listed, open an issue.

## Contributing from now on

New contributions are accepted under the AGPL-3.0. The Darkmoon [Contributor License Agreement](https://github.com/ASCIT31/Dark-Moon/blob/master/CLA.md)
is a draft under legal review and cannot be signed yet.

## Darkmoon

Darkmoon Community, the platform this repository works with, is AGPL-3.0 as well (earlier releases up to commit
`edfe9cb` stay GPL-3.0), see its [LICENSING.md](https://github.com/ASCIT31/Dark-Moon/blob/master/LICENSING.md).
Darkmoon Pro is a separate commercial product with its own licence.

## Trademarks

The licences cover the code and content, not the Darkmoon name and logos.

## License texts

- [LICENSE](LICENSE) — GNU Affero General Public License v3.0 (also in [LICENSES/AGPL-3.0.txt](LICENSES/AGPL-3.0.txt))
- [LICENSES/GPL-3.0.txt](LICENSES/GPL-3.0.txt) — GNU General Public License v3.0 (earlier versions)
- [studies/llm-pentest-juice-shop-2026/datasets/LICENSE](studies/llm-pentest-juice-shop-2026/datasets/LICENSE) — CC BY 4.0 notice for the study data
