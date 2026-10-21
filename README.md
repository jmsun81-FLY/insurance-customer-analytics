# Insurance Customer Analytics: Predictive Modelling & Customer Segmentation

### MBA Business Analytics Project | Brock University | 2026

## 1. Project Overview

This academic team project explored how machine learning and business analytics could improve customer targeting and decision-making in the auto insurance industry.

Using approximately 100,000 historical insurance quotation records, our team investigated two key business questions:

1. Which factors are associated with successful conversion of insurance quotations into purchased policies?
2. How can predictive models and customer segmentation support more efficient customer follow-up and resource allocation?

The project combined data preparation, customer segmentation, predictive modelling, model evaluation, and business recommendations.

In addition to the team-based analysis using Orange, I independently used Python to validate the results of three machine learning models. The Python results were broadly consistent with those obtained in Orange.

**Project Information**
- Institution: Goodman School of Business, Brock University
- Program: Master of Business Administration – Business Analytics
- Course: MBAB 5P11 – Introduction to Business Analytics
- Year: 2026
- Project Type: Academic Team Project with Independent Python Validation

## 2. Tools and Technologies

**Data Analytics and Machine Learning**
- **Orange Data Mining:** Model development, parameter tuning, evaluation, and comparison
- **Python:** Independent validation of machine learning model results
- **IBM SPSS Statistics:** Statistical analysis and customer segmentation
- **Microsoft Excel:** Exploratory data analysis and supporting calculations

**Machine Learning Methods**
- Decision Tree
- Logistic Regression
- Neural Network
- Two-Step Clustering

**Analytical Techniques**
- Data preprocessing and feature selection
- Exploratory Data Analysis (EDA)
- Class imbalance analysis
- Oversampling and undersampling
- Cross-validation
- Hyperparameter tuning
- Model performance comparison
- Independent cross-tool validation
- Business interpretation of analytical results

**Evaluation Metrics**
- Area Under the ROC Curve (AUC)
- Classification Accuracy
- Precision
- Recall
- F1 Score
- Matthews Correlation Coefficient (MCC)

## 3. Business Problem

Insurance companies receive many quotation requests, but only a portion of them become purchased policies.

Treating every quotation as equally likely to convert can lead to inefficient allocation of marketing and customer service resources.

The objective of this project was to evaluate whether data-driven analytical techniques could help identify higher-potential quotations and provide meaningful customer segmentation.

The intended business value was to support more informed follow-up prioritization, differentiated customer engagement, and resource allocation decisions.

## 4. Analytical Workflow

### Step 1: Data Exploration and Preparation

The dataset contained approximately 100,000 insurance quotation records with customer, vehicle, driving, and insurance-related information.

The team explored variable distributions, missing values, potential predictors, and data quality issues.

A significant challenge was class imbalance:

- Approximately 78.12% of quotations were not converted into policies.
- Approximately 21.88% resulted in purchased policies.

Initial models tended to favor the majority class, limiting their usefulness in identifying potential customers.

To address this issue, different sampling strategies were evaluated, including oversampling and undersampling.

A balanced modelling sample was subsequently used to improve the identification of the minority class.

### Step 2: Customer Segmentation

The team applied Two-Step Clustering to identify meaningful customer groups based on demographic characteristics, driving patterns, vehicle information, and existing insurance relationships.

Multiple clustering specifications were evaluated, including alternative variable combinations and two-, three-, and four-cluster solutions.

The final three-cluster solution was selected based on cluster quality, segment balance, and business interpretability.

The resulting segments demonstrated different quotation conversion patterns, supporting potential improvements in customer engagement strategies.

### Step 3: Predictive Model Development

Three classification models were developed and compared using Orange Data Mining.

**Decision Tree**

The team tested alternative configurations involving:

- Minimum leaf size
- Minimum split size
- Maximum tree depth
- Branching approach

Sixteen configurations were evaluated to identify a suitable balance between model performance, complexity, and interpretability.

**Logistic Regression**

The team examined regularization approaches and different parameter settings.

Lasso (L1) regularization was selected, with a final regularization parameter of C = 0.1.

**Neural Network**

The team experimented with:

- Hidden-layer configurations
- Activation functions
- Optimization methods

The objective was to determine whether a more complex model could improve predictive performance compared with simpler classification approaches.

### Step 4: Model Evaluation and Comparison

All three models were evaluated using a consistent cross-validation approach.

Because the original dataset was imbalanced, accuracy alone was insufficient to assess model usefulness.

Particular attention was given to AUC, Recall, Precision, F1 Score, and MCC.

The comparison considered both predictive performance and practical business interpretation.

### Step 5: Independent Validation Using Python

In addition to the modelling completed in Orange, I independently used Python to perform a second validation of the three classification models:

- Decision Tree
- Logistic Regression
- Neural Network

The purpose was to cross-check the Orange modelling results using another analytical environment.

The Python validation produced results broadly consistent with those obtained in Orange.

This exercise strengthened my understanding of model evaluation, analytical consistency, and the importance of independently checking results rather than relying on a single tool.

It also reinforced the need to consider differences in data preprocessing, model configuration, and evaluation methods when interpreting results across analytical environments.

## 5. Key Results

### Customer Segmentation Results

The analysis identified three customer segments with different observed quotation conversion rates.

| Segment | Approximate Conversion Rate |
|---|---:|
| Segment 1 | 24.8% |
| Segment 2 | 15.7% |
| Segment 3 | 22.3% |

The results suggested that existing insurance relationships, customer characteristics, and driving patterns could help inform differentiated follow-up strategies.

### Predictive Model Comparison

The final Orange model comparison produced the following results:

| Model | AUC | Recall | F1 Score |
|---|---:|---:|---:|
| Decision Tree | 0.626 | 0.658 | 0.620 |
| Logistic Regression | 0.634 | 0.652 | 0.618 |
| Neural Network | 0.633 | 0.646 | 0.616 |

**Recommended Model: Logistic Regression**

Logistic Regression was selected because it provided a competitive balance of predictive performance, stability, and interpretability.

Its AUC of 0.634 was the highest among the compared models.

Although Decision Tree achieved slightly higher Recall and F1 Score, Logistic Regression offered a strong combination of analytical performance and business interpretability.

The independently conducted Python validation produced broadly similar findings.

These results represent academic experimental findings and should not be interpreted as evidence of production-level predictive performance.

## 6. Business Recommendations

The analysis supported three potential business applications.

**1. Prioritize Customer Follow-Up**

Use predictive scores to help identify quotations that may warrant greater attention from sales or customer service teams.

**2. Develop Segment-Based Engagement Strategies**

Tailor follow-up approaches to different customer segments based on observed characteristics and conversion patterns.

**3. Monitor Model Performance**

Review data quality, predictive performance, and changes in customer behaviour before considering operational implementation.

The project emphasized that analytical models should support business judgment rather than automatically determine customer decisions.

## 7. My Technical Contribution

My individual contribution included conducting a secondary validation of the team's three machine learning models using Python.

I used this additional analysis to cross-check the results generated through Orange and evaluate whether the findings were broadly consistent across tools.

This work provided practical experience in:

- Applying Python to machine learning validation
- Comparing analytical results across different tools
- Interpreting model performance metrics
- Evaluating consistency and potential analytical limitations
- Connecting technical findings with business-oriented recommendations

The broader clustering, model development, and business recommendation activities were completed collaboratively as part of the academic team project.

## 8. Key Lessons Learned

**Data Quality Is Fundamental**

Missing values, feature selection, and class imbalance can significantly influence analytical results.

**Model Evaluation Requires Multiple Metrics**

A model with relatively high accuracy may still perform poorly when identifying an underrepresented target class.

**Independent Validation Is Valuable**

Rechecking machine learning results in Python provided an additional perspective on the consistency of findings obtained in Orange.

**More Complexity Does Not Always Mean Better Performance**

The Neural Network did not significantly outperform Logistic Regression, highlighting the importance of evaluating model complexity against practical benefits.

**Interpretability Matters**

Analytical solutions should be understandable to business stakeholders, particularly when recommendations influence customer engagement and resource allocation.

**Human Judgment Remains Essential**

Model outputs must be interpreted in context, with attention to data limitations, uncertainty, privacy, and responsible analytical practices.

## 9. Relevance to AI Prototyping and Enterprise Technology

Although this project focused on traditional machine learning rather than generative AI agents, the development process involved several principles relevant to AI solution building:

- Understanding and defining a business problem
- Translating business needs into analytical objectives
- Experimenting with alternative technical approaches
- Testing and evaluating outputs
- Performing independent validation
- Documenting findings and limitations
- Communicating results in business terms
- Considering responsible use and human oversight

The project helped build a foundation for exploring AI prototypes, automation workflows, and data-driven solutions in enterprise environments.

## 10. Data Privacy and Responsible Use

This GitHub repository provides a portfolio-level summary of an academic project.

To respect privacy and data-use restrictions:

- Original insurance quotation datasets are not published.
- No customer-level records or personally identifiable information are included.
- Findings are presented only in aggregated form.
- Original institutional or third-party datasets are not distributed.
- Any future demonstration datasets will be synthetic or explicitly authorized for public release.

**Project Status:** Completed academic analysis, independent model validation, and business recommendations.

**Deployment Status:** No production deployment is claimed.

## 11. Project Information

**Portfolio Maintainer:** Jiming Sun

**Institution:** Goodman School of Business, Brock University

**Program:** MBA – Business Analytics

**Project Year:** 2026

**Project Type:** Academic Team Project

**Individual Technical Focus:** Independent Python validation of machine learning models

**Areas of Interest:**
- Business Analytics
- Machine Learning
- Model Testing and Validation
- AI-Assisted Business Solutions
- Financial Services Analytics
- Business Process Improvement

---

## Reusable AI Skill and MCP Integration

As an extension of this academic project, I developed and tested a reusable AI Model Evaluation Skill using VS Code and GitHub Copilot.

### What I Built

- Created a reusable SKILL.md to guide AI-assisted model evaluation.
- Configured a filesystem MCP server to read authorized JSON data.
- Integrated the MCP tool with an AI-assisted evaluation workflow.
- Tested model comparison, class imbalance interpretation, and business recommendations.
- Refined the Skill after identifying missing sampling context.

### Technical Demonstration

The AI assistant successfully retrieved aggregated model metrics through an MCP filesystem tool and consulted the project's Model Evaluation Skill.

The MCP server was restricted to an authorized data directory to demonstrate controlled access.

### Project Resources

- [Reusable AI Skill](.github/skills/model-evaluation/SKILL.md)
- [Skill Testing Documentation](.github/skills/model-evaluation/TESTING.md)
- [MCP Configuration](.vscode/mcp.json)
- [Aggregated Model Metrics](examples/model_metrics.json)

### Key Learning

This prototype demonstrated how reusable AI instructions, external tool connections, iterative testing, and human oversight can support business-oriented analytics.

The project remains a local prototype and has not been deployed in a production environment.

*This repository documents academic project methodology, summarized findings, and learning outcomes. It does not contain confidential datasets, customer-level information, or proprietary source materials.*
