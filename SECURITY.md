# Security Policy

## Supported Versions

NullRun is shipping in alpha. Only the latest minor version receives security
updates. Older versions are not patched.

| Version | Supported          |
| ------- | ------------------ |
| 0.3.x   | :white_check_mark: |
| < 0.3   | :x:                |

## Reporting a Vulnerability

**Please do not file public issues for security problems.**

Email: **security@nullrun.io**

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
- `nullrunio/nullrun` — gateway (Rust)
- `nullrunio/nullrun-sdk-python` — Python SDK
- `nullrunio/nullrun-docs` — documentation
- `nullrunio/nullrun-examples` — example code

Out of scope:
- Third-party dependencies (please report upstream)
- Social-engineering attacks against staff
- Denial of service against the marketing site

## Recognition

We maintain a private acknowledgement list and will credit reporters in the
relevant CHANGELOG unless anonymity is requested.
