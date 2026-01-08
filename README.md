                                                    Rating prediction via prompting
 **Objective**

The goal of Task 1 is to evaluate how different prompt engineering strategies affect the ability of a Large Language Model (LLM) to classify Yelp reviews into 1–5 star ratings, while producing valid structured JSON output.

This task focuses on:

Prompt design

Output reliability

Evaluation of accuracy and JSON validity
rather than model training.

**Dataset**

Source: Yelp Reviews Dataset (Kaggle)

Sample Size: 200 reviews (randomly sampled)

Fields Used:

review_text

actual_stars

The dataset was not artificially balanced to preserve real-world distribution.

 **Approach**

The problem was treated as a prompt-based classification task using an LLM.

For each review:

A prompt was constructed

The LLM predicted a star rating

Output was expected in a strict JSON format

Predictions were compared with ground-truth ratings

Three different prompt versions were implemented and evaluated.

✏️ Prompt Versions
**Prompt V1 – Naive Prompt**

Minimal instructions

Weak formatting constraints
Purpose: Establish a baseline

**Prompt V2 – Strict JSON Prompt**

Enforced JSON-only output

Required integer ratings (1–5)
Purpose: Improve JSON validity

**Prompt V3 – Anchored Prompt**

Defined semantic meaning for each star rating

Strong output constraints
Purpose: Improve accuracy and consistency

**Evaluation Metrics**

Each prompt version was evaluated using:

Accuracy
Percentage of correct predictions compared to actual ratings (only valid outputs considered)

JSON Validity Rate
Percentage of model outputs that could be successfully parsed as valid JSON

Graceful error handling was implemented to avoid failures due to malformed outputs.

**Results Summary**
Prompt Version	JSON Validity Rate	Accuracy
V1 (Naive)	Low (~18%)	Moderate (~58%)
V2 (Strict JSON)	Improved	Improved
V3 (Anchored)	Highest	Best overall

(Exact values are reproducible in the notebook.)

 **Key Observations**

Naive prompts produced reasonable predictions but poor JSON reliability

Strict output rules significantly improved format consistency

Anchored prompts improved both accuracy and reliability

Prompt engineering alone had a strong impact on model performance

📁 **Files Included**

task1_rating_prediction.ipynb – Full implementation, evaluation, and results

Task_1_Report_Misba_Yadgiri.pdf – Detailed report for Task 1

**Notes**

No model training was performed
All evaluation was done via prompt-based inference
Results are fully reproducible using the notebook

All evaluation was done via prompt-based inference

Results are fully reproducible using the notebook
