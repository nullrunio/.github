![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png)

**NullRun** is an enforcement platform for AI agents — a set of products that
let teams ship agents without losing control of cost, scope, or behaviour.

## Products

NullRun ships as a single binary (`breaker-core`) plus the SDK
(`pip install nullrun`) and the dashboard (`breaker-dashboard`).
Conceptually the platform covers:

- **Breaker** — cost control + circuit breaker for agent runs. The
  flagship. (`backend/src/{admission, cost, enforcement}`)
- **Gate** — unified enforcement endpoint (`/api/v1/gate`) that
  combines budget pre-flight, policy evaluation, and sensitive-tool
  decision in a single call. Backed by the policy engine
  (`backend/src/policy`).
- **Vault** — provider credential vault (`backend/src/security`).
  Stores LLM-provider API keys, encrypts at rest with pgcrypto, and
  logs every credential access (`CredentialAccessLog`). Distinct from
  `entitlement`, which is the capability-based authorisation model
  for agent-side tool calls.
- **Trace** — execution telemetry, audit log, and decision history.
  `backend/src/{observability, audit, decision_history}`.
- **Policy** — declarative rules with first-match-wins composition
  (ADR-007). The `policy` module's evaluation graph.
- **Signal** — real-time behavioural detectors
  (`backend/src/detectors`): loops, retry storms, rate limits, and
  budget breaches. Anomaly detection is loop / retry focused — the
  broader "drift" signal that earlier marketing mentioned is **not**
  shipped (the `drift_detection` feature key was removed from
  canonical plan rows by migration 136_plan_rebalance_v2 in
  `backend/src/db/mod.rs:3392`).
- **Kill / Pause** — operator-initiated workflow termination over
  the WebSocket control plane (`backend/src/actions/{kill, pause}`)
  and the dashboard Workflows panel. Pairs with Breaker.

> Earlier versions of this file also listed a "Flow" product —
> "durable workflow runtime with retry, pause, resume". That
> capability is **not** a separate module. The `streaming` module
> (`backend/src/streaming`) is a streaming state machine + governance
> layer, not a durable workflow runtime, and retry/pause live in the
> `actions` module wired to the control plane. We've folded those
> concerns into **Kill / Pause** above and removed "Flow" from the
> product list to keep the marketing in lockstep with the code.

## Core architecture

Every product is built on three shared layers:

- **Detectors** (`backend/src/detectors`) — real-time behavioural
  monitoring: loops, retry storms, rate limits, budget breaches.
  The detectors surface signals to the policy engine.
- **Enforcement Engine** (`backend/src/{enforcement, admission}`)
  — hard runtime constraints: per-workflow budgets, plan-derived
  limits, capability tokens, and per-agent boundaries. This is the
  gate that runs synchronously on every `@protect`-wrapped call.
- **Decision Engine** (`backend/src/decision_engine`) — the
  truth-to-action mapping layer (Phase 3.5). It evaluates the
  detector signals against the resolved policy and returns a
  single decision (`allow` / `block` / `require_approval`) with a
  `decision_source` audit trail. The exact action taxonomy is
  defined in `decision_engine.rs`, not in this README — the
  Observe / Warn / Block / Degrade wording from earlier docs is
  aspirational and not the on-the-wire vocabulary.

## Why NullRun?

| Capability               | Existing tools | NullRun       |
| ------------------------ | -------------- | ------------- |
| Cost analytics           | ✅             | ✅            |
| Observability            | ✅             | ✅            |
| Circuit breakers         | ⚠️ Limited     | ✅ Native     |
| Loop / retry detection   | ❌             | ✅            |
| Capability tokens        | ❌ Rare        | ✅ Core       |
| Real-time enforcement    | ❌ Post-hoc    | ✅ Before exec|
| Agent-native design      | ❌             | ✅            |

> "Drift detection" is **not** currently a NullRun capability — see
> the Signal note above.

## Where to start

- Managed control plane: https://app.nullrun.io
- API: https://api.nullrun.io
- Self-host the gateway: https://github.com/nullrunio/nullrun
- Python SDK: https://github.com/nullrunio/nullrun-sdk-python (`pip install nullrun`)
- Examples: https://github.com/nullrunio/nullrun-examples
- Docs: https://github.com/nullrunio/nullrun-docs (https://docs.nullrun.io)
