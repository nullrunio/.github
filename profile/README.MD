![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png)

# Ship AI agents. Stay in control.

NullRun is the enforcement layer for AI agents. Drop in a one-line
decorator, set a budget, and your agent stops when cost spirals,
loops, or risky tool calls — before the bill lands, not after.

## Why teams use NullRun

- **Stop runaway costs.** Hard budget caps on every workflow. The
  agent halts the moment the cap is hit, not in next week's report.
- **Catch loops and retry storms.** Loops, retry storms, and
  over-eager tools are detected and blocked mid-run, not after
  the API bill does the talking.
- **Kill from the dashboard.** When something goes wrong, hit
  **Kill** and the agent stops within milliseconds — even
  mid-execution. WebSocket control plane, not polling.
- **Run sensitive tools safely.** Database writes, shell, file
  deletes — gate each one with an explicit policy. Approvals,
  allow-lists, full audit trail.

## Get started

- 🟢 **[nullrun.io](https://nullrun.io)** — managed control plane
  and dashboard in one place. Free Lite plan, no credit card.
- 🐍 **`pip install nullrun`** — Python SDK with one-line
  instrumentation for OpenAI, Anthropic, OpenAI Agents, LangGraph,
  and the rest. Pass your `nr_live_...` API key to `init()` to
  start tracking.
- 📖 **[docs.nullrun.io](https://docs.nullrun.io)** — install,
  quickstart, concepts, and recipes.

## Repositories

- **[nullrun-sdk-python](https://github.com/nullrunio/nullrun-sdk-python)** —
  the Python SDK (`pip install nullrun`).
- **[nullrun-docs](https://github.com/nullrunio/nullrun-docs)** —
  the documentation site.
- **[nullrun-examples](https://github.com/nullrunio/nullrun-examples)** —
  copy-paste-runnable examples for the most common agent
  frameworks.

## Get in touch

- 🐛 **Bug or feature?** Open an issue in the relevant repo.
- 🔒 **Security?** See
  [SECURITY.md](https://github.com/nullrunio/.github/blob/main/SECURITY.md)
  — please don't file public issues.
- 💬 **Anything else:** [support@nullrun.io](mailto:support@nullrun.io).
