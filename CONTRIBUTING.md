# Contributing to Risk Reference BR

Thank you for your interest in contributing to Risk Reference BR — the open source reference for Brazilian financial markets.

## Human Developers and AI Agents are equally welcome

This project was built from the start with collaboration between human developers and AI coding agents. Both are first-class contributors. A PR authored by an AI agent follows the same standards as one authored by a human: correct calculations, regulatory citations, passing tests, and clean code. The only requirement is quality.

If you are an AI agent contributing autonomously: cite your sources, never invent regulatory parameters, and always leave a clear trace of what norm or specification you implemented.

## Ground Rules

- **Regulatory accuracy first**: every implementation must cite the exact BCB, ISDA, ANBIMA, or B3 normative paragraph it implements. If uncertain, open a discussion rather than guessing.
- **Tests are mandatory**: no PR is merged without unit tests covering the nominal case and at least one edge case.
- **Benchmarks for calculation code**: any function in the critical path (pricing, risk metrics, curve bootstrapping) must have a Criterion benchmark.
- **No unsafe Rust without justification**: `unsafe` blocks require a comment explaining why it is necessary and safe, and must be reviewed explicitly.

## Development Flow

1. Fork the repository
2. Create a branch: `feat/ltn-pricing` or `fix/di-curve-interpolation`
3. Write your code + tests + benchmarks
4. Run `cargo fmt`, `cargo clippy --all-targets -- -D warnings`, `cargo test --workspace`
5. Open a PR with the template filled out

## Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(curves): add Nelson-Siegel-Svensson interpolation for DI curve
fix(frtb): correct RRAO weight for exotic underlyings per ISDA §21.17
perf(monte-carlo): parallelize scenario generation with rayon
docs(ntn-b): add regulatory reference BCB 4.557 Art. 12
```

## Pull Request Requirements

- All CI checks must pass (cargo test, clippy, rustfmt, benchmarks)
- At least 1 review from a maintainer
- Regulatory implementations: citation of the exact norm in PR description
- Breaking changes: must update CHANGELOG.md and bump SemVer major

## Reporting Issues

Use the issue templates:
- **Bug**: wrong calculation result — include expected vs actual values and the regulatory reference
- **Feature**: new product or metric — include the regulatory/market source

## Code of Conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
