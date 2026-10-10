# SignalDeck — Public Track Record

Every predictor SignalDeck tracks, rendered verbatim from [`accuracy_registry.json`](accuracy_registry.json) on every publish — FAILED and INSUFFICIENT verdicts included, nothing filtered. A deliberately unflattering public record is the point: it cannot be fabricated overnight, and the commit history of this repo makes later retouching of the past record evident.

- Generated: 2026-10-09T14:05:16
- Minimum independent n for a verdict: 30
- Survivorship epoch: 2026-07-24
- Null policy: prequential-majority only: each day's constant guess is the majority class over days strictly before it. The hindsight null was retired after the dual-null transition cycle; the switchover regrade recorded zero verdict changes (audits/2026-07-27-null-transition.md).

| Predictor | Family | Band | n | Accuracy | 95% CI | Prequential null | Verdict | Note |
|---|---|---|--:|--:|---|--:|---|---|
| directional-ensemble (1d) | direction | all | 1804 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label grades from 2026-10-04 and figures return only after that window clears its evidence floors | live forward record; non-overlapping forward-window blocks, block-resampled interval |
| prequential-majority (1d) | benchmark | all | 1135 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label grades from 2026-10-04 and figures return only after that window clears its evidence floors | live-committed running-majority benchmark; graded under the identical dedup/survivorship rules as the ensemble |
| directional-ensemble (1d, high conviction) | direction | \|p-0.5\|>=0.15 | 482 | withheld (SD-30) | withheld (SD-30) | withheld (SD-30) | withheld: label partly realised at issue (SD-30); a corrected label grades from 2026-10-04 and figures return only after that window clears its evidence floors | the tier a user would actually trade |
| filingsdrift21 | structure | all | 205 | 45.4% | withheld | — | NO BASELINE — naive-persistence null not frozen for these calls | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21 | structure | all | 14678 | 70.2% | withheld | — | INSUFFICIENT BLOCKS (3/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21#persist | structure-benchmark | all | 14390 | 71.0% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| liquidity21-crypto | structure | all | 289 | 56.1% | withheld | — | INSUFFICIENT BLOCKS (3/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| liquidity21-crypto#persist | structure-benchmark | all | 268 | 53.7% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21 | structure | all | 14787 | 78.4% | withheld | — | INSUFFICIENT BLOCKS (3/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21#persist | structure-benchmark | all | 14503 | 78.6% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend21-crypto | structure | all | 289 | 57.8% | withheld | — | INSUFFICIENT BLOCKS (3/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| trend21-crypto#persist | structure-benchmark | all | 268 | 55.2% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |
| trend63 | structure | all | 0 | — | — | — | PENDING (first grade 2026-09-25, 0/30 resolved) | claim is backtested, not yet a live record |
| vol21 | structure | all | 14810 | 50.3% | withheld | — | INSUFFICIENT BLOCKS (4/10 non-overlapping horizon blocks) — no interval, so no verdict | live-graded, interval resampled over non-overlapping horizon blocks |
| vol21#persist | structure-benchmark | all | 14519 | 49.2% | withheld | — | BENCHMARK — the frozen naive-persistence null itself | "nothing changes" guess frozen at call time and graded by the same resolver as the call; never recomputed afterwards |

**SD-30.** The 1d/1w directional figures withheld above are still inside [`accuracy_registry.json`](accuracy_registry.json): that exact file is what is timestamped, so it is published unaltered. Those figures rest on a label partly realised at issue and are not a claim; a corrected label grades from 2026-10-04 (PREREGISTRATION.md section 15).

## Verifying this record

- `accuracy_registry.json` — the canonical machine-readable registry; this README is a rendering of it, regenerated by `ops/anchor-publish.sh` on every push and never hand-edited.
- `anchors.log` — signed ledger anchor digests, append-only; a digest in the git history of this repo is evidence the operator cannot fabricate after the fact.
- `prereg.log` — pre-registration chain heads: structural claims frozen and timestamped before their outcomes existed.
- `PREREGISTRATION.md` — the frozen 2026-08-14 structural grading protocol (claim freeze, null choice, min-n/min-days gates, no post-hoc slicing); its `shasum -a 256` must equal the specHash of the chain's prereg-document record.
