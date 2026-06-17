![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png)

**NullRun** is an enforcement platform for AI agents — a set of products that
let teams ship agents without losing control of cost, scope, or behaviour.

## Products

- **Breaker** — cost control + circuit breaker for agent runs (the flagship)
- **Gate** — tool/action security layer (policy-bound execution)
- **Flow** — durable workflow runtime with retry, pause, resume
- **Vault** — secrets + signed credentials for agent-side calls
- **Trace** — execution telemetry and audit log
- **Policy** — declarative rules with first-match-wins composition
- **Signal** — anomaly detection on agent behaviour (loops, retry storms, drift)

## Core architecture

Every product is built on three shared layers:

- **Detectors** — real-time behavioural monitoring (loops, retry storms, rate limits, budget, anomalies)
- **Enforcement Engine** — hard runtime constraints (invariants, capability tokens, policies, per-agent boundaries)
- **Decision Engine** — confidence scoring + action levels (Observe / Warn / Block / Degrade), plan-aware

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

## Design philosophy

- **Prevent** cost explosions, don't just report them
- Treat agents as **untrusted** execution systems
- Enforce constraints **in real time**, not after logs
- Make enforcement **deterministic** and **auditable**

## Where to start

- Managed control plane: https://app.nullrun.io
- API: https://api.nullrun.io
- Self-host the gateway: https://github.com/nullrunio/nullrun
- Python SDK: https://github.com/nullrunio/nullrun-sdk-python (`pip install nullrun`)
- Examples: https://github.com/nullrunio/nullrun-examples
- Docs: https://github.com/nullrunio/nullrun-docs (https://docs.nullrun.io)
