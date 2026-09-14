# Lab 1: MLP Regression & Classification — One-Hot, Binary, Multiclass

**Estimated time:** 75 minutes (in-class, guided)
**Submission:** Two links on Canvas — your GitHub repo URL, and your completed notebook URL
**Due:** Sept 14, 2026 at 3:05 pm - Section 1, Sept 14, 2026 at 4:40 pm - Section 2

## A Note on Format

Part 1 continues directly from what you already built in Lab 1 — same dataset, same one-hot encoding approach. Parts 2 and 3 apply that same MLP-building pattern to a new problem type: classification instead of regression. Watch closely for exactly which pieces of the code change, and which stay identical — that comparison is the real point of this lab.

## Learning Objectives

By the end of this lab, you will be able to:
- Build an MLP regression model using one-hot encoded categorical features
- Build an MLP binary classification model, and explain why its output layer differs from a regression model's
- Build an MLP multiclass classification model, and explain why its output layer differs from a binary model's
- Choose the correct loss function and output activation for each of the three task types
- Evaluate a regression model (RMSE/MAE) and classification models (accuracy, confusion matrix) appropriately for each

## Datasets

- **Part 1:** Ames Housing (same as Lab 1)
- **Part 2:** Pima Indians Diabetes — binary classification, 8 medical measurements, predicting diabetic vs. not
- **Part 3:** Wine Quality (red wine) — multiclass classification, physicochemical measurements, predicting a quality band (bucketed into low/medium/high)

All three load directly via `fetch_openml()` — no manual download needed.

---

## Part 1 — Regression with One-Hot Encoding

1. Load the Ames dataset, one-hot encode the categorical features.
2. Split into train/test (80/20), scaling features and target — **fit on train only, transform both.**
3. Build your MLP for regression.
4. Train, plot training vs. validation loss, and diagnose the fit.
5. Evaluate — report RMSE and MAE **in real dollars.**

## Part 2 — Binary Classification

1. Load the diabetes dataset, inspect class balance.
2. Split into train/test (80/20), **stratified on the target.**
3. Scale features only (not the target this time — think about why).
4. Build your MLP for classification.
5. Train, plot loss and accuracy curves, diagnose the fit.
6. Evaluate — report accuracy and a confusion matrix. Discuss the cost of false positives vs. false negatives in a medical context.

## Part 3 — Multiclass Classification

1. Load the wine quality dataset, bucket raw quality scores into 3 bands (low/medium/high).
2. Split into train/test (80/20), stratified. Scale features (train-only fit).
3. Build your MLP for classification
4. Train, plot loss and accuracy curves, diagnose the fit.
5. Evaluate — report accuracy and a confusion matrix. Discuss which classes get confused most often.

---

## The Comparison

Fill in your own results:

| | Part 1 (Regression) | Part 2 (Binary) | Part 3 (Multiclass) |
|---|---|---|---|
| Output neurons | | | |
| Output activation | | | |
| Loss function | | | |
| Label format | | | |
| Evaluation metric(s) | | | |

Answer in your notebook:
1. What's the general rule connecting the number of classes to the number of output neurons and the choice of activation?
2. Why doesn't regression need an output activation, while both classification tasks do?
3. Why might accuracy alone be misleading for Part 3 if the classes are imbalanced?

## Deliverables Checklist

- [ ] Part 1: one-hot pipeline, MLP built and justified, loss curve diagnosed, RMSE/MAE reported in dollars
- [ ] Part 2: binary MLP built and justified, loss/accuracy curves diagnosed, confusion matrix reported
- [ ] Part 3: multiclass MLP built and justified, loss/accuracy curves diagnosed, confusion matrix reported
- [ ] Comparison table completed
- [ ] All reflection questions answered

## Grading Rubric (100 points)

| Section | Points | Criteria |
|---|---|---|
| Part 1 — Regression | 30 | Correct encoding/scaling; architecture justified; loss curve correctly diagnosed; RMSE/MAE reported in dollars |
| Part 2 — Binary Classification | 30 | Correct output layer (sigmoid, 1 neuron) and loss (binary cross-entropy) with reasoning; stratified split; confusion matrix and threshold discussion |
| Part 3 — Multiclass Classification | 30 | Correct output layer (softmax, N neurons) and loss with reasoning; confusion matrix and class-confusion discussion |
| Comparison & Reflection | 10 | Table completed accurately; reflection questions show correct understanding of the output-layer/loss/metric relationships across all three tasks |
