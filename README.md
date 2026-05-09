# MCP Sentinel Dashboard

> Live governance dashboard for **MCP Sentinel** — observability, security audit, and policy visibility for Model Context Protocol servers.

[![CI](https://github.com/mizcausevic-dev/mcp-sentinel-dashboard/actions/workflows/ci.yml/badge.svg)](https://github.com/mizcausevic-dev/mcp-sentinel-dashboard/actions/workflows/ci.yml)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-10B981.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Live demo](https://img.shields.io/badge/demo-mcp.kineticgain.com-10B981.svg)](https://mcp.kineticgain.com)
[![React](https://img.shields.io/badge/React-19-10B981.svg)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-10B981.svg)](https://www.typescriptlang.org/)

The visual surface for the [`mcp-sentinel`](https://github.com/mizcausevic-dev/mcp-sentinel) governance engine. Real-time-shaped UX showing what enterprise MCP server oversight looks like — registration validation, tool-surface scans for prompt injection, PII isolation, schema drift detection, and a posture score recruiters and security teams can read in 5 seconds.

> **MCP** = [Model Context Protocol](https://modelcontextprotocol.io), the open spec from Anthropic for letting AI agents talk to external tools, files, and APIs in a standardized way. As the protocol gets adopted across Claude, Cursor, Zed, Continue and others — the question of **who's auditing those servers** becomes critical. This dashboard answers it.

---

## Live demo

[**mcp.kineticgain.com**](https://mcp.kineticgain.com) — interactive preview of the governance UX.

---

## What you see

| Surface | What it shows |
|---|---|
| **Global Overview** | Active guards, filtered request count, threat score, average latency. The 30-second posture summary. |
| **Sentinel Shield Activity Overlay** | Animated traffic visualization — incoming RPC calls flowing through the validation layer. WAF bypass attempts, sensitive-leak markers, and safe-buffer requests rendered as labels orbiting the shield core. |
| **Interception Log** | Real-time-shaped log feed with `[INFO] / [PASS] / [BLCK] / [IDLE]` tagging. Visible at-a-glance whether the sentinel is doing work. |
| **Repo Intelligence** | Inspect any file in the sentinel codebase — selected file shows risk level, drift detection score, PII isolation %, and a contextual code preview with policy-aware syntax highlighting. |

---

## Why this exists

Modern AI platforms ship MCP servers fast. Most of them have **no audit layer**. The sentinel project answers the platform-engineering version of "who's watching the watchers." This dashboard is what that oversight looks like in production, presented as a single-page operator surface that:

- **CISO can show to the board** in a posture review
- **Platform engineers can dock to a wall** in their war room
- **Hiring managers can read in 30 seconds** during a portfolio review

---

## Stack

| Layer | Tech |
|---|---|
| Framework | React 19 + Vite 6 |
| Language | TypeScript 5.8 |
| Styling | Tailwind 4 (CSS variable theme) |
| Animations | Motion (framer-motion successor) |
| Icons | Lucide React |
| Fonts | IBM Plex Sans / Mono / Serif |
| Theme | Black + emerald — the security-UI semiotic (green = safe, red = blocked, amber = preview) |

---

## Quick start

```bash
git clone https://github.com/mizcausevic-dev/mcp-sentinel-dashboard.git
cd mcp-sentinel-dashboard
npm install
npm run dev
```

Open http://localhost:3000.

### Build for production

```bash
npm run build      # tsc + vite build → dist/
npm run preview    # serve dist/ locally to test
```

---

## Roadmap

### v0.1 — *Shipped*
- [x] Governance dashboard UX (Architecture + Repo Intelligence tabs)
- [x] Animated Sentinel Shield activity overlay
- [x] Interception log feed with semantic tagging
- [x] Protocol-aware code viewer with policy highlighting
- [x] AGPL-3.0 license + CI matrix on Node 20 / 22

### v0.2 — *Next*
- [ ] **Live MCP server scanning** — paste a server URL, get a real audit
- [ ] Real heuristics for prompt injection patterns (templated against the [MCP spec](https://modelcontextprotocol.io))
- [ ] Backend proxy (Cloudflare Workers) for cross-origin server inspection
- [ ] Posture-score history tracking (KV-backed)

### v0.3 — *Product*
- [ ] Multi-server fleet view (compare posture across N servers)
- [ ] Webhook / Slack alerts on drift or blocked-call anomalies
- [ ] Scheduled re-audits with diff reports
- [ ] Exportable PDF posture report for compliance reviewers

### v1.0 — *Commercial*
- [ ] SaaS tiers (Free per-server / Pro / Team)
- [ ] Enterprise feature: org-wide MCP server inventory + compliance attestations
- [ ] White-label / on-prem deploys

---

## Companion repository

This dashboard is the visual surface for [`mcp-sentinel`](https://github.com/mizcausevic-dev/mcp-sentinel) — the actual TypeScript implementation of the governance engine. The two are deliberately split:

- **`mcp-sentinel`** = the engine (validators, schema scanners, audit logic)
- **`mcp-sentinel-dashboard`** = the UX (this repo)

Run them together for a complete preview, or run the dashboard standalone to showcase the UX.

---

## License

**AGPL-3.0-only**. See [LICENSE](LICENSE).

The AGPL means: you can fork, modify, and self-host this — but if you run a modified version as a service, you must publish your source. This protects the project's monetization runway while keeping it genuinely open-source for individuals and security teams.

For commercial licensing inquiries (closed-source forks, white-label deployments, on-prem with proprietary modifications), contact: **miz@kineticgain.com**

---

## Author

**Miz Causevic** — Director of Web Engineering · Platform Architecture
[mizcausevic-dev.github.io](https://mizcausevic-dev.github.io/) · [github.com/mizcausevic-dev](https://github.com/mizcausevic-dev) · [gv.kineticgain.com](https://gv.kineticgain.com)
