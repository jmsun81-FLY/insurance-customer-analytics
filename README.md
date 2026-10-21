
# Insurance Customer Analytics
### Machine Learning, Reusable AI Skills & MCP Integration

**MBA Business Analytics Portfolio | Goodman School of Business, Brock University | 2026**

This portfolio combines an academic machine learning project with a practical AI prototyping extension.

The original team project examined auto insurance quotation conversion using customer segmentation and predictive modelling. I subsequently performed independent Python validation and developed a reusable AI Model Evaluation Skill connected to aggregated model results through the Model Context Protocol (MCP).

The goal is to demonstrate how technical experimentation, business understanding, and responsible AI practices can work together to address real-world analytical challenges.

## Project Highlights

| Area | Highlights |
|---|---|
| Business Analytics | 101,891 insurance quotation records |
| Machine Learning | Decision Tree, Logistic Regression, Neural Network |
| Customer Segmentation | Three segments using Two-Step Clustering |
| Python | Independent validation of three model results |
| Reusable AI Skill | Model evaluation instructions with structured outputs |
| MCP Integration | VS Code Copilot connected to a filesystem MCP server |
| Testing | Iterative evaluation and improvement based on feedback |
| Responsible AI | Scoped data access, privacy protection, human oversight |

## Quick Links

- [Reusable AI Model Evaluation Skill](.github/skills/model-evaluation/SKILL.md)
- [Skill Testing and Iteration](.github/skills/model-evaluation/TESTING.md)
- [MCP Server Configuration](.vscode/mcp.json)
- [Aggregated Model Metrics (JSON)](examples/model_metrics.json)
- [Project Screenshots and Visualizations](screenshots/README.md)

---

# Part I: Insurance Customer Analytics

## 1. Business Problem

Insurance providers receive large numbers of quotation requests, but only a portion convert into purchased policies.

Following up with every quotation equally may result in inefficient use of sales and customer service resources.

This project explored two business questions:

1. Which customer and insurance-related characteristics are associated with quotation conversion?
2. How can predictive modelling and customer segmentation support more effective follow-up strategies?

The project combined exploratory data analysis, clustering, machine learning, performance evaluation, and business recommendations.

## 2. Dataset and Class Imbalance

The original dataset contained 101,891 auto insurance quotation records.

| Original Dataset | Records | Share |
|---|---:|---:|
| Non-converted quotations | 79,599 | 78.12% |
| Converted quotations | 22,292 | 21.88% |
| Total | 101,891 | 100% |

The class imbalance presented a modelling challenge because models tended to favor the majority class.

The team evaluated sampling strategies and used random undersampling to create a balanced modelling sample:

| Balanced Modelling Sample | Records |
|---|---:|
| Non-converted quotations | 22,292 |
| Converted quotations | 22,292 |
| Total | 44,584 |

An important lesson was that model evaluation metrics calculated on a balanced sample cannot automatically be interpreted as performance on the original customer population.

## 3. Machine Learning Workflow

The team developed and compared three classification algorithms using Orange Data Mining.

![Orange Machine Learning Workflow](screenshots/orange-workflow.png)

**Figure 1. Orange Data Mining Workflow**

The analytical process included:

- Data exploration and preprocessing
- Feature selection
- Class imbalance assessment and sampling
- Machine learning model development
- Hyperparameter experimentation
- Cross-validation and performance comparison
- Business interpretation of model outputs

### Models Evaluated

**Decision Tree**

Tested different tree configurations, including minimum leaf size, split size, maximum depth, and branching approaches.

**Logistic Regression**

Compared regularization methods and parameter values to balance performance, complexity, and interpretability.

**Neural Network**

Evaluated different hidden-layer structures, activation functions, and optimization methods.

## 4. Model Performance Comparison

![Machine Learning Model Comparison](screenshots/model%20compare.png)

**Figure 2. Final Orange Model Evaluation Results**

| Model | AUC | Accuracy | Precision | Recall | F1 | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Decision Tree | 0.626 | 0.597 | 0.586 | 0.658 | 0.620 | 0.195 |
| Logistic Regression | 0.634 | 0.597 | 0.588 | 0.652 | 0.618 | 0.196 |
| Neural Network | 0.633 | 0.597 | 0.588 | 0.646 | 0.616 | 0.194 |

### Key Findings

- **Logistic Regression** achieved the highest AUC (0.634) and MCC (0.196).
- **Decision Tree** achieved the highest Recall (0.658) and F1 Score (0.620).
- **Neural Network** showed similar performance without a clear advantage over simpler approaches.
- The differences were relatively small, and none of the models demonstrated strong predictive discrimination.

### Model Recommendation

Logistic Regression was selected as the preferred candidate in the academic project because of its competitive ranking performance, interpretability, and practical business considerations.

However, the preferred model may depend on the business objective. For example, Decision Tree may be considered when recall at the evaluated threshold is the main priority.

Additional evaluation on a representative, untouched test set would be necessary before operational use.

## 5. Independent Python Validation

As an individual technical contribution, I used Python to conduct a secondary validation of the three machine learning models:

- Decision Tree
- Logistic Regression
- Neural Network

The Python-based results were broadly consistent with the Orange analysis.

This experience reinforced the importance of independent validation, analytical consistency, and critical review of model outputs.

Similar results across tools provide an additional consistency check but do not independently establish real-world predictive reliability.

## 6. Customer Segmentation

Two-Step Clustering was used to identify meaningful customer segments based on demographic, driving, vehicle, and insurance relationship characteristics.

![Customer Segmentation Results](screenshots/powerBI3.png)

**Figure 3. Customer Segmentation and Business Insights**

| Customer Segment | Customer Share | Quote Binding Rate |
|---|---:|---:|
| Loyal Multi-Product Commuters | 42.5% | 24.8% |
| Young Non-Multi-Product Commuters | 23.4% | 15.7% |
| Experienced Leisure Drivers | 34.0% | 22.3% |

The analysis found a statistically significant association between customer segments and quotation conversion status (Chi-square test, p < 0.001).

### Business Implications

- **Segment 1:** Consider prioritized follow-up, cross-selling, and loyalty initiatives.
- **Segment 2:** Explore introductory offers and cost-effective customer acquisition approaches.
- **Segment 3:** Consider retention strategies and bundled insurance products.

These findings demonstrate how statistical analysis can support differentiated business strategies.

---

# Part II: Reusable AI Skill & MCP Integration

## 7. AI Prototype Overview

Building on the insurance analytics project, I developed a reusable AI Model Evaluation Skill and tested its integration with an MCP-enabled AI assistant.

The prototype was designed to help an AI assistant:

1. Retrieve authorized model evaluation data.
2. Compare classification models using consistent analytical criteria.
3. Consider class imbalance and sampling methods.
4. Explain model performance trade-offs.
5. Recommend appropriate models based on business objectives.
6. Highlight limitations and further validation requirements.

This extension demonstrates a practical application of reusable AI instructions, tool integration, and human-guided evaluation.

## 8. Reusable AI Model Evaluation Skill

**Skill:** [model-evaluation](.github/skills/model-evaluation/SKILL.md)

The Skill uses a structured `SKILL.md` instruction file to guide classification model assessment.

### Main Capabilities

- Understand the business objective and target variable.
- Compare AUC, Accuracy, Precision, Recall, F1, and MCC.
- Distinguish original and resampled class distributions.
- Explain predictive performance and model trade-offs.
- Generate structured business-oriented recommendations.
- Identify analytical limitations and validation requirements.

The Skill was designed to be reusable across similar classification problems, rather than limited to the original insurance project.

## 9. MCP Tool Integration

**Technology:** Visual Studio Code, GitHub Copilot, Node.js, and Model Context Protocol (MCP).

I configured a filesystem MCP server to give the AI assistant access to an authorized directory containing aggregated model evaluation results.

### Integration Workflow

**Step 1 – User Request**

The user asks the AI assistant to evaluate classification models and recommend a suitable approach.

**Step 2 – MCP Data Retrieval**

The AI assistant uses the filesystem MCP tool to retrieve the JSON file containing model metrics.

**Step 3 – Reusable Skill Guidance**

The assistant accesses the Model Evaluation Skill to apply a structured model comparison and recommendation process.

**Step 4 – Business Recommendation**

The assistant generates a model comparison, identifies trade-offs, and explains business implications and limitations.

### Files and Configuration

- [MCP Configuration](.vscode/mcp.json)
- [Model Metrics JSON](examples/model_metrics.json)
- [Model Evaluation Skill](.github/skills/model-evaluation/SKILL.md)

### Verified Local MCP Test

During testing in VS Code, the MCP server successfully initialized and exposed filesystem tools.

GitHub Copilot used the MCP `read_text_file` tool to retrieve aggregated model metrics from `examples/model_metrics.json`.

The assistant also accessed the workspace Skill instructions and generated a model comparison with business recommendations.

The MCP server's allowed filesystem scope was limited to the `examples` directory. An attempted MCP read of `SKILL.md` outside this scope was denied, demonstrating the configured access boundary.

The Skill instructions were subsequently accessed through the editor's workspace file-reading capability without expanding the MCP server's directory permissions.

This was a local prototype test, not an enterprise deployment.

## 10. Testing, Feedback and Iterative Improvement

The AI Skill was evaluated through multiple tests using aggregated model results.

### Test 1: Initial Evaluation

The AI compared three models and recommended Logistic Regression.

However, it identified an apparent inconsistency between classification metrics and the original 21.88% positive-class prevalence.

The missing context was that the modelling sample had been balanced through undersampling.

### Improvement

I refined the Skill instructions to explicitly distinguish:

- Original class distribution
- Balanced modelling sample
- Evaluation distribution
- Sampling methods
- Possible metric interpretation differences

### Test 2: Evaluation with Complete Sampling Context

After providing the sampling information, the AI correctly distinguished the original dataset from the balanced modelling sample.

It reassessed the apparent metric inconsistency and explained why the reported performance metrics were approximately consistent with a 50% positive-class evaluation distribution.

### MCP and Skill Integration Test

A subsequent VS Code Copilot test demonstrated:

- Retrieval of JSON model metrics through MCP
- Access to the workspace Skill instructions
- Structured model comparison
- Explanation of class imbalance
- Business-oriented model recommendations
- Identification of validation limitations

A later test without explicitly naming the Skill also showed the assistant consulting `SKILL.md`. The exact automatic discovery mechanism was not independently verified.

### Lessons from Iteration

- AI analysis depends on complete and accurate context.
- Structured instructions can improve analytical consistency.
- Testing can reveal missing assumptions.
- Human feedback remains essential when evaluating AI-generated conclusions.
- Data access permissions should be limited to necessary resources.
- A successful prototype still requires further testing before production use.

See the [Skill Testing Documentation](.github/skills/model-evaluation/TESTING.md) for the initial testing and refinement record.

## 11. Reproducing the MCP Prototype

The local MCP demonstration was configured on Windows.

### Prerequisites

- Visual Studio Code with an MCP-capable GitHub Copilot Agent
- Node.js and npx
- This project repository opened as a trusted VS Code workspace

### Basic Steps

1. Open the project folder in VS Code.
2. Review `.vscode/mcp.json`.
3. Start the `insurance-model-metrics` server using VS Code's MCP server management tools.
4. Confirm that the MCP tools are available.
5. Open a Copilot Agent conversation.
6. Request a model evaluation using the available MCP data tools.
7. Review the actual tool calls to verify that the JSON file was read through MCP.

The configuration is intended for a Windows environment and uses a local filesystem MCP server.

The demonstration uses aggregated model metrics. It does not require access to original customer records.

---

# Part III: Responsible AI & Portfolio Information

## 12. Data Privacy and Security

This repository is a portfolio demonstration and does not distribute confidential insurance datasets.

The following safeguards are applied:

- No original customer-level insurance records are published.
- No personally identifiable customer information is included.
- Model results are presented in aggregated form.
- The MCP server is scoped to an authorized example-data directory.
- Testing focused on read operations without modifying source data.
- AI-generated conclusions are subject to human review.

The filesystem MCP server may support additional file operations within its authorized scope; permissions should be reviewed before allowing such operations.

## 13. Project Limitations

The original machine learning analysis was completed as an academic team project.

The AI Skill and MCP integration are local prototypes developed for experimentation and learning.

Current limitations include:

- No production deployment
- No live insurance database integration
- No automated end-to-end regression test suite
- No verified real-world conversion uplift
- Further model evaluation needed on representative, untouched data

The project demonstrates technical exploration and analytical decision support rather than a completed commercial AI application.

## 14. My Contributions

### Academic Analytics Project

- Independently used Python to cross-check three machine learning model results developed in Orange.
- Participated in a team-based business analytics project involving customer segmentation, predictive modelling, and business recommendations.

### AI Skill and MCP Extension

- Created a reusable Model Evaluation Skill using structured instructions.
- Refined Skill guidance after reviewing model evaluation limitations.
- Configured and tested a filesystem MCP server in VS Code.
- Connected authorized aggregated model data to an AI-assisted evaluation workflow.
- Reviewed the generated model comparisons and business recommendations.
- Documented the testing process and technical limitations.

## 15. Technologies and Skills Demonstrated

**Analytics:** Python, Orange Data Mining, IBM SPSS Statistics, Microsoft Excel

**Machine Learning:** Decision Tree, Logistic Regression, Neural Network, Two-Step Clustering

**AI Prototyping:** Reusable AI Skills, GitHub Copilot, AI-assisted evaluation, prompt and instruction refinement

**Integration:** MCP, filesystem tools, JSON, VS Code, Node.js

**Professional Skills:** Problem solving, model evaluation, business analysis, documentation, testing, iterative improvement, and responsible AI practices

## 16. About Me

**Jiming Sun**

MBA Candidate – Business Analytics  
Goodman School of Business, Brock University  
St. Catharines, Ontario, Canada

My interests include business analytics, financial services technology, AI-enabled workflow improvement, and responsible enterprise AI applications.

This portfolio reflects my interest in combining practical business knowledge with analytical and emerging AI technologies.

---

*This repository contains academic findings, aggregated model metrics, reusable AI instructions, and a local MCP prototype. It does not contain confidential customer data or claim production deployment.*
