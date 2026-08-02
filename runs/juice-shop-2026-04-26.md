# Darkmoon vs OWASP Juice Shop, raw run

- Campaign: `camp_20260426_3d2f`
- Target: 172.19.0.3, OWASP Juice Shop (Node.js/Express, Angular, Nginx), default image, black-box
- Date: 2026-04-26
- Duration: 28.5 min
- LLM: local (Ollama/llama.cpp)
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
