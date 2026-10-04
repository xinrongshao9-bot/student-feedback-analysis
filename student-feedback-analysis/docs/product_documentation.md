# Product documentation

## User and purpose

Lecturers and course coordinators need a concise, inspectable account of course feedback. The MVP highlights concerns and strengths with source identifiers to support human review. It does not establish allegations, make personnel decisions, or demonstrate course improvement.

## Inputs and outputs

Input: 100 English questionnaire comments grouped into ten courses, with stable comment IDs. Some Chinese responses were AI-translated and manually reviewed. The program validates six CSV fields, identifiers and expected sample counts. Model requests contain course ID/name and ten comment IDs/texts, plus the system prompt; reference answers and human scores are excluded.

Output: JSON containing course_id, main_issues, strengths and summary. Each issue/strength has a description and evidence_ids. Lists contain up to three entries and can be empty. The notebook also saves request/response records, checks structure, and calculates the final author-reviewed scores. It is a course-summarisation notebook, not a sentiment classifier or web application.

## Architecture

```text
[English questionnaire CSV]
             |
             v
[Local field validation and course grouping]
             |
             v
[Fixed prompt + all ten comments for one course]
             |
             v
[OpenRouter -> openai/gpt-4o-mini]
             |
             v
[Save request, response, usage and elapsed time]
             |
             v
[Local JSON and citation-ID checks]
             |
             v
[Author reviews claims against source and references]
             |
             v
[Separate course-level metrics + inspectable summaries]
```

Default replay reads saved responses at the output stage; it makes no API requests. Model inference is purchased. Data organisation, prompting, orchestration, validation, logging and evaluation are implemented locally. No retrieval index is needed for ten short comments. Larger inputs would require testing context limits and aggregation losses.

## Metrics targeted and reached

Target dimensions are main-issue coverage without substantive overstatement, reference-strength completeness, citation support and uncertainty preservation. No pre-registered numerical acceptance threshold is claimed. In the final reevaluation, these score 8/8, 8/8, 8/8 and 7/8 respectively. Structural and evidence-ID checks pass 8/8. Development C01 and C08 are excluded.

C07 loses qualification and fails uncertainty preservation, while its substantive theme remains supported under the author's documented rubric. C05 omits positive case-discussion feedback despite passing reference-strength coverage, exposing a reference-answer limitation. The final C06 and C09 outputs no longer show their earlier failures. Full scoring rules and qualifications are in ../evals/EVAL_README.md.

Final batch API cost is US$0.00195855 for 80 comments, using 8,056 tokens. Estimated cost per 1,000 comparable comments is US$0.02448. Recorded durations sum to 22.618 seconds, averaging 2.827 seconds per course. These exclude development, human review, setup, hosting and maintenance and are not institutional productivity measurements.

## Limitations and responsible use

The small peer convenience sample and translation may limit representativeness and nuance. The author prepared references and evaluated outputs with AI assistance; this is not an independent blinded assessment. Reusing an already examined eight-course split does not establish performance on unseen courses. One changed score moves a rate by 12.5 percentage points. Repeated API calls may vary even at temperature zero.

Human review must cover the overall summary as well as individual issues and strengths. C01 illustrates lost qualification in a summary, and C05 shows how a metric can pass despite omission. Citation membership does not establish support. No institutional workflow trial, operational improvement or actual time saving was measured.

Deployment would require appropriate authorisation, de-identification, access and retention controls, and review of external processing under applicable privacy requirements. Anonymous collection does not eliminate identification through contextual details. Future work should expand data, preserve original-language responses and translation records, obtain independent reviewers, and measure usefulness and correction effort with lecturers.

## Reproducibility

The final batch is 20261004T025037178550Z with prompt v2_provenance_corrected, temperature 0 and max_tokens 1800. See ../results/README.md for preserved history and corrected provenance. Replaying reproduces saved results; live generation is not guaranteed to reproduce them and requires new scoring.
