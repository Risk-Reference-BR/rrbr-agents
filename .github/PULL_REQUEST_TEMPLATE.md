## Description

<!-- What does this PR do? Which product/metric/feature does it implement or fix? -->

## Type of Change

- [ ] `feat`: new product implementation or new risk metric
- [ ] `fix`: incorrect calculation result
- [ ] `perf`: performance improvement (include benchmark comparison)
- [ ] `refactor`: code restructure without behavior change
- [ ] `docs`: documentation only
- [ ] `chore`: build, CI, dependencies

## Regulatory Reference

<!-- MANDATORY for any pricing or risk metric change.
     Cite the exact normative source: BCB resolution, ISDA paragraph, ANBIMA manual section, B3 specification.
     Example: "BCB Resolução 4.958/2021, Art. 8º, §3º — FRTB-SA IR bucket correlation parameters" -->

**Regulatory source:**

## Test Coverage

- [ ] Unit tests added/updated
- [ ] Edge cases covered (zero notional, extreme rates, maturity boundaries)
- [ ] Benchmark added for calculation-critical code (Criterion)

## Checklist

- [ ] `cargo fmt` applied
- [ ] `cargo clippy --all-targets -- -D warnings` passes
- [ ] `cargo test --workspace` passes
- [ ] No `unsafe` added without justification comment
- [ ] CHANGELOG.md updated (if breaking change)
