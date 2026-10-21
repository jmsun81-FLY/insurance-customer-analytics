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

### Completed

- Developed a reusable Model Evaluation AI Skill using SKILL.md.
- Completed two rounds of manual Skill testing and iterative improvement.
- Improved the Skill to distinguish original class prevalence from balanced modelling samples.
- Configured a filesystem MCP server using Visual Studio Code, Node.js, and GitHub Copilot.
- Successfully connected the MCP server to aggregated model evaluation data stored in JSON format.
- Verified actual MCP tool calls using `read_text_file`.
- Tested the combined workflow using MCP data retrieval and reusable Skill instructions.
- Confirmed that the AI assistant could access SKILL.md from the workspace and apply its model evaluation guidance.
- Generated business-oriented model comparisons and recommendations.
- Verified that MCP filesystem access restrictions prevented unauthorized directory access.

### MCP Integration Test Results

**MCP Server:** insurance-model-metrics

**Data Source:** examples/model_metrics.json

**Tools Successfully Used:**
- read_text_file
- list_allowed_directories
- directory_tree

**Results:**

The AI assistant successfully retrieved aggregated machine learning evaluation metrics through the MCP filesystem server.

It also accessed the reusable Model Evaluation Skill instructions and generated a structured comparison of Decision Tree, Logistic Regression, and Neural Network models.

The output included model performance comparisons, class imbalance considerations, business recommendations, and validation limitations.

### Security and Access Control

The MCP server was configured to access only the authorized `examples` directory.

During testing, an attempt to read SKILL.md outside the authorized MCP directory was denied.

The AI assistant subsequently accessed SKILL.md through the editor's workspace file-reading capability without expanding the MCP server's permissions.

This demonstrated the importance of scoped tool access and appropriate separation of responsibilities.

### Not Yet Completed or Fully Verified

- The specific automatic Skill discovery mechanism has not been independently verified, although the assistant accessed SKILL.md during testing without the Skill being explicitly named.
- Automated regression testing across multiple datasets and scenarios.
- Integration with live enterprise databases or APIs.
- Production deployment and operational monitoring.

### Final Project Status

**Status: Functional Local Prototype**

The reusable AI Skill and MCP filesystem integration have been successfully tested in a local VS Code environment.

The prototype demonstrates a build-test-improve workflow involving reusable AI instructions, tool integration, iterative evaluation, business interpretation, and human oversight.

No confidential customer records were used in the MCP demonstration.

The project is intended for learning and portfolio demonstration rather than production deployment.


This project demonstrates an initial build-test-improve workflow for reusable AI instructions.

No customer-level records or confidential datasets are included.
