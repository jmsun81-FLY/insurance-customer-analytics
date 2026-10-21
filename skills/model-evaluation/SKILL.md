
---
name: model-evaluation
description: Compare machine learning classification models using evaluation metrics and generate business-oriented recommendations. Use when users provide model results and need help selecting, validating, or explaining a classification model.
---

# Machine Learning Model Evaluation Skill

## Purpose

Help users compare classification models, interpret evaluation metrics, and recommend suitable models based on business objectives.

This skill is designed for analytical projects involving Decision Trees, Logistic Regression, Neural Networks, and other classification algorithms.

## Required Inputs

Ask the user to provide:

1. Business objective and target variable.
2. Model names.
3. Available performance metrics:
   - AUC
   - Accuracy
   - Precision
   - Recall
   - F1 Score
   - MCC
4. Class distribution, if available.
5. Evaluation method, such as cross-validation or a held-out test set.

Use only the information provided. Do not invent missing results.

## Evaluation Workflow

### Step 1: Understand the Business Objective

Identify whether the objective prioritizes:

- Finding more positive cases (Recall)
- Reducing false positives (Precision)
- Ranking cases effectively (AUC)
- Balancing Precision and Recall (F1)
- Interpreting and explaining predictions

### Step 2: Check Evaluation Conditions

Verify whether models were compared using consistent:

- Data preprocessing
- Sampling strategies
- Training and validation procedures
- Target class definitions
- Performance metrics

If these conditions are unknown, explain the uncertainty.

### Step 3: Compare Model Performance

Create a comparison table using the available metrics.

Identify the strongest model for each reported metric.

Do not automatically select the model with the highest Accuracy.

Consider class imbalance and the business objective.

### Step 4: Assess Model Trade-offs

Discuss:

- Predictive performance
- Model complexity
- Interpretability
- Operational usefulness
- Potential limitations

Explain why a simpler model may sometimes be preferable to a more complex one.

### Step 5: Recommend a Model

Recommend a model based on the available evidence and stated business priorities.

Explain the selection using specific evaluation metrics.

Distinguish between statistical performance and practical business value.

### Step 6: Responsible AI and Validation

Remind users that:

- Model results depend on data quality.
- Class imbalance may affect evaluation.
- Similar cross-tool results do not guarantee real-world accuracy.
- Independent validation improves confidence but does not eliminate uncertainty.
- Models should be tested appropriately before deployment.
- Human oversight remains important.

Never claim that model training, Python execution, or external validation has occurred unless it was actually performed.

Do not request or expose private customer-level data.

## Standard Output Format

When performing an evaluation, generate:

### 1. Business Objective
Summarize the problem being addressed.

### 2. Model Comparison
Display the available model metrics in a table.

### 3. Key Findings
Explain major strengths and weaknesses of each model.

### 4. Recommended Model
Identify the preferred model and justify the recommendation.

### 5. Business Implications
Explain how the results could support business decisions.

### 6. Limitations and Next Steps
Identify limitations, additional validation needs, and appropriate precautions.

## Example Use Case

Business problem:
Predict whether an auto insurance quotation will convert into a purchased policy.

Candidate models:
- Decision Tree
- Logistic Regression
- Neural Network

Important considerations:
- Class imbalance
- AUC and Recall
- Interpretability
- Customer follow-up prioritization

Evaluate the supplied results and recommend an appropriate model without inventing additional evidence.

## Privacy and Safety

Use aggregated model evaluation metrics or authorized synthetic data.

Do not publish confidential datasets, personal customer records, or proprietary materials.

This skill provides analytical guidance and does not independently access databases, execute code, or deploy production systems.
