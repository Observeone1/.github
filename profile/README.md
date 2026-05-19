# ObserveOne

Website monitoring with Playwright Autopilot. Point it at a URL and it generates a real browser test suite for you. Add URL, API, and heartbeat monitoring, incidents, and status pages — run all of it from a dashboard or entirely from the CLI.

[![Website](https://img.shields.io/badge/website-observeone.com-2563eb)](https://www.observeone.com)
[![npm](https://img.shields.io/npm/v/@observeone/cli?label=%40observeone%2Fcli)](https://www.npmjs.com/package/@observeone/cli)
[![License](https://img.shields.io/badge/core-Apache_2.0-blue)](https://github.com/Observeone1/oo-workers/blob/main/LICENSE)

## Open source

| Repo | What it is |
|------|-----------|
| **[oo-workers](https://github.com/Observeone1/oo-workers)** | The monitoring engine, self-hosted. Real Playwright browser checks and JSONPath assertions. If you've run Uptime Kuma and wished it could drive a browser, this is that. `Apache-2.0` |
| **[ObserveOne CLI](https://github.com/Observeone1/ObserveOne-CLI)** | Monitors, API checks, heartbeats, incidents, and status pages from the terminal. The config is JSON, so it lives in git like everything else. `Apache-2.0` |
| **[browser-use](https://github.com/Observeone1/browser-use)** | Our fork of the browser-use library for AI-driven browser automation. We track upstream and patch here. `MIT` |

## What you get

- **Playwright Autopilot.** Point it at a URL and it generates the browser test suite for you, running on real Chromium. When a test breaks because your UI moved, it tries to fix the selector instead of just going red.
- **URL, API, and heartbeat monitoring** in one place — uptime, endpoint checks, and cron liveness.
- **Incidents and public status pages.** Open, assign, resolve.
- **It's all JSON.** `obs export` pulls your whole setup; `obs apply` puts it back. Commit it, diff it, review it like code.
- **CI that fails the build.** GitHub App with PR comments and merge blocking. GitLab and plain webhooks work too.

## Quick start

**SaaS** — free plan, no card → **[app.observeone.com](https://app.observeone.com)**

**Self-hosted** — your own engine on Docker, Postgres, and Redis → **[oo-workers](https://github.com/Observeone1/oo-workers)**

**CLI**

```bash
npm install -g @observeone/cli
obs login
obs export                 # pull your monitoring stack as JSON
obs apply observeone.json  # commit it, GitOps it
```

## How it's built

A few moving parts:

- Express API on Supabase Postgres
- Playwright workers on BullMQ, split by region — that's [oo-workers](https://github.com/Observeone1/oo-workers)
- Next.js dashboard, with SSE so runs stream live
- TypeScript CLI that speaks strict JSON in and out, so agents and CI can parse it

## License

oo-workers and the CLI are Apache 2.0. The hosted platform isn't open source. Each repo states its own license.

— [observeone.com](https://www.observeone.com)
