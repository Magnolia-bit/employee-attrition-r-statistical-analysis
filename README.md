# Employee Attrition & Income Analysis Using R

**R Programming | Statistical Analysis | Hypothesis Testing | Linear Regression**

---

## Project Overview

This project explores relationships between employee characteristics, attrition and monthly income using the IBM HR Analytics Employee Attrition dataset.

The objective was to apply statistical methods in R to investigate employee demographics, identify relationships between numerical variables and examine how age and working experience relate to income.

**Project context:** Completed during guided data analytics learning, providing practical experience with R programming and applied statistics.

## Dataset

**Source:** IBM HR Analytics Employee Attrition & Performance

| Dataset characteristic | Value |
|---|---|
| Employee records | 1,470 |
| Variables | 35 |
| Data format | CSV |
| Primary tool | R / RStudio |
| Analysis type | Exploratory and statistical |

The dataset includes employee demographics, education, monthly income, working experience, job characteristics and attrition status.

---

## Research Questions

The analysis investigates three main questions:

1. **Employee attrition:** Does average employee age differ between those who leave and those who remain?
2. **Income and experience:** How are employee age and total working years associated with monthly income?
3. **Employee characteristics:** What relationships exist between education, experience and other numerical variables?

---

## Analytical Methods

### 01 — Exploratory Data Analysis

Used R to import, inspect and explore employee records.

Techniques included:

- Data import using `read.csv()`
- Data-frame indexing and variable selection
- Correlation matrices using `cor()`
- Scatterplot matrices using `pairs()`
- Categorical variable conversion using `factor()`
- Box plots to explore distributions across employee groups

### 02 — Hypothesis Testing

Applied a Welch two-sample t-test to compare employee ages between those who left and those who remained.

**R function:** `t.test()`

The test examines whether there is statistical evidence of a difference in mean employee age between the two groups.

### 03 — Simple Linear Regression

Examined the relationship between employee age and monthly income.

**Model:** `MonthlyIncome ~ Age`

**R function:** `lm()`

### 04 — Multiple Linear Regression

Extended the income model to include total working experience.

**Model:** `MonthlyIncome ~ Age + TotalWorkingYears`

**R function:** `lm()`

This model examines how age and working experience are associated with monthly income when included together.

---

## Skills Demonstrated

- R programming and data manipulation
- Exploratory data analysis
- Data visualisation using base R
- Correlation analysis
- Hypothesis testing and statistical inference
- Simple and multiple linear regression
- Working with numerical and categorical variables
- Reproducible analysis using R Markdown

---

## Repository Contents

| File | Description |
|---|---|
| [employee_attrition_analysis.Rmd](employee_attrition_analysis.Rmd) | R Markdown source code and statistical analysis |
| [employee_attrition_analysis.html](employee_attrition_analysis.html) | Rendered analytical report |
| `HR-Employee-Attrition.csv` | Original dataset, where redistribution is permitted |
| README.md | Project documentation and methodology |

---

## How to Reproduce

**Requirements:**

- R
- RStudio (recommended)
- R Markdown and its rendering dependencies
- IBM HR Analytics Employee Attrition dataset

**Instructions:**

1. Download or clone this repository.
2. Place `HR-Employee-Attrition.csv` in the same directory as the R Markdown file.
3. Open `employee_attrition_analysis.Rmd` in RStudio.
4. Install any missing R Markdown rendering dependencies.
5. Select **Knit → Knit to HTML**.
6. Review the generated charts and statistical outputs.

The analysis primarily uses base R functions.

---

## Limitations

This is an exploratory statistical analysis rather than a predictive employee attrition model.

- Statistical associations do not establish causality.
- The dataset may not represent real-world employee populations.
- Regression estimates may be affected by omitted explanatory variables.
- Correlation does not necessarily imply a causal relationship.
- The regression models examine monthly income rather than predicting employee attrition.

---

## Project Attribution & AI Disclosure

The R analysis was completed during guided Data Analytics Accelerator (DAA) learning, independently of AI assistance.

AI was used solely to write and format this GitHub README in Markdown. The underlying R code, statistical analysis and analytical methods were completed without AI assistance.

---

## Project Takeaway

This project provided practical experience using R to explore data, visualise relationships and apply statistical techniques.

The central learning was understanding how **correlation, hypothesis testing and regression can be used to investigate analytical questions**, while recognising the assumptions and limitations associated with statistical interpretation.
