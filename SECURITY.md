# Security Policy

## Supported Versions

NullRun is shipping in alpha. Only the latest minor version receives security
updates. Older versions are not patched.

| Version   | Supported          |
| --------- | ------------------ |
| 0.6.x     | :white_check_mark: |
| 0.5.x     | :white_check_mark: |
| < 0.5     | :x:                |

## Reporting a Vulnerability

**Please do not file public issues for security problems.**

Email: **support@nullrun.io** (same inbox as general support — no
separate security alias today)

We will acknowledge receipt within 48 hours and aim to ship a fix or
mitigation within 14 days for critical issues. We coordinate disclosure
timing with reporters.

When reporting, please include:
- A clear description of the vulnerability
- Steps to reproduce (proof of concept preferred)
- Affected component (`nullrun` backend, `nullrun-sdk-python`, `nullrun-docs`,
  examples, etc.) and version
- Potential impact

## Scope

In scope:
- The NullRun gateway and dashboard (private repo).
- `nullrun-sdk-python` — Python SDK (`nullrun` 0.6.0 on PyPI).
- `nullrun-docs` — documentation site.
- `nullrun-examples` — example code.

Out of scope:
- Third-party dependencies (please report upstream)
- Social-engineering attacks against staff
- Denial of service against the marketing site
- Network/infrastructure issues outside our control

## Recognition

We maintain a private acknowledgement list and will credit reporters in the
release notes on https://nullrun.io/changelog unless anonymity is requested.
