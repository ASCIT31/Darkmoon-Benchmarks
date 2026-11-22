# Darkmoon on Azure AI Foundry: provider validation (2026-11-22)

> **What this page is.** A record of **smoke checks and single runs** made by the Darkmoon team on 2026-11-22, to check that Darkmoon Pro can run its campaigns on models deployed in Azure AI Foundry. Each model was run once or a few times against an **intentionally vulnerable lab application** (Damn Vulnerable GraphQL Application, on a loopback address inside a sandbox), under operator rules (lab only, no destructive mutation, no denial of service, `curl --max-time 10`, finalize within 15 min), and most runs were **stopped as soon as the check passed**. It is **not a benchmark**: no repeated runs, no common time box, no scoring protocol. Do not rank models from it.

Evidence labels: **VERIFIED** = run by the Darkmoon team, with console logs, run records and screenshots kept in the team's internal evidence folder (not published in this repository); **UNKNOWN** = not established. No raw log of these runs is published here.

## Set-up

- **Provider**: Azure AI Foundry, pay-as-you-go subscription, region East US 2. Models reached through Darkmoon Pro's native Azure mode (opencode's built-in `azure` provider) or the OpenAI-compatible route.
- **Darkmoon**: Darkmoon Pro installed with the public installer in a sandbox, then updated to pre-release builds of the fixes being tested that day (not a public release).
- **Target**: Damn Vulnerable GraphQL Application (DVGA), a public, intentionally vulnerable lab, no external target.
- **Cost**: the costs below are **estimates** from the token counts recorded by opencode multiplied by Azure retail list prices; the Azure billing data was not yet available.

## Results

| Model (Foundry deployment) | Did a Darkmoon campaign run? | Result | Level |
|---|---|---|---|
| `gpt-5.3-codex` | **Yes, completed** | One run completed and finalized in 6.4 min: 14 commands, **4 findings (1 critical exploited: command injection in `systemDebug`; 2 medium; 1 low)**, est. USD 0.46. In another run, the `graphql` specialist dispatched through the `task` tool made 63 tool calls of its own (54 commands on the lab). An earlier run hit Azure's 429 token-rate limit at a 200 K TPM deployment quota (12 commands, 2 findings before it stopped). | VERIFIED |
| `Kimi-K3.1-Pro` | **Yes, completed** | One full campaign: 4 commands plus the `graphql` specialist, **6 findings (3 high, 3 medium; 5 exploited)**, finalized in 13.6 min, est. USD 1.53; one headless-browser sub-agent response was blocked by Azure's default content filter. A second run (later build): 9 commands, 4 findings, finalized, est. USD 0.99. Two later runs ended on a network error (ECONNRESET). | VERIFIED |
| `gpt-oss-120b` | Started, shallow | The campaign started with no refusal and 8 orchestrator commands; the dispatched `graphql` specialist made 1 tool call and returned an empty result. | VERIFIED |
| `gpt-5-mini` | Started, shallow | **0 refusals in 9 campaigns**; results were shallow (2 to 6 commands, 0 to 2 findings per run). | VERIFIED |
| `DeepSeek-V4-Pro` | **No** | Blocked by quota: the deployment is capped at 20 K tokens per minute (the subscription maximum), below Darkmoon's first prompt (about 40 K tokens), so every call returned 429. Not a model result. | VERIFIED |
| `grok-4.6` | Not run as a campaign | The deployment answered API calls (Responses and chat routes); no campaign was run. | VERIFIED (API only) |
| Claude (`claude-opus-4-6`, `claude-haiku-4-5`) | **No, not deployable** | Quota existed, but the deployments failed with « This purchase cannot be completed »: Claude on Foundry is an Azure Marketplace purchase, which this subscription was refused. A Darkmoon campaign on Claude through Foundry is **UNKNOWN**. | VERIFIED (deployment failure) |
| `gpt-6.2-sol`, `gpt-6.1-sol`, `gpt-6-sol`, `gpt-5.6-sol`, `gpt-5.5` | **No, not deployable** | Deployment failed on a quota of 0; quota requests were refused (« contact support »). | VERIFIED (deployment failure) |

No model refused to run a campaign in these checks (gpt-5-mini, gpt-5.3-codex, gpt-oss-120b, Kimi K3.1 Pro).

## Limits of this protocol

- **One or a few runs per model**, on one small lab application, with different builds during the day; most runs were stopped once the check passed. Findings counts are therefore not comparable across models and say nothing about coverage.
- **Infrastructure noise**: intermittent TLS resets (ECONNRESET) on the path to the Foundry regional gateway ended several runs (GPT and Kimi alike); whether the cause was the test network or the gateway is UNKNOWN. 429 rate limits depend on the deployment quota, not on Darkmoon.
- **Early end of turn**: on `gpt-5.3-codex`, several Pro runs ended after about 30 s with 0 commands because the model ended its turn without a tool call; those runs are recorded as aborted, not as results.
- **Content filters**: Azure's default content filter blocked one sub-agent response (Kimi). A custom filter policy (harm thresholds at High, jailbreak shield annotate-only) was attached to one deployment; its effect was not measured (UNKNOWN).
- **No independent reproduction**, no published raw logs, estimated (not billed) costs.

## Relation to the published Darkmoon reports

The published Darkmoon lab reports indexed in the [leaderboard](./index.md) were run on `claude-opus-4-6` (see the leaderboard's reading notes); this page adds no result to them and changes none. The multi-run, protocol-based comparison of model labels on OWASP Juice Shop is the study [`studies/llm-pentest-juice-shop-2026`](../studies/llm-pentest-juice-shop-2026/).
