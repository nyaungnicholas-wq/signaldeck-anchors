# SignalDeck — Public Track Record

Every predictor SignalDeck tracks, rendered verbatim from [`accuracy_registry.json`](accuracy_registry.json) on every publish — FAILED and INSUFFICIENT verdicts included, nothing filtered. A deliberately unflattering public record is the point: it cannot be fabricated overnight, and the commit history of this repo makes later retouching of the past record evident.

- Generated: 2026-10-03T14:05:18
- Minimum independent n for a verdict: 30
- Survivorship epoch: 2026-07-24
- Null policy: prequential-majority only: each day's constant guess is the majority class over days strictly before it. The hindsight null was retired after the dual-null transition cycle; the switchover regrade recorded zero verdict changes (audits/2026-07-27-null-transition.md).

| Predictor | Family | Band | n | Accuracy | 95% CI | Prequential null | Verdict | Note |
|---|---|---|--:|--:|---|--:|---|---|
| directional-ensemble (1d) | direction | all | 2065 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1d) | benchmark | all | 2065 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1w) | direction | all | 288 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1w) | benchmark | all | 288 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1d, high conviction) | direction | \|p-0.5\|>=0.15 | 140 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | the tier a user would actually trade |
| directional-ensemble (1w, high conviction) | direction | \|p-0.5\|>=0.15 | 21 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label is pending a preregistration decision | the tier a user would actually trade |
| filingsdrift21 | structure | all | 199 | 46.2% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21 | structure | all | 12151 | 69.8% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21#persist | structure-benchmark | all | 11863 | 70.7% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| liquidity21-crypto | structure | all | 254 | 50.0% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21-crypto#persist | structure-benchmark | all | 233 | 46.8% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21 | structure | all | 12239 | 78.3% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21#persist | structure-benchmark | all | 11955 | 78.6% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21-crypto | structure | all | 254 | 52.8% | withheld | — | INSUFFICIENT BLOCKS (2/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21-crypto#persist | structure-benchmark | all | 233 | 49.4% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend63 | structure | all | 0 | — | — | — | PENDING (first grade 2026-09-25, 0/30 resolved) | claim is backtested, not yet a live record |
| vol21 | structure | all | 12252 | 49.5% | withheld | — | INSUFFICIENT BLOCKS (3/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| vol21#persist | structure-benchmark | all | 11961 | 48.0% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |

## Verifying this record

- `accuracy_registry.json` — the canonical machine-readable registry; this README is a rendering of it, regenerated by `ops/anchor-publish.sh` on every push and never hand-edited.
- `anchors.log` — signed ledger anchor digests, append-only; a digest in the git history of this repo is evidence the operator cannot fabricate after the fact.
- `prereg.log` — pre-registration chain heads: structural claims frozen and timestamped before their outcomes existed.
- `PREREGISTRATION.md` — the frozen 2026-08-14 structural grading protocol (claim freeze, null choice, min-n/min-days gates, no post-hoc slicing); its `shasum -a 256` must equal the specHash of the chain's prereg-document record.
