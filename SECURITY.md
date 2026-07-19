# Security Policy

Last reviewed: 2026-07-19

## Supported Versions

NullRun is currently in alpha. Security fixes are applied to the latest
minor SDK release. Older minor releases may not receive security fixes.

| Version | Supported          |
| ------- | ------------------ |
| 0.13.x  | :white_check_mark: |
| < 0.13  | :x:                |

The hosted gateway and dashboard are continuously deployed. When reporting
an issue that involves the gateway, include the deployed version returned by
`/health` or `/healthz`.

## Reporting a Vulnerability

**Please do not file public issues for security problems.**

Email: **support@nullrun.io** (the same inbox is used for general support;
there is no separate security alias today).

We will acknowledge receipt within 48 hours and aim to ship a fix or
mitigation within 14 days for critical issues. We coordinate disclosure
timing with reporters.

When reporting, please include:
- A clear description of the vulnerability
- Steps to reproduce (proof of concept preferred)
- Affected component (`nullrun` gateway, `nullrun-sdk-python`,
  `nullrun-docs`, examples, etc.) and version
- Potential impact

Please do not include API keys, HMAC secrets, credentials, prompts,
completions, or other private customer data in a report. Redact sensitive
values in logs and reproduction snippets.

## Scope

In scope:
- The NullRun gateway and dashboard (private repo).
- `nullrun-sdk-python` — Python SDK (`nullrun` 0.13.x on PyPI).
- `nullrun-docs` — documentation site.
- `nullrun-examples` — example code.

Out of scope:
- Third-party dependencies (please report upstream)
- Social-engineering attacks against staff
- Denial of service against the marketing site
- Network/infrastructure issues outside our control

## Recognition

We maintain a private acknowledgement list and may credit reporters in the
relevant public release notes unless anonymity is requested.
