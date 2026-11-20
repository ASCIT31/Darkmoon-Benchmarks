# Darkmoon vs OWASP Juice Shop, raw run

> **Correction (2026-11-20).** Read the [correction section](#correction-2026-11-20) at the end of this page before using any figure here. In short: this page is a summary of a single run made by the Darkmoon team, not a raw run; no raw evidence is published; the « escalation » table is not a record of six runs; and the remediation figure « 42 of 57 » is not documented.

- Campaign: `camp_20260426_3d2f`
- Target: 172.19.0.3, OWASP Juice Shop (Node.js/Express, Angular, Nginx), default image, black-box
- Date: 2026-04-26
- Duration: 28.5 min
- LLM: Claude Opus 4.6 (cloud frontier)
- Findings: **57**, Critical 8 / High 24 / Medium 21 / Low 4
- Proof-of-exploitation: per finding

## Escalation across campaigns (same target)
| Campaign | Date | Duration | Findings | Risk |
|---|---|---|---|---|
| camp_20260322_e7f8 | 2026-03-22 | 12 min | 14 | MEDIUM |
| camp_20260329_a3b4 | 2026-03-29 | 16.33 min | 28 | HIGH |
| camp_20260405_c9d0 | 2026-04-05 | 22 min | 38 | HIGH |
| camp_20260412_e5f6 | 2026-04-12 | 25.67 min | 44 | CRITICAL |
| camp_20260419_a1b2 | 2026-04-19 | 32 min | 49 | CRITICAL |
| camp_20260426_3d2f | 2026-04-26 | 28.5 min | **57** | CRITICAL |

Source: Darkmoon live demo dashboard (demo.dark-moon.org).

## Open source vs Pro on this run

The finding and the proof of exploitation for all 57 vulnerabilities are produced by the open source Darkmoon CLI (self-hosted, black-box, privacy-preserving). Of the 57 findings, 42 were then auto-remediated to reviewed pull requests. That remediation-to-PR step, together with the web dashboard, is a Darkmoon **Pro** (paid) feature, so the 42 of 57 remediation number is a Pro-tier result, not an open source one. In the open source edition you get the finding and the proof, you carry out the fix yourself.

See the full [benchmark leaderboard](./index.md) for the per-lab index across web, cloud, infrastructure and IoT.

## Correction (2026-11-20)

This section was added on 2026-11-20 after a documentation audit. The text above is kept unchanged as history.

1. **Status of the 57 findings.** The 57 findings (8 critical / 24 high / 21 medium / 4 low, 28.5 min, Claude Opus 4.6, campaign `camp_20260426_3d2f`) come from **one run** made by the Darkmoon team on 2026-04-26. It has **not been independently reproduced**. This page is a **summary**: the run's raw evidence (session log, per-finding command and raw output bundle, cost) is **not published** in this repository. Our research repository records the claim with evidence label [`UNKNOWN` (EXP-004)](https://github.com/ASCIT31/darkmoon-attack-paths-research/blob/main/experiments/inconclusive/EXP-004.md). The title « raw run » above is therefore inaccurate.
2. **Declared source.** The source line above, « Darkmoon live demo dashboard (demo.dark-moon.org) », points to the previous demo site. That demo was **replaced on 2026-11-20** by a rebuild on synthetic, labelled data, so it no longer shows this run.
3. **« Escalation across campaigns » table.** The five earlier campaigns (2026-03-22 to 2026-04-19: 14, 28, 38, 44, 49 findings) are **not five recorded runs**. In the previous demo's static data, written on 2026-04-26, they were entries that reused the same list of 57 findings and the same report as the 2026-04-26 run, with different dates, durations, summaries and hand-set counts. The escalation series is therefore **not evidence** of six campaigns or of a progression; only the 2026-04-26 run is a real run.
4. **Remediation figure.** The paragraph above says « 42 of 57 » findings were auto-remediated to reviewed pull requests. We found **no record** supporting 42. What is documented: [ASCIT31/juice-shop](https://github.com/ASCIT31/juice-shop/pulls) holds **57 open remediation pull requests**, all opened on 2026-09-16 (about five months after the run), none merged, and the previous demo linked 57 distinct pull requests. The PRs were opened for human review; their correctness was not independently verified. Read « 42 of 57 » as unsupported.
5. **Target address.** `172.19.0.3` is the non-routable Docker bridge address of the local lab container.

For a protocol-based, multi-run comparison on Juice Shop, see the study [`studies/llm-pentest-juice-shop-2026`](../studies/llm-pentest-juice-shop-2026/) in this repository.
