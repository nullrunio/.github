
![NullRun](https://github.com/nullrunio/.github/blob/main/images/gh_banner.png) 

**Real‑time enforcement layer** between AI agents and external tools (LLMs, APIs, DBs).  
Blocks uncontrolled costs, runaway loops, unsafe behaviour **before** execution – not after.

## Core layers

- **Detectors** – real‑time behavioural monitoring (loops, retry storms, rate limits, budget, anomalies)
- **Enforcement Engine** – hard runtime constraints (invariants, capability tokens, policies, per‑agent boundaries)
- **Decision Engine** – confidence scoring + action levels (Observe/Warn/Block/Degrade), plan‑aware

## Key features

- **Circuit breaker for agents** – auto‑halt runaway agents
- **Policy engine** – fine‑grained rules per workspace / agent / execution type
- **Capability tokens** – signed, bounded permissions
- **Cost intelligence** – real‑time + predictive cost attribution
- **Audit logging** – full traceability
- **Adaptive enforcemen**t – risk‑ and context‑aware rules
- **Multi‑tenant isolation**

## Why NullRun?

| Capability               | Existing tools | NullRun       |
| ------------------------ | -------------- | ------------- |
| Cost analytics           | ✅             | ✅            |
| Observability            | ✅             | ✅            |
| Circuit breakers         | ⚠️ Limited     | ✅ Native     |
| Loop / retry detection   | ❌             | ✅            |
| Capability tokens        | ❌ Rare        | ✅ Core       |
| Real‑time enforcement    | ❌ Post‑hoc    | ✅ Before exec|
| Agent‑native design      | ❌             | ✅            |

## Design philosophy

- **Prevent** cost explosions, don’t just report them
- Treat agents as **untrusted** execution systems
- Enforce constraints **in real time**, not after logs
- Make enforcement **deterministic** and **auditable**