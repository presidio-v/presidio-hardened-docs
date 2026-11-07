---
title: PRESIDIO SDLC — Applicability Matrix
version: 1.2
date: 2026-11-07
next_review: 2027-01-08
audience: Customers, partners, and prospective adopters
---

# Applicability matrix

Companion to [`sdlc-report.md`](sdlc-report.md) §1. It lists every **public**
`presidio-v` repository, the baseline that applies to it, and the controls
measured for it. Private and internal repositories are tiered in an internal
register with the same rules.

Measured 2026-11-07 from the repositories' default branches (workflow files, `SECURITY.md`, `PRESIDIO-REQ.md`) and from PyPI. Previous measurements: 2026-11-05, 2026-10-08. A dash means the
control is absent, not unknown. Gaps are listed as gaps.

## Tier rules

The tier depends on how the code runs, not which repository it sits in or how
mature it is.

| Tier | Applies when | Required controls |
|---|---|---|
| **Commercial-operated** | PRESIDIO operates it as a service, delivers it to a paying customer, or it handles personal data or payments on PRESIDIO's behalf | Full SDLC document set (charter, threat model, ASVS verification, DPIA, risk register, ADRs, supply-chain posture) plus everything below |
| **Open-source baseline** | Published on a package registry, or a public repository that ships code | CI with tests and lint; static analysis (CodeQL or a language equivalent); a dependency audit; Dependabot; `SECURITY.md` with a disclosure path **and a statement of this tier**; `PRESIDIO-REQ.md` requirements baseline; OpenSSF Scorecard on public repositories |
| **Exempt** | Documentation, unpublished research, scaffolding, archived | None beyond the organisation baseline. Listed so the exemption is explicit |

A stage of *frozen* does not exempt a package that is still published and
installed; it only means no new features are planned.

## Commercial-operated

| Component | Where the full set lives | Status |
|---|---|---|
| x402 screening service (`screen.presidio-group.eu`) | Internal repository of `presidio-hardened-x402`, `sdlc/` | Full set; quarterly review held 2026-10-08 |

## Open-source baseline (public repositories)

Columns: **CI** tests + lint · **SAST** CodeQL or equivalent · **Audit**
dependency audit in CI · **Dep** Dependabot · **Sec** `SECURITY.md` ·
**Tier** tier statement in `SECURITY.md` · **REQ** `PRESIDIO-REQ.md` ·
**SC** Scorecard workflow.

| Repository | Registry | CI | SAST | Audit | Dep | Sec | Tier | REQ | SC |
|---|---|---|---|---|---|---|---|---|---|
| presidio-hardened-x402 (library) | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-x402-mcp | PyPI, MCP Registry | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-ai | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-evidence | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-arch-translucency | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-ikigov-assess | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-scoutsuite | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-treasury | — (Rust) | ✓ | ✓ | ✓ (`cargo-deny`) | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-angellist | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-vol-assign | — (GitHub releases) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-fastapi | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-flask | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-requests | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-opcua | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-crypto-channel | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-vuln-scanner | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-fl | — | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-ids | — | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-esp32 | — | ✓ (host tests) | ✓ | ✓ (pin check) | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-repo | — | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – | ✓ |

The **Tier** column counts an existing "Software Development Lifecycle" section
in `SECURITY.md`. The rollout of an explicit tier sentence into those sections
is tracked in the internal review tracker.

## Exempt (public)

| Repository | Reason |
|---|---|
| presidio-hardened-docs | Documentation only (this report) |
| x402-pre-payment-guard | Collaborative working draft for [x402-foundation/x402#2533](https://github.com/x402-foundation/x402/issues/2533): interface spec, reference plugins and conformance vectors. Not published and not a PRESIDIO product |

## Known gaps, open-source baseline

- **No `PRESIDIO-REQ.md`:** hardened-repo.
- **Accepted exceptions in the audits:**
  - opcua's audit ignores PYSEC-2026-888 (CVE-2022-25304). Every `opcua` release
    has it and there is no fix upstream. The package caps chunk size, chunk count
    and message size on import, and documents this in its `SECURITY.md`.
  - esp32 declares no managed components, so it has nothing to scan for
    vulnerabilities. Its audit is a pin check: it fails if a dependency is added
    without an exact version or commit. ESP-IDF itself, with its bundled mbedTLS,
    is not covered.
- **esp32 tests run on the host only:** the 40 portable unit tests run on Linux
  under ASan/UBSan. Hardware paths are built for four targets but not executed in
  CI.

Closed on 2026-11-07:
- The CI dependency audits for opcua, esp32 and hardened-repo. Since 2026-10-08,
  ikigov-assess, crypto-channel, vuln-scanner, fl and ids had already closed this
  gap, and scoutsuite now audits every pull request.
- Lint and host tests for esp32.
- The tier statements in `SECURITY.md` for treasury, hardened-repo and evidence.
- **Scorecard on 9 of 20 repositories.** The ≥ 7.0 target is enforced only
  where the workflow runs; all nine score 8.4 or higher.

## Review

Quarterly with `sdlc-report.md`, and whenever a repository changes visibility,
starts or stops publishing, gets a deployment, or changes stage.
