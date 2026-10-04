# Code guide

Student_Feedback_Analysis.ipynb is the executable entry point. Its sections are organised by responsibility:

1. Load input: locate the extracted project locally or accept its ZIP in Colab. Default RUN_LIVE is False.
2. Validate and group: check columns, empty values, unique IDs, expected ten courses and ten comments each; build complete course requests.
3. Fixed prompt: define the final literal prompt and verify equality with the final manifest.
4. Structural validation: check JSON fields, course identity, list bounds, nonempty descriptions and evidence IDs, and ID uniqueness/membership. This does not judge semantic support.
5. Replay or run: replay eight final files by default. Optional live mode saves each request, response, error and usage record into a separate timestamped folder. Failed requests are recorded without automatic retries.
6. Inspect: display one course's summary and all source comments; development records can also be selected.
7. Evaluation: read the author's CSV, filter the eight heldout_rerun courses and report each metric separately; calculate recorded usage from the final summary CSV.

Data and evals explanations are in their own README files. results/README.md identifies the authoritative batch. docs/product_documentation.md explains the user-facing purpose and design decisions.

Required external dependencies are pandas and requests, plus Jupyter for local notebook use. Google Colab provides its upload interface. No database, vector store, web server or autonomous tool selection is used. API credentials are entered through a hidden prompt or environment variable and are not written to result records.
