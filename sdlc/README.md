# SDLC report

- **Markdown:** [`sdlc-report.md`](sdlc-report.md)
- **PDF:** [`sdlc-report.pdf`](sdlc-report.pdf)

The report describes two baselines — **open-source** (applies to every
`presidio-hardened-*` package on PyPI) and **commercial-operated** (adds the
full framework for PRESIDIO-operated services and paid-customer deployments).
See §1 of the report for the distinction.

## Building the PDF

`sdlc-report.pdf` is generated from `sdlc-report.md`:

```bash
make            # -> sdlc-report.pdf
```

Requires `pandoc` and a `pdflatex` TeX distribution (TeX Live). The house style
and unicode glyph maps live in [`house-style.tex`](house-style.tex) (injected via
`--include-in-header`); the table/list/link machinery comes from pandoc's default
LaTeX template. Version and date are read from the report's front matter, so a
version bump only needs editing `sdlc-report.md`.

Version 1.2 · 2026-07-23.
