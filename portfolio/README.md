# PRESIDIO Hardened Public Portfolio

Public-facing snapshot of the PRESIDIO hardened component family: deployable hardened libraries, governance tools, cloud posture components, research artifacts, and flagship platforms. Non-public workspaces, scaffolding, and private repository URLs are intentionally omitted.

*Generated 2026-06-25T09:16:38Z from the public subset of `presidio-projects-overview`.*

## Metrics snapshot

| Public components | LOC | Installs | Commits (90d) | Changes (90d) | Churn (90d) | Deployments | PyPI publishers | Signed-tagged | Static-tested | Dynamic-tested |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 17 | 119.2k | 3.8k | 382 | 2334 | 163.5k | 32 | 13 | 11 | 16 | 17 |

![Public portfolio overview](overview.svg)

## Live deployments

| Component | Service | URL | Live since | Requests |
|---|---|---|---|---|
| x402 | x402 Screening API | [screen.presidio-group.eu](https://screen.presidio-group.eu) | Apr 2026 | — |

## Hardened Infrastructure

Drop-in hardened replacements for standard libraries and runtimes — the secure substrate an org deploys.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [crypto-channel](https://github.com/presidio-v/presidio-hardened-crypto-channel) | Frozen | `0.1.0` | 2026-06-11 | 959 LOC; 124 installs; 5 commits/90d; 31 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | Secure cryptographic channel demonstrating ECDH key exchange, AES-256-GCM |
| [esp32](https://github.com/presidio-v/presidio-hardened-esp32) | Frozen | `-` | 2026-06-11 | 3.5k LOC; 0 installs; 7 commits/90d; 13 changes; tests S/D; deploy; publish none; tags none | Add presidio-hardened-esp32 to any ESP-IDF v5.0+ project and your existing code |
| [fastapi](https://github.com/presidio-v/presidio-hardened-fastapi) | Frozen | `0.2.0` | 2026-06-11 | 2.7k LOC; 180 installs; 7 commits/90d; 29 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | A hardened, near drop-in replacement for FastAPI with strong security defaults. |
| [flask](https://github.com/presidio-v/presidio-hardened-flask) | Frozen | `0.2.0` | 2026-06-11 | 4.4k LOC; 152 installs; 10 commits/90d; 21 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | Hardened drop-in replacement for Flask with production security defaults applied automatically. |
| [opcua](https://github.com/presidio-v/presidio-hardened-opcua) | Frozen | `0.1.0` | 2026-06-11 | 3.2k LOC; 141 installs; 13 commits/90d; 22 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | Hardened OPC UA wrapper with Presidio security extensions. |
| [requests](https://github.com/presidio-v/presidio-hardened-requests) | Frozen | `0.2.0` | 2026-06-11 | 2.6k LOC; 106 installs; 5 commits/90d; 18 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | Hardened drop-in replacement for Python requests with secure defaults for TLS, timeouts, and defensive HTTP use. |
| [vuln-scanner](https://github.com/presidio-v/presidio-hardened-vuln-scanner) | Frozen | `0.1.0` | 2026-06-11 | 1.3k LOC; 150 installs; 7 commits/90d; 47 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 1/1 signed | Web application vulnerability scanner with a deliberately vulnerable Flask app |

## Cloud Posture & Translucency

Continuous audit of cloud workloads and architectural transparency over what is actually running.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [arch-translucency](https://github.com/presidio-v/presidio-hardened-arch-translucency) | Flagship | `0.17.0` | 2026-06-22 | 20.3k LOC; 997 installs; 64 commits/90d; 351 changes; tests S/D; deploy; publish PyPI+TP; tags 6/12 signed | Architecture transparency tooling for monitoring running systems against intended deployment structure. |
| [scoutsuite](https://github.com/presidio-v/presidio-hardened-scoutsuite) | Component | `0.29.0` | 2026-06-18 | 15.5k LOC; 151 installs; 37 commits/90d; 413 changes; tests S/D; deploy; publish PyPI+TP; tags 2/2 signed | Security-hardened ScoutSuite distribution for cloud posture assessment. |

## AI Governance & Assessment

Assess and gate AI use cases against the IKI-Gov reference model and signed evidence records.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [ikigov-assess](https://github.com/presidio-v/presidio-hardened-ikigov-assess) | Flagship | `0.21.1` | 2026-06-25 | 13.6k LOC; 106 installs; 49 commits/90d; 290 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 3/22 signed | CLI assessment tool for evaluating AI use cases against the IKI-Gov reference model and evidence requirements. |

## Flagship Platforms

Deep-research + software platforms that an org operates: payments, AI, treasury.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [treasury](https://github.com/presidio-v/presidio-hardened-treasury) | Flagship | `0.21.0` | 2026-06-12 | 16.7k LOC; 0 installs; 42 commits/90d; 304 changes; tests -/D; deploy; publish none; tags none | Audit-grade treasury close tooling for crypto-first organizations. |
| [x402](https://github.com/presidio-v/presidio-hardened-x402) | Flagship | `0.7.0` | 2026-06-23 | 17.2k LOC; 908 installs; 77 commits/90d; 388 changes; tests S/D; deploy; publish PyPI+TP+PEP740; tags 3/5 signed | Security middleware for the x402 payment protocol. |
| [x402-mcp](https://github.com/presidio-v/presidio-hardened-x402-mcp) | Component | `0.1.1` | 2026-06-15 | 1.5k LOC; 381 installs; 16 commits/90d; 47 changes; tests S/D; deploy; publish PyPI+TP; tags 2/2 signed | MCP pre-payment PII screener for x402 payment metadata before an agent signs a request. |

## Research & Publications

Publication-heavy work that underpins the platforms with models, proofs, and frameworks.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [fl](https://github.com/presidio-v/presidio-hardened-fl) | Frozen | `0.1.0` | 2026-06-11 | 1.5k LOC; 0 installs; 13 commits/90d; 47 changes; tests S/D; deploy; publish none; tags none | Privacy-preserving federated learning simulation for PRES-EDU-CS-101 |
| [ids](https://github.com/presidio-v/presidio-hardened-ids) | Frozen | `0.1.0` | 2026-06-11 | 1.2k LOC; 0 installs; 5 commits/90d; 36 changes; tests S/D; deploy; publish none; tags none | ML-based intrusion detection system with adversarial evasion and hardening. |
| [vol-asssign](https://github.com/presidio-v/presidio-hardened-vol-assign) | Research | `0.2.0` | 2026-06-07 | 6.5k LOC; 0 installs; 11 commits/90d; 117 changes; tests S/D; deploy; publish PyPI+TP; tags 0/1 signed | Python CLI implementation of a multi-objective volunteer assignment model. |

## Public Tooling & Assurance

Public support tooling and assurance material for the hardened product family.

| Project | Stage | Version | Updated | Metrics | Purpose |
|---|---|---|---|---|---|
| [angellist](https://github.com/presidio-v/presidio-hardened-angellist) | Component | `0.7.1` | 2026-06-07 | 6.5k LOC; 407 installs; 14 commits/90d; 160 changes; tests S/D; deploy; publish PyPI+TP; tags 0/3 signed | Security-hardened deal-flow triage and due-diligence toolkit. |

---

**Public-scope note:** non-public workspaces, private repositories, and scaffolding are excluded. Activity metrics use the last 90 days. Tests are evidence-based: S = static tooling/workflows, D = dynamic tests/test files. Installs combine PyPI last-month downloads and GitHub release asset downloads where available. PyPI publishers are repos with an explicit publish workflow; signed-tagged counts repos with at least one signed Git tag object.
