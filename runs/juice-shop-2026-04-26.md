# Darkmoon vs OWASP Juice Shop, raw run

> **Update (2026-11-22).** The anonymised record of this campaign (`camp_20260426_3d2f919b`: 57 findings with their evidence, map and possible attack paths) and of 10 other complete Juice Shop runs is now public on [demo.dark-moon.org](https://demo.dark-moon.org/project/proj_f3a8d4), and 80 remediation pull requests are public on [ASCIT31/juice-shop](https://github.com/ASCIT31/juice-shop/pulls?q=is%3Apr). The record also corrects two figures of the summary below: **24 of the 57 findings are recorded as exploited and 33 as confirmed** (not « proof of exploitation per finding »). Read the [update section](#update-2026-11-22) at the end of this page.

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

## Update (2026-11-22)

This section was added on 2026-11-22. The text above, including the correction of 2026-11-20, is kept unchanged as history; where they disagree, this section is the current statement.

Evidence labels: **VERIFIED** = checked on a public source linked here (the demo page or the GitHub repository), on 2026-11-22; **OBSERVED** = seen in a Darkmoon team record that is not published; **UNKNOWN** = no record.

### What is now public

1. **The campaign itself (VERIFIED).** [demo.dark-moon.org](https://demo.dark-moon.org/campaign/camp_20260426_3d2f919b?tab=findings) was rebuilt on 2026-11-20 to 2026-11-22 (this replaces item 2 of the correction above: the demo no longer shows synthetic data for Juice Shop). The project « Demo · OWASP Juice Shop — anonymised real campaigns » shows the real campaign `camp_20260426_3d2f919b` (the full id of `camp_20260426_3d2f`), anonymised: lab address, e-mail addresses, password hashes, tokens, keys, passwords and security answers are replaced or withheld, and the agent session logs are not included. Each finding has its description, CVSS score, endpoint, evidence and remediation text; the campaign also has its infrastructure map and attack-path view.
2. **Figures of the record (VERIFIED on the demo page).**

   | Field | Value on record | Note |
   |---|---|---|
   | Campaign | `camp_20260426_3d2f919b`, completed, 2026-04-26 16:24 UTC | |
   | Target | OWASP Juice Shop v19.2.1, black-box, lab container (anonymised as `juice-shop.demo.invalid`) | |
   | Findings | **57**: 8 critical / 24 high / 21 medium / 4 low / 0 info | unchanged |
   | Status | **24 exploited, 33 confirmed**, 0 unconfirmed | replaces « proof of exploitation per finding » |
   | Duration | 28 min « duration on record » (1,710 s = 28.5 min in the campaign record) | the campaign record's own value |
   | Activity window | about 55 min between the first and the last server event (3,295 s) | reconstructed from the run's session log, not recorded by the run |
   | Agents | 2 test agents: `nodejs`, `headless-browser` | |
   | Attack paths | 0 proven, 11 « possible, not proven » | |

3. **Model (OBSERVED, not in the published record).** The campaign record has no model field. The team states that this run used `claude-opus-4-6` (see the [leaderboard notes](./index.md)); no published file shows it, so treat the model of this one run as declared, not verified. For the four Opus runs of the history below, the model `claude-opus-4-6` is recorded in the agent session store of the Darkmoon team (matched to each campaign by its start time); that store is not published.
4. **Duplicates (VERIFIED on the demo page).** The 57 records are the agents' findings as pushed, not a de-duplicated list. Some overlap, for example two « Admin account weak password » records and three « password hash leak via /rest/memories » records. The « findings de-duplicated » wording elsewhere in this repository does not apply to this count.

### The other real Juice Shop runs (replaces the « escalation » table)

The demo project lists **11 real, complete campaigns** (26 Apr to 29 Sep 2026): the 26 Apr run above and the 10 below (VERIFIED on the [project page](https://demo.dark-moon.org/project/proj_f3a8d4)). They are kept as stored (date, status, findings), not copied or shifted. They are **not a progression** and not a repeated-measure series: Juice Shop version, scope, time box and model differ between runs, and two runs were deliberately scoped to SQL injection.

| Date (UTC) | Campaign | Findings (C/H/M/L/Info) | Exploited / confirmed | Duration on record | Scope (from the run's own summary) | Model (OBSERVED, session store) |
|---|---|:--:|:--:|:--:|---|---|
| 2026-04-26 16:24 | `camp_20260426_3d2f919b` | 57 (8/24/21/4/0) | 24 / 33 | 28.5 min | full | `claude-opus-4-6` (declared, see item 3) |
| 2026-07-28 07:09 | `camp_20260728_9018be77` | 45 (10/11/19/5/0) | 32 / 13 | 15 min | full | `claude-opus-4-6` |
| 2026-09-07 11:22 | `camp_20260907_84543343` | 7 (2/3/2/0/0) | 4 / 3 | 3 min | full | `claude-opus-4-6` |
| 2026-09-09 16:59 | `camp_20260909_57e146e4` | 40 (5/12/14/7/2) | 22 / 17 (1 unconfirmed) | 30 min | full | `claude-opus-4-6` |
| 2026-09-24 09:45 | `camp_20260924_0b3b1f9b` | 12 (4/4/1/3/0) | 9 / 3 | 5 min | full | `claude-sonnet-5` |
| 2026-09-24 10:24 | `camp_20260924_70602bf9` | 5 (2/1/2/0/0) | 5 / 0 | 15 min | SQL injection and IDOR only | `claude-sonnet-5` |
| 2026-09-24 12:19 | `camp_20260924_822d0040` | 7 (4/2/1/0/0) | 6 / 1 | 15 min | SQL injection only | `claude-sonnet-5` |
| 2026-09-24 12:36 | `camp_20260924_9fbe4f0d` | 13 (4/5/2/2/0) | 10 / 3 | 30 min | full | `claude-sonnet-5` |
| 2026-09-24 12:39 | `camp_20260924_f3d37e78` | 12 (4/2/2/4/0) | 8 / 4 | 23.3 min | full | `claude-sonnet-5` |
| 2026-09-24 12:41 | `camp_20260924_75d9ef1d` | 13 (3/5/2/3/0) | 7 / 5 (1 unconfirmed) | 15 min | full | `claude-sonnet-5` |
| 2026-09-29 15:41 | `camp_20260929_4b206944` | 31 (4/10/9/7/1) | 18 / 12 (1 unconfirmed) | 10 min | full | `claude-opus-4-6` |

Findings, severities, statuses and dates: VERIFIED on the demo (project page and each campaign's findings tab), from the anonymised extracts that build it. « Duration on record » is the `duration_seconds` field each run stored, read from the anonymised extract that builds the demo (OBSERVED; the demo shows it for the 26 Apr run); it is not a measured wall-clock time. Two further Juice Shop runs of 2026-11-08 ended `stopped` (not complete) and are not shown on the demo or counted here. Tokens and cost of these runs are not published (UNKNOWN here).

### Remediation pull requests (replaces item 4 of the correction)

VERIFIED on 2026-11-22 with `gh pr list -R ASCIT31/juice-shop --state all`:

- [ASCIT31/juice-shop](https://github.com/ASCIT31/juice-shop/pulls?q=is%3Apr) holds **80 pull requests**: **#1 to #57**, one per finding of the 26 Apr campaign, opened 2026-09-16; **#58**, a README change (not a remediation, merged 2026-11-20); **#59 to #80**, 22 remediation PRs opened 2026-11-21 for findings of the 10 other runs.
- All **79 remediation PRs are open; none is merged**. Each states that it is opened for human review and never auto-merged. Their correctness has not been independently verified.
- On the demo, all 57 findings of the 26 Apr campaign link to a PR (#1 to #57). In the 10 other runs, 182 of 185 findings link to a PR (a PR from #1 to #80 can fix the same issue found by several runs); 3 have none.
- « 42 of 57 remediated » remains **unsupported**: no record shows 42, and no remediation PR is merged. The documented figure is: 57 of 57 findings have an open remediation PR.
- PRs #1 to #57 each carry an AI-assistance disclosure naming the Darkmoon remediation agent and the finding id. PRs #59 to #80 carry no such statement: how they were produced is not recorded on the PR (UNKNOWN).

### What is still unknown

- Independent reproduction of any of these runs: none (UNKNOWN).
- Agent session logs, per-command raw output and cost of the 26 Apr run: not published.
- The model of the 26 Apr run: declared `claude-opus-4-6`, not in the published record.

For a protocol-based, multi-run comparison with recorded model labels, see the study [`studies/llm-pentest-juice-shop-2026`](../studies/llm-pentest-juice-shop-2026/). For model and provider checks on Azure AI Foundry, see [`azure-foundry-provider-validation-2026-11-22.md`](./azure-foundry-provider-validation-2026-11-22.md).
