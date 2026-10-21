
# Model Evaluation AI Skill – Testing and Iteration

## Project Objective

Develop and evaluate a reusable AI Skill that helps users compare machine learning classification models, identify evaluation limitations, and generate business-oriented recommendations.

The Skill was designed using the Agent Skills instruction format and tested through manually supplied instructions in ChatGPT.

## Test 1: Initial Model Evaluation

**Objective:** Evaluate the Skill's ability to compare three classification models and identify the most appropriate model for insurance quotation conversion prediction.

**Test Data:**
- Decision Tree
- Logistic Regression
- Neural Network
- Original positive-class prevalence: 21.88%
- Evaluation metrics: AUC, Accuracy, Precision, Recall, F1 and MCC

**Results:**

The AI successfully compared the models and provided a provisional recommendation for Logistic Regression.

However, it identified an apparent inconsistency between Accuracy, Precision and Recall when interpreting the results using the original 21.88% positive-class prevalence.

**Issue Identified:**

The initial test did not explicitly provide the class distribution of the balanced modelling sample.

The AI correctly requested additional information, but could not fully resolve the issue without sampling context.

## Iteration: Improving Evaluation Context

The evaluation instructions were refined to distinguish:

- Original dataset class distribution
- Sampling methods
- Balanced modelling sample
- Evaluation class distribution
- Potential effects of resampling on performance metrics

This improvement addressed the need for more complete evaluation context.

## Test 2: Evaluation with Sampling Information

**Additional Context:**

Original dataset:
- 79,599 non-converted quotations
- 22,292 converted quotations
- Total: 101,891 records
- Conversion prevalence: 21.88%

After random undersampling:
- 22,292 non-converted quotations
- 22,292 converted quotations
- Balanced modelling sample: 44,584 records
- Positive-class proportion: 50%

**Results:**

The AI correctly distinguished the original dataset from the balanced modelling sample.

It reassessed the previously identified inconsistency and demonstrated that the reported metrics were approximately mathematically consistent with a 50% positive-class evaluation distribution.

For Logistic Regression, the reconstructed Accuracy was approximately 0.598, consistent with the reported value of approximately 0.597 after allowing for rounding and aggregation differences.

The AI maintained Logistic Regression as the provisional recommendation while recognizing the small performance differences among the models.

## Key Learning Outcomes

1. Context completeness is essential for reliable AI evaluation.
2. Model metrics must be interpreted using the appropriate evaluation population.
3. Iterative testing helps identify missing assumptions.
4. Human review is necessary to verify and correct AI-generated conclusions.
5. Clear analytical instructions improve the consistency and usefulness of AI outputs.
6. Successful instruction-based tests do not replace independent model validation.

## Current Status and Limitations

**Completed:**
- Reusable Skill instruction file
- Two manual evaluation tests
- Sampling-context clarification
- Evaluation of AI-generated recommendations

**Not Yet Completed:**
- Automatic Skill discovery and invocation in an Agent runtime
- MCP tool integration
- Automated regression testing
- Production deployment

This project demonstrates an initial build-test-improve workflow for reusable AI instructions.

No customer-level records or confidential datasets are included.
