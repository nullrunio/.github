<div align="center">

![NullRun banner](https://raw.githubusercontent.com/nullrunio/.github/main/images/gh_banner.png)

# NullRun

**Runtime authorization for AI agents.**

Decide which agent actions are allowed to execute before they reach production systems.

</div>

---

```
   AI Agent
      │
      │  tool call
      ▼
   ┌──────────┐
   │ NullRun  │
   │   Gate   │
   └────┬─────┘
        │
        ├── ALLOW ────────────► Tool executes
        ├── REQUIRE APPROVAL ─► Human decides
        └── BLOCK ─────────────► Tool does not execute
```

## Start here

| I want to... | Open |
| --- | --- |
| Install the SDK | **[nullrun-sdk-python](https://github.com/nullrunio/nullrun-sdk-python)** · `pip install nullrun` |
| See it running | **[nullrun-examples](https://github.com/nullrunio/nullrun-examples)** · LangGraph, CrewAI, MCP, … |
| Read the docs | **[docs.nullrun.io](https://docs.nullrun.io)** · concepts, how-to, API reference |
| Manage policies | **[nullrun.io](https://nullrun.io)** · dashboard and control plane |

## Releases

[![Latest release](https://img.shields.io/github/v/release/nullrunio/nullrun-sdk-python?display_name=tag&sort=semver&style=for-the-badge)](https://github.com/nullrunio/nullrun-sdk-python/releases)
[![PyPI](https://img.shields.io/pypi/v/nullrun?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/nullrun/)
[![Python 3.10+](https://img.shields.io/pypi/pyversions/nullrun?style=for-the-badge&logo=python&logoColor=white)](https://pypi.org/project/nullrun/)
[![Apache-2.0](https://img.shields.io/github/license/nullrunio/nullrun-sdk-python?style=for-the-badge)](https://github.com/nullrunio/nullrun-sdk-python/blob/master/LICENSE)

[All SDK releases →](https://github.com/nullrunio/nullrun-sdk-python/releases)

## What NullRun enforces

- **Tool policies** — block sensitive tools before execution.
- **Spend limits** — hard and soft budgets, chain-aware overdraft, rate caps.
- **Human approval** — action-bound grants via SHA-256 payload digest.
- **Workflow control** — pause / kill from the dashboard over WebSocket.
- **Audit trail** — hash-chained `audit_events` for every gate decision.

## Trust boundary

NullRun evaluates structured action requests — `allow`, `require_approval`, `block`. It does **not** inspect prompts or arbitrary semantic content; tool-block policies match tool names only, and approval rules predicate over typed, explicitly forwarded tool parameters. Cost enforcement relies on SDK-reported usage — a malicious SDK that controls its own cost reports is not protected by the gate.

## Repositories

- **[nullrun-sdk-python](https://github.com/nullrunio/nullrun-sdk-python)** — Python SDK (Apache-2.0, `pip install nullrun`).
- **[nullrun-docs](https://github.com/nullrunio/nullrun-docs)** — documentation source.
- **[nullrun-examples](https://github.com/nullrunio/nullrun-examples)** — runnable agent integrations.
- **`nullrun`** — gateway and dashboard. Private; access on request.

## Support

- **Bug or feature?** Open an issue in the relevant repo.
- **Security?** See [SECURITY.md](./SECURITY.md) — please don't file public issues.
- **Email:** [support@nullrun.io](mailto:support@nullrun.io).
