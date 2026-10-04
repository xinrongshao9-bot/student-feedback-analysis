# Data provenance

The dataset contains 100 comments across ten undergraduate courses, with ten comments per course, collected through an anonymous questionnaire distributed to undergraduate peers. Some Chinese responses were translated into English with AI assistance and manually reviewed. This provenance is reported by the project author. The submitted CSV is the English analysis dataset; the original questionnaire and bilingual translation pairs are not included. Manual review does not guarantee perfect semantic equivalence.

This convenience sample is not representative of the wider student population. Comment counts are not verified counts of distinct respondents. Anonymous collection does not eliminate identification through contextual detail.

## Fields

- comment_id: stable source identifier, used to inspect citations.
- course_id: C01–C10 grouping identifier.
- course_name: supplied course label.
- comment_text: English feedback supplied to the model.
- data_type: anonymised comments.
- source_basis: collection and translation description.

C01 and C08 are development cases. C02–C07, C09 and C10 form the reevaluation of the original test split. No comment-level sentiment ground truth is supplied. The English comment text and IDs must remain unchanged when replaying the submitted evaluation.

The metadata columns are not sent to the model. Course name, course ID and comment IDs/text are sent along with the fixed system prompt. See ../results/README.md for the historical provenance correction.
