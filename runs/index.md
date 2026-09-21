<div align="center">

# The Darkmoon AI-Pentester Leaderboard

### Autonomous AI penetration testing benchmark, honest AI security testing numbers across web, cloud, infrastructure and IoT labs

[![Star Dark-Moon](https://img.shields.io/github/stars/ASCIT31/Dark-Moon?style=social)](https://github.com/ASCIT31/Dark-Moon)

**Every row below is a real Darkmoon run against a named, reproducible lab. Every finding count and exploited count is copied from that lab's full report (linked in the last column), where the same numbers appear in the report's own Findings Summary table. Nothing on this page is estimated.**

[**Star Darkmoon**](https://github.com/ASCIT31/Dark-Moon) · [**Full evidence corpus**](https://github.com/ASCIT31/darkmoon-research) · [**dark-moon.org**](https://dark-moon.org)

</div>

---

## How to read this leaderboard

- **Surface**: web, cloud, infra (databases, CI/CD, secret stores, IaC), or iot.
- **Findings (C/H/M/L)**: distinct vulnerabilities by severity (Critical / High / Medium / Low), taken from the linked report's Findings Summary table.
- **Exploited**: findings the agent actively exploited with proof (a stricter bar than merely confirmed).
- **Full report**: the complete per-lab report, with one section per finding and evidence, in the sibling [darkmoon-research](https://github.com/ASCIT31/darkmoon-research) corpus. This index links out, it does not duplicate that content.

Finding and proof-of-exploitation are the open source CLI's job (local, black-box, privacy-preserving). The web dashboard and automated remediation to reviewed pull requests are Darkmoon **Pro** (paid) features, labeled wherever they appear.

---

## Leaderboard

| Lab | Surface | Findings (C/H/M/L) | Exploited | Duration | Model | Full report |
|---|:--:|:--:|:--:|:--:|:--:|---|
| OWASP Juice Shop | web | **57** (8/24/21/4) | proof per finding | 28.5 min | local (Ollama/llama.cpp) | [runs/juice-shop-2026-04-26.md](./juice-shop-2026-04-26.md) |
| AWS account (public EBS snapshot + S3 + IAM) | cloud | **9** (0/2/5/2) | 0 | n/r | opus-4-6 | [cloud/aws-pwnedlabs-online.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/aws-pwnedlabs-online.md) |
| AWS S3 anonymous to IT-admin chain | cloud | **9** (5/1/2/1) | 5 | n/r | opus-4-6 | [cloud/aws-s3-huge-logistics.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/aws-s3-huge-logistics.md) |
| Azure Entra ID priv-esc (helpdesk to Global Admin) | cloud | **19** (8/6/5/0) | 11 | n/r | opus-4-6 | [cloud/azure-bloodhound-pwnedlabs.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/azure-bloodhound-pwnedlabs.md) |
| Azure Entra ID tenant takeover (deleted-blob recovery) | cloud | **28** (11/10/4/3) | 12 | n/r | opus-4-6 | [cloud/azure-entra-pwnedlabs.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/azure-entra-pwnedlabs.md) |
| Azure Key Vault to PCI data exfiltration | cloud | **7** (3/2/2/0) | 4 | n/r | opus-4-6 | [cloud/azure-keyvault-confirm.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/azure-keyvault-confirm.md) |
| Azure Key Vault RBAC over-permission | cloud | **16** (2/6/8/0) | 6 | n/r | opus-4-6 | [cloud/azure-keyvault-pwnedlabs.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/azure-keyvault-pwnedlabs.md) |
| GCP SSRF to metadata token to GCS exfil | cloud | **4** (3/1/0/0) | 3 | n/r | opus-4-6 | [cloud/gcp-ssrf-gopher-pwnedlabs.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/gcp-ssrf-gopher-pwnedlabs.md) |
| GCP public GCS backup archive exfil | cloud | **5** (3/1/1/0) | 4 | n/r | opus-4-6 | [cloud/gcp-storage-pwnedlabs.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/cloud/gcp-storage-pwnedlabs.md) |
| GitLab CE 19.2.1 (admin PAT, CI/CD secrets) | infra | **26** (4/8/10/2) [^info] | 2 | n/r | opus-4-6 | [infrastructure/gitlab.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/gitlab.md) |
| Redis 7.4.10 (unauthenticated) | infra | **9** (3/5/1/0) | 5 | n/r | opus-4-6 | [infrastructure/messaging-cache_redis.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/messaging-cache_redis.md) |
| PostgreSQL 16 + MySQL 5.6 | infra | **22** (6/10/6/0) | 13 | n/r | opus-4-6 | [infrastructure/sql-databases_pg-mysql.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/sql-databases_pg-mysql.md) [^assembled] |
| Terraform state + AWS + Ansible (IaC) | infra | **34** (21/5/8/0) | 16 | n/r | opus-4-6 | [infrastructure/terraform-aws-ansible.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/terraform-aws-ansible.md) |
| HashiCorp Vault + OCI Registry + Docker Engine | infra | **41** (15/15/9/2) | 8 | n/r | opus-4-6 | [infrastructure/vault-registry-docker.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/vault-registry-docker.md) |
| Jenkins 2.541.3 (unauthenticated) | infra | **3** (3/0/0/0) | 3 | n/r | opus-4-6 | [infrastructure/jenkins.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/infrastructure/jenkins.md) [^assembled] |
| OWASP IoTGoat (live device) | iot | **9** (4/3/2/0) | 3 | n/r | opus-4-6 | [iot/iotgoat-device-live.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/iot/iotgoat-device-live.md) |
| OWASP IoTGoat (firmware image) | iot | **20** (4/7/7/2) | 1 | n/r | opus-4-6 | [iot/iotgoat-firmware-image.md](https://github.com/ASCIT31/darkmoon-research/blob/main/reports/iot/iotgoat-firmware-image.md) |

[^info]: GitLab CE additionally carries 2 informational findings, so the report's Findings Summary total is 26.
[^assembled]: The compiled server report generator returned a 500 for this campaign (a stale-reconciler flipped the long-running campaign to `stopped` before finalize completed, see the Darkmoon end-to-end validation notes). The report was assembled from the agent's pushed findings using the same schema, so every finding keeps its full per-finding evidence. Counts here come from that assembled report.

### Reading notes

- **Duration**: `n/r` means the per-lab report does not record a wall-clock time. Only the OWASP Juice Shop run page records a duration (28.5 min), so that is the only duration published here. No run time is estimated for the other labs.
- **Model**: the lab reports (cloud, infra, iot) are the Pro-stack validation wave recorded in the Darkmoon end-to-end validation results (`E2E-RESULTS.md`), which documents that wave running on model `claude-opus-4-6` (shown here as `opus-4-6`). The OWASP Juice Shop row was run on a local model (Ollama/llama.cpp) per its run page, a deliberate choice that proves the tool works without sending target data to a third party.
- **Findings totals** are taken from each report's own Findings Summary table (the same table also reports the exploited count). Where a report also prints a `TOTAL` row, it matches the numbers above.

---

## Totals

Across the 16 named lab reports in the [darkmoon-research](https://github.com/ASCIT31/darkmoon-research) corpus (cloud, infra, iot): **261 findings, 96 of them exploited with proof**. The OWASP Juice Shop web run adds **57 findings** (proof of exploitation per finding). Reproduce or contest any row by reading its linked report and running the target yourself.

---

## Add your tool or your lab

This is a community leaderboard, not a marketing page. Open a PR with a named, reproducible lab, per-severity finding counts, exploited count, LLM location (local or cloud), and a link to the full report or raw output. We merge honest, reproducible runs. We do not claim anyone cheats, we publish every condition in the open.

<div align="center">

[**⭐ Star Darkmoon, the open source autonomous AI penetration testing platform**](https://github.com/ASCIT31/Dark-Moon)

</div>
