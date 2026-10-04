# Evaluation protocol and final results

## Authority and independence

The author prepared course-level reference answers and manually reviewed the generated outputs, with AI assistance in checking references and reviewing scores. This is not independent or blinded evaluation. The workbook is the author's final reviewed table; outcome_metrics.csv contains the same scores and notes, plus explicit split and batch identifiers for calculation. Ground truth is excluded from model requests.

The submitted ground_truth.csv preserves the existing references. Some wording is broader than the English comments; source comments are authoritative for factual support. Reference evidence lists are pooled per course, not exhaustive citation requirements. Do not treat the references as externally validated truth.

## Four separate binary metrics

- main_issues_pass: all reference issues covered, without unsupported issues or substantive overstatement.
- strengths_complete: reference strengths covered; related themes can be merged. Empty strengths pass where no explicit reference strengths exist. This is not a guarantee that every positive source theme is retained.
- evidence_supported: cited comments support the substantive claim; membership checks alone are insufficient. Exhaustive citation is unnecessary.
- uncertainty_preserved: perceptions or suspicions retain appropriate qualification in issues, strengths and the overall summary.

For this final review, loss of qualification can fail uncertainty_preserved without failing issue coverage or evidence support when the substantive theme remains supported. Material unsupported allegations would affect those other metrics too. This boundary is subjective and requires independent review in future work.

## Final batch

Batch: 20261004T025037178550Z. Prompt: v2_provenance_corrected. Eight reevaluated courses: C02, C03, C04, C05, C06, C07, C09, C10. The split label is heldout_rerun because the original test courses had already been inspected. This is not a new unseen evaluation.

- main_issues_pass: 8/8 (100%).
- strengths_complete: 8/8 (100%).
- evidence_supported: 8/8 (100%).
- uncertainty_preserved: 7/8 (87.5%).
- Automated structure and evidence-ID membership: 8/8.

Do not average overlapping dimensions into overall accuracy. One course changes each rate by 12.5 percentage points. C01 and C08 do not enter these denominators.

## Case interpretation

C07 fails uncertainty preservation: “does not accommodate varying fitness levels” is more categorical than the comments' preferences for greater consideration. The author judges its theme and cited evidence supported and treats the error as qualification loss rather than substantive coverage or support failure.

C05 passes the reference-strength metric, but omits positive comments about case discussions. The limited reference answer focuses on videos. This qualitative omission exposes a coverage gap in the metric; it is not evidence of perfect positive-theme preservation.

C06 now includes willingness to help. C09 qualifies the potential impact on grading comparability. Their earlier failures did not recur in this batch, which does not establish a causal or reliable improvement from the provenance correction.

Development C01 scores 1,1,1,0: its overall summary loses the personal-perception qualification for fair grading. C08 scores 1,1,1,1. Each refers to its saved 4 October development JSON.

## Scope

Scores apply only to these saved outputs. All new API runs require new review. No sentiment accuracy, independent inter-rater agreement, institutional improvement or actual time savings were measured. Preserve all outputs and document failures instead of selecting the best response.
