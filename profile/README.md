# ObserveOne

**AI-powered website monitoring, synthetic testing, and monitoring-as-code.**

Describe what to check in plain English. We open a real browser, run your flows, and alert you the moment something breaks — with video replay on every run.

[![Website](https://img.shields.io/badge/website-observeone.com-2563eb)](https://www.observeone.com)
[![npm](https://img.shields.io/npm/v/@observeone/cli?label=%40observeone%2Fcli)](https://www.npmjs.com/package/@observeone/cli)
[![License](https://img.shields.io/badge/core-Apache_2.0-blue)](https://github.com/Observeone1/oo-workers/blob/main/LICENSE)

---

## Open Source

| Repo | What it is |
|------|-----------|
| **[oo-workers](https://github.com/Observeone1/oo-workers)** | Self-hosted monitoring engine — real browser checks (Playwright) + JSONPath assertions. An Uptime Kuma alternative you actually own. `Apache-2.0` |
| **[ObserveOne CLI](https://github.com/Observeone1/ObserveOne-CLI)** | Manage monitors, API checks, heartbeats, incidents & status pages from your terminal. Monitoring-as-code. `Apache-2.0` |
| **[browser-use](https://github.com/Observeone1/browser-use)** | Our fork of `browser-use` — the agent layer that lets AI drive real browsers for synthetic flows. `MIT` |

---

## What ObserveOne Does

- **AI Browser Checks** — Describe a flow in plain English. We run real Chromium and return pass/fail with a video.
- **Playwright Autopilot** — Paste a URL, get a generated test suite. Selectors self-heal when your UI changes.
- **URL, API & Heartbeat Monitoring** — Uptime, endpoint validation, and cron-job liveness from one place.
- **Incidents & Status Pages** — Open, assign, resolve. Public status pages included.
- **Monitoring-as-Code** — `obs export` / `obs apply` your entire stack as JSON. GitOps-ready, agent-friendly.
- **CI/CD Integration** — GitHub App triggers, PR comments, merge blocking. GitLab and webhooks too.

---

## Quick Start

**SaaS** — free plan, no credit card → **[app.observeone.com](https://app.observeone.com)**

**Self-hosted** — your own engine on Docker + Postgres + Redis → **[oo-workers](https://github.com/Observeone1/oo-workers)**

**CLI**
```bash
npm install -g @observeone/cli
obs login
obs export                 # pull your whole monitoring stack as JSON
obs apply observeone.json  # commit it, GitOps it
```

---

## Architecture

A distributed system:

- **Backend** — Express.js API on Supabase Postgres
- **Workers** — Regional BullMQ workers running Playwright browsers ([oo-workers](https://github.com/Observeone1/oo-workers))
- **Frontend** — Next.js dashboard with live SSE streaming
- **CLI** — TypeScript with strict JSON envelopes for agent/CI consumption ([ObserveOne CLI](https://github.com/Observeone1/ObserveOne-CLI))

---

## License

Open-source projects are **Apache 2.0** (`oo-workers`, `ObserveOne CLI`). The hosted SaaS platform is proprietary. See each repo for its license.

— [observeone.com](https://www.observeone.com)
