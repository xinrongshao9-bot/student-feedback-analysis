# Student Feedback Analysis

A Python notebook MVP for inspectable course-feedback summaries using GPT-4o-mini through OpenRouter. The supplied data contains 100 anonymous questionnaire comments, including manually reviewed AI translations of some Chinese responses.

## Run in Google Colab

1. Open Student_Feedback_Analysis.ipynb in Colab.
2. Keep RUN_LIVE = False and run all cells from top to bottom.
3. When prompted, upload student-feedback-analysis.zip from the submission package. Upload the project ZIP, not the outer submission ZIP or a single CSV.
4. The notebook loads the CSV, checks inputs, replays eight saved outputs and displays metrics without an API key or paid request.
5. In the inspection cell, set DISPLAY_COURSE to C05, C07 or another C01–C10 ID and rerun that cell to inspect its evidence.

## Run locally

Extract student-feedback-analysis.zip. Open a terminal in the extracted student-feedback-analysis folder:

```sh
python -m pip install -r requirements.txt
jupyter notebook Student_Feedback_Analysis.ipynb
```

Run the notebook from top to bottom with RUN_LIVE = False. Start Jupyter from this folder so the data and results paths resolve. Python 3.10 or later is recommended; the submitted replay was checked using the available bundled Python runtime. Fresh dependency installation and Google Colab were not independently tested in this packaging step.

## Optional new live run

Set RUN_LIVE = True, then run from the top. Supply an OpenRouter API key through OPENROUTER_API_KEY or the hidden prompt. This makes eight sequential paid requests. Results go into results/reruns/ with a new timestamp. There are no automatic retries. Keep the final submitted batch unchanged. New outputs need new human scores; the final-score cell continues to identify the submitted batch explicitly. Model availability, output and price may vary.

## Final result

Eight reevaluated courses: structural checks 8/8; issue coverage 8/8; reference strengths 8/8; evidence support 8/8; uncertainty preservation 7/8. C01 and C08 are development cases. C07 loses qualification. C05 illustrates an omission outside the reference-strength metric. This is reevaluation of an already examined split, not a new unseen test, and the dimensions are not combined into overall accuracy.

Final batch: 8,056 tokens, US$0.00195855, summed request duration 22.618 seconds. No real-world improvement or time savings were measured.

## Files

- Student_Feedback_Analysis.ipynb: runnable workflow with section explanations.
- requirements.txt: local dependencies.
- data/: English comments and provenance explanation.
- evals/: supplied reference answers, final reviewed workbook, matching CSV and scoring explanation.
- results/final_rerun/: unchanged final eight-course API batch.
- results/development/: new C01/C08 records.
- results/history/: earlier records, excluded from final metrics.
- docs/product_documentation.md: persona, input/output, architecture, metrics and limitations.
- docs/code_guide.md: file and module responsibilities.

Historical prompts incorrectly labelled questionnaire comments as synthetic. Final prompts correct the label. History is preserved transparently; see results/README.md. The report and demonstration recording materials are supplied alongside the project. The student must record the face-and-screen video separately.
