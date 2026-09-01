# SignalDeck — Public Track Record

Every predictor SignalDeck tracks, rendered verbatim from [`accuracy_registry.json`](accuracy_registry.json) on every publish — FAILED and INSUFFICIENT verdicts included, nothing filtered. A deliberately unflattering public record is the point: it cannot be fabricated overnight, and the commit history of this repo makes later retouching of the past record evident.

- Generated: 2026-08-31T19:38:09
- Minimum independent n for a verdict: 30
- Survivorship epoch: 2026-07-24
- Null policy: prequential-majority only: each day's constant guess is the majority class over days strictly before it. The hindsight null was retired after the dual-null transition cycle; the switchover regrade recorded zero verdict changes (audits/2026-07-27-null-transition.md).

| Predictor | Family | Band | n | Accuracy | 95% CI | Prequential null | Verdict | Note |
|---|---|---|--:|--:|---|--:|---|---|
| directional-ensemble (1d) | direction | all | 2768 | 44.4% | [0.346, 0.546] | 55.4% | FAILED — significantly worse than the naive baseline | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1d) | benchmark | all | 2439 | 56.2% | [0.376, 0.732] | 54.2% | NO SKILL — indistinguishable from baseline | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1w) | direction | all | 5183 | 45.2% | withheld | 57.4% | INSUFFICIENT DAYS (4/10 credible days of 29, 25 degenerate) — no interval, so no verdict | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1w) | benchmark | all | 4822 | 58.1% | withheld | 57.5% | INSUFFICIENT DAYS (4/10 credible days of 27, 23 degenerate) — no interval, so no verdict | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1d, high conviction) | direction | \|p-0.5\|>=0.15 | 455 | 45.1% | withheld | 48.5% | INSUFFICIENT DAYS (5/10 credible days of 8, 3 degenerate) — no interval, so no verdict | the tier a user would actually trade |
| directional-ensemble (1w, high conviction) | direction | \|p-0.5\|>=0.15 | 695 | 41.4% | withheld | 53.5% | INSUFFICIENT DAYS (5/10 credible days of 26, 21 degenerate) — no interval, so no verdict | the tier a user would actually trade |
| filingsdrift21 | structure | all | 44 | 45.5% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21 | structure | all | 1099 | 74.1% | withheld | — | INSUFFICIENT BLOCKS (1/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21#persist | structure-benchmark | all | 814 | 71.6% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| liquidity21-crypto | structure | all | 37 | 97.3% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21-crypto#persist | structure-benchmark | all | 16 | 93.8% | withheld | — | BENCHMARK (INSUFFICIENT 16/30) | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21 | structure | all | 1106 | 77.8% | withheld | — | INSUFFICIENT BLOCKS (1/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21#persist | structure-benchmark | all | 824 | 77.5% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21-crypto | structure | all | 37 | 67.6% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21-crypto#persist | structure-benchmark | all | 16 | 43.8% | withheld | — | BENCHMARK (INSUFFICIENT 16/30) | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend63 | structure | all | 0 | — | — | — | PENDING (first grade 2026-09-25, 0/30 resolved) | claim is backtested, not yet a live record |
| vol21 | structure | all | 1111 | 57.2% | withheld | — | INSUFFICIENT BLOCKS (1/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| vol21#persist | structure-benchmark | all | 824 | 54.5% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |

## Verifying this record

- `accuracy_registry.json` — the canonical machine-readable registry; this README is a rendering of it, regenerated by `ops/anchor-publish.sh` on every push and never hand-edited.
- `anchors.log` — signed ledger anchor digests, append-only; a digest in the git history of this repo is evidence the operator cannot fabricate after the fact.
- `prereg.log` — pre-registration chain heads: structural claims frozen and timestamped before their outcomes existed.
- `PREREGISTRATION.md` — the frozen 2026-08-14 structural grading protocol (claim freeze, null choice, min-n/min-days gates, no post-hoc slicing); its `shasum -a 256` must equal the specHash of the chain's prereg-document record.
