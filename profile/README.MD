![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png)

# Ship AI agents. Stay in control.

NullRun is the runtime policy engine for AI agents. Drop in a one-line
decorator, set a budget, and govern cost, tool use, and workflow state
before a runaway agent turns into an incident.

## Why teams use NullRun

- **Stop runaway costs.** Hard budget policies stop a workflow at the
  cap. Soft policies can allow a bounded overdraft for an active chain,
  up to the configured overdraft limit.
- **Catch loops and retry storms.** Repeated tool calls and retry
  storms are detected during a run so the gate can block or flag them
  before the API bill does the talking.
- **Control from the dashboard.** Pause or kill a workflow through the
  WebSocket control plane. If the socket is unavailable, the SDK falls
  back to HTTP polling; signals are applied at the next gate or yield
  boundary, typically within about a second.
- **Govern sensitive tools safely.** Database writes, shell, file
  deletes, and external actions can be blocked by ToolBlock policies or
  routed through human approval, with a full audit trail.

## Get started

- 🟢 **[nullrun.io](https://nullrun.io)** — managed control plane
  and dashboard in one place. Start with the Lite plan, no credit card.
- 🐍 **`pip install nullrun`** — Python SDK with one-line
  instrumentation for OpenAI, Anthropic, OpenAI Agents, LangGraph,
  LangChain, LlamaIndex, CrewAI, AutoGen, Mistral, Gemini, Cohere,
  and AWS Bedrock. Pass your `nr_live_...` API key to `init()` to
  start tracking and enforcing policy.
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
- 💬 **General questions:** [Discord](https://discord.gg/N63ECwnV3) is the
  fastest channel.
- ✉️ **Email support:** [support@nullrun.io](mailto:support@nullrun.io).
