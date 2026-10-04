# Experiment records

final_rerun/ contains the authoritative eight-course batch 20261004T025037178550Z, unchanged from the author's ZIP: per-course JSON records, manifest.json and run_summary.csv. It used the questionnaire-provenance-corrected prompt. development/ contains the corresponding new C01 and C08 records.

history/ preserves the earlier supplied experiments unchanged. Their prompts mistakenly described the questionnaire comments as synthetic. This is a historical prompt-label error, not the actual data provenance. Historical outputs do not enter the final metrics. Retaining them supports the report's discussion of development and variability.

The final eight-course batch totals 8,056 tokens, US$0.00195855 and 22.618 seconds of summed request duration. The latter uses rounded per-course durations in run_summary.csv. Mean duration is 2.82725 seconds. These exclude development and historical calls. The estimate of US$0.024481875 per 1,000 comments assumes comparable lengths, grouping and pricing, and excludes human work and operational overhead.

No API keys are included in request payloads. Optional notebook live runs write separately under reruns/ and require fresh evaluation. Final scores must not be applied to reruns.
