# SignalDeck — Public Track Record

Every predictor SignalDeck tracks, rendered verbatim from [`accuracy_registry.json`](accuracy_registry.json) on every publish — FAILED and INSUFFICIENT verdicts included, nothing filtered. A deliberately unflattering public record is the point: it cannot be fabricated overnight, and the commit history of this repo makes later retouching of the past record evident.

- Generated: 2026-09-29T19:01:04
- Minimum independent n for a verdict: 30
- Survivorship epoch: 2026-07-24
- Null policy: prequential-majority only: each day's constant guess is the majority class over days strictly before it. The hindsight null was retired after the dual-null transition cycle; the switchover regrade recorded zero verdict changes (audits/2026-07-27-null-transition.md).

| Predictor | Family | Band | n | Accuracy | 95% CI | Prequential null | Verdict | Note |
|---|---|---|--:|--:|---|--:|---|---|
| directional-ensemble (1d) | direction | all | 603 | 52.2% | [0.423, 0.62] | 51.5% | NO SKILL — indistinguishable from baseline | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1d) | benchmark | all | 603 | 47.3% | [0.366, 0.582] | 51.5% | NO SKILL — indistinguishable from baseline | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1w) | direction | all | 6838 | 48.3% | withheld | 55.3% | INSUFFICIENT DAYS (7/10 credible days of 41, 34 degenerate) — no interval, so no verdict | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1w) | benchmark | all | 6803 | 43.5% | withheld | 55.4% | INSUFFICIENT DAYS (7/10 credible days of 41, 34 degenerate) — no interval, so no verdict | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1d, high conviction) | direction | \|p-0.5\|>=0.15 | 1 | 0.0% | withheld | 50.0% | INSUFFICIENT (1/30) | the tier a user would actually trade |
| directional-ensemble (1w, high conviction) | direction | \|p-0.5\|>=0.15 | 1090 | 49.0% | withheld | 60.6% | INSUFFICIENT DAYS (7/10 credible days of 36, 29 degenerate) — no interval, so no verdict | the tier a user would actually trade |
| filingsdrift21 | structure | all | 191 | 46.6% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21 | structure | all | 9913 | 69.2% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21#persist | structure-benchmark | all | 9625 | 70.1% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| liquidity21-crypto | structure | all | 226 | 49.6% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21-crypto#persist | structure-benchmark | all | 205 | 44.4% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21 | structure | all | 9973 | 78.6% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21#persist | structure-benchmark | all | 9689 | 78.9% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21-crypto | structure | all | 226 | 50.4% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21-crypto#persist | structure-benchmark | all | 205 | 46.3% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend63 | structure | all | 0 | — | — | — | PENDING (first grade 2026-09-25, 0/30 resolved) | claim is backtested, not yet a live record |
| vol21 | structure | all | 9985 | 48.9% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| vol21#persist | structure-benchmark | all | 9694 | 46.4% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |

## Verifying this record

- `accuracy_registry.json` — the canonical machine-readable registry; this README is a rendering of it, regenerated by `ops/anchor-publish.sh` on every push and never hand-edited.
- `anchors.log` — signed ledger anchor digests, append-only; a digest in the git history of this repo is evidence the operator cannot fabricate after the fact.
- `prereg.log` — pre-registration chain heads: structural claims frozen and timestamped before their outcomes existed.
- `PREREGISTRATION.md` — the frozen 2026-08-14 structural grading protocol (claim freeze, null choice, min-n/min-days gates, no post-hoc slicing); its `shasum -a 256` must equal the specHash of the chain's prereg-document record.
