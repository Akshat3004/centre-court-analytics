# Reported results and evidence

The figures below are from the **original team's published local experiments**, not independent measurements by this showcase.

| Metric | Documented value |
| --- | ---: |
| Curated singles point rows | **1,922,136** |
| Curated singles matches | **10,508** |
| Replay events | **1,917,672** |
| Replay matches | **10,464** |
| Full demo scored events | **9,049 across 50 matches** |
| Model | HistGradientBoostingClassifier |
| Model features | **26** point-in-time-safe features |
| Model training rows | **300,000** |
| Held-out test points | **284,868** |
| Test ROC AUC | **0.6415** |
| Test Brier score | **0.2347** |
| Test log loss | **0.6619** |
| Local scorer throughput | **2,454.17 events/sec** |
| Local scoring p95 latency | **0.575 ms/event** |
| Kafka/Spark streamed and scored | **1,000 events**, 0 invalid in recorded run |

**Sources:** [Project README](https://github.com/vishaljha2121/big_data_spring_proj), [model training audit](https://github.com/vishaljha2121/big_data_spring_proj/blob/main/docs/model_training_audit.md), [model comparison audit](https://github.com/vishaljha2121/big_data_spring_proj/blob/main/docs/model_comparison_analysis.md), [Spark audit](https://github.com/vishaljha2121/big_data_spring_proj/blob/main/docs/spark_structured_streaming_audit.md).

## How to interpret these metrics

- **0.6415 AUC is not 64.15% accuracy.** The target is whether Player A wins an individual point, not a match.
- The 2,454 events/sec result measures a **local scoring benchmark**, not full Kafka/Spark throughput or production performance.
- The 1,000-event Spark run validated a **local** pipeline, not end-to-end exactly-once delivery at production scale.
- Dashboard scoring used a 50-match sample; the larger replay manifest is separate.
- Risk signals are statistical anomaly indicators only, not proof of misconduct or match-fixing.
- Missing surface metadata, sparse rally data and unverified ATP ranking linkage limit feature coverage.

## Screenshots

The original [capture report](https://github.com/vishaljha2121/big_data_spring_proj/blob/main/presentation/assets_v2/screenshots/capture_results.json) marks most frontend views **SKIP**; several image filenames map to an identical Git blob. We deliberately haven't reproduced those as distinct dashboard screenshots. Capture genuine images from a running local demo before adding a visual gallery.
