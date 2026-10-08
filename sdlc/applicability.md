---
title: PRESIDIO SDLC — Applicability Matrix
version: 1.0
date: 2026-10-08
next_review: 2027-01-08
audience: Customers, partners, and prospective adopters
---

# Applicability matrix

Companion to [`sdlc-report.md`](sdlc-report.md) §1. It lists every **public**
`presidio-v` repository, the baseline that applies to it, and the controls
measured for it. Private and internal repositories are tiered in an internal
register with the same rules.

Measured 2026-10-08 (flask updated 2026-10-09) from the repositories' own workflow files. A dash means the
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
| presidio-hardened-arch-translucency | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-ikigov-assess | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-scoutsuite | PyPI | ✓ | ✓ | release only | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-treasury | — (Rust) | ✓ | clippy only | ✓ (`cargo-deny`) | ✓ | ✓ | – | ✓ | – |
| presidio-hardened-angellist | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| presidio-hardened-vol-assign | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-fastapi | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-flask | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-requests | PyPI | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-opcua | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-crypto-channel | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-vuln-scanner | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-fl | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-ids | PyPI | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-esp32 | — | ✓ | ✓ | – | ✓ | ✓ | ✓ | ✓ | – |
| presidio-hardened-repo | PyPI | ✓ | ✓ | – | ✓ | ✓ | – | – | ✓ |
| x402-pre-payment-guard | — (spec + vectors) | not measured | | | | | | | |

The **Tier** column counts an existing "Software Development Lifecycle" section
in `SECURITY.md`. The rollout of an explicit tier sentence into those sections
is tracked in the internal review tracker.

## Exempt (public)

| Repository | Reason |
|---|---|
| presidio-hardened-docs | Documentation only (this report) |

## Known gaps, open-source baseline

- **No dependency audit in CI:** ikigov-assess, opcua, crypto-channel,
  vuln-scanner, fl, ids, esp32, hardened-repo. scoutsuite audits only at
  release, not per pull request.
- **No CodeQL:** treasury (Rust; `clippy` and `cargo-deny` run).
- **No tier statement in `SECURITY.md`:** treasury, hardened-repo. (Every public repository states its tier in its README since 2026-10-09.)
- **No `PRESIDIO-REQ.md`:** hardened-repo.
- **Scorecard only on 6 of 18 repositories.** The ≥ 7.0 target is enforced only
  where the workflow runs.

## Review

Quarterly with `sdlc-report.md`, and whenever a repository changes visibility,
starts or stops publishing, gets a deployment, or changes stage.
