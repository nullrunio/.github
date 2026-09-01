![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png)

# Ship AI agents. Stay in control.

NullRun is the runtime decision layer for tool-using AI agents. Drop in a
one-line decorator, set a budget, and govern cost, tool use, and workflow
state before a runaway agent turns into an incident.

**Managed runtime control plane. Not a self-hosted deployment.**

## Why teams use NullRun

- **Stop runaway costs.** Hard budget policies stop a workflow at the cap.
  Soft policies can allow a bounded overdraft for an active chain — but
  only when the policy uses `enforcement_mode = Soft`, an active
  `chain_id` exists, and the projected cost stays within the configured
  overdraft limit.
- **Action-bound approvals.** Approval rules can match against a typed
  action payload (a money amount or a tool-call argument bag). Every
  approval is bound by a SHA-256 digest of the exact payload — the gate
  refuses to honour the grant if a later `/execute` arrives with a
  different amount or different arguments.
- **Control from the dashboard.** Pause or kill a workflow through the
  WebSocket control plane. Signals are applied at the next gate or yield
  boundary.
- **Govern sensitive tools safely.** Database writes, shell, file
  deletes, and external actions can be blocked by ToolBlock policies or
  routed through human approval, with a full audit trail.

## SDK coverage

The Python SDK is the only runtime client for the agent hot path.
Integration coverage varies by framework:

- **End-to-end tested** (decorator plus dedicated behaviour tests):
  LangGraph, CrewAI, AutoGen, LlamaIndex.
- **HTTP transport tested**: OpenAI.
- **Decorator implemented, no dedicated end-to-end test**: OpenAI
  Agents, LangChain, Anthropic.
- **Extractor unit-tested, no full transport-to-track integration
  test**: Mistral, Gemini, Cohere, AWS Bedrock.

## Get started

- **[nullrun.io](https://nullrun.io)** — managed control plane and
  dashboard in one place. Start with the Lite plan, no credit card.
- **`pip install nullrun`** — Python SDK (0.14.x). Pass your
  `nr_live_...` API key to `init()` to start tracking and enforcing
  policy.
- **[docs.nullrun.io](https://docs.nullrun.io)** — install, quickstart,
  concepts, and recipes.

## Trust boundary

NullRun evaluates structured action requests before execution and returns
`allow`, `block`, or `require_approval`. It does not inspect prompts or
raw semantic content; tool-block policies match tool names only, and
approval rules predicate over typed, explicitly forwarded tool
parameters — never arbitrary payloads. Cost enforcement relies on
SDK-reported estimates and usage — a malicious SDK that controls its
own cost reports is not protected by the gate.

## Repositories

- **[nullrun-sdk-python](https://github.com/nullrunio/nullrun-sdk-python)** —
  the Python SDK (`pip install nullrun`).
- **[nullrun-docs](https://github.com/nullrunio/nullrun-docs)** —
  the documentation site.
- **[nullrun-examples](https://github.com/nullrunio/nullrun-examples)** —
  copy-paste-runnable examples for the most common agent frameworks.

## Get in touch

- **Bug or feature?** Open an issue in the relevant repo.
- **Security?** See
  [SECURITY.md](https://github.com/nullrunio/.github/blob/main/SECURITY.md)
  — please don't file public issues.
- **General questions:** [Discord](https://discord.gg/N63ECwnV3) is the
  fastest channel.
- **Email support:** [support@nullrun.io](mailto:support@nullrun.io).
