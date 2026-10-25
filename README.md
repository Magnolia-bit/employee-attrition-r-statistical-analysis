# Employee Attrition & Income Analysis Using R

**R Programming | Statistical Analysis | Hypothesis Testing | Linear Regression**

## Project Overview

This project examines employee age, attrition and monthly income using the IBM HR Analytics Employee Attrition dataset.

The analysis compares the ages of employees who left and remained, explores relationships between employee characteristics, and investigates how the association between age and income changes when working experience is included in a regression model.

Completed as part of guided Data Analytics Accelerator (DAA) learning.

## Key Findings

### 1. Employees who left were younger on average

| Attrition status | Mean age |
|---|---:|
| Left | 33.61 years |
| Remained | 37.56 years |

Employees who left were approximately **3.95 years younger on average**.

A Welch two-sample t-test found evidence of a difference in mean age (*p* < 0.001). The estimated difference, calculated as left minus remained, had a **95% confidence interval of −5.29 to −2.62 years**.

This describes an association in the dataset. It does not establish that age causes attrition or explain why employees left.

### 2. Age was positively associated with income in the simple model

The model `MonthlyIncome ~ Age` estimated an increase of approximately **256.57 income units per month for each additional year of age**.

Its R² was **0.248**, meaning it explained approximately **24.8% of the observed variation in monthly income** within this dataset.

This model considers age alone. Its coefficient may reflect other characteristics associated with age, including accumulated working experience.

### 3. Including experience substantially changed the age–income relationship

Adding total working years increased R² from **0.248 to 0.599**.

| Model | Age coefficient | Total working years coefficient | R² |
|---|---:|---:|---:|
| Age only | 256.57 | — | 0.248 |
| Age and total working years | −26.87 | 489.13 | 0.599 |

In the multiple regression:

- Each additional year of total working experience was associated with approximately **489.13 more monthly income units**, holding age constant.
- Each additional year of age was associated with approximately **26.87 fewer monthly income units**, holding total working experience constant.

The change in the age coefficient shows that the age–income association depends substantially on whether working experience is included. It does **not** mean that getting older causes someone’s income to fall.

The higher R² describes improved fit to the analysed data; it is not a measure of predictive accuracy on new employees.

## Dataset

**Source:** IBM HR Analytics Employee Attrition & Performance

| Dataset characteristic | Value |
|---|---|
| Employee records | 1,470 |
| Original variables | 35 |
| Data format | CSV |
| Primary tool | R / RStudio |
| Analysis type | Exploratory and statistical |

The dataset includes employee demographics, education, income, working experience, job characteristics and attrition status.

## Research Questions

1. Does mean age differ between employees who left and those who remained?
2. How are age and total working years associated with monthly income?
3. What relationships and distributional differences appear across other employee characteristics?

## Analytical Methods

### Exploratory Analysis

Imported and inspected the dataset, selected numerical variables and explored relationships using:

- Correlation matrices with `cor()`.
- Scatterplot matrices with `pairs()`.
- Labelled education categories created with `factor()`.
- Box plots comparing age, experience and income across groups.

Education is an ordinal variable. Correlations involving its numerical codes require caution because the gaps between education categories are not necessarily equal.

### Welch Two-Sample t-Test

Used `t.test()` to compare mean age between employees with and without attrition.

The Welch test allows the two groups to have unequal variances and sample sizes.

### Linear Regression

Estimated two models using `lm()`:

- **Simple regression:** `MonthlyIncome ~ Age`
- **Multiple regression:** `MonthlyIncome ~ Age + TotalWorkingYears`

Compared coefficients and R² to examine how including working experience changes the estimated association between age and income.

## Skills Demonstrated

- R programming and data selection.
- Exploratory analysis and visualisation using base R.
- Correlation analysis and hypothesis testing.
- Simple and multiple linear regression.
- Interpretation of coefficients, confidence intervals and model fit.
- Analysis reporting using R Markdown.

## Repository Contents

| File | Description |
|---|---|
| [employee_attrition_analysis.Rmd](employee_attrition_analysis.Rmd) | R Markdown source containing the analysis |
| [employee_attrition_analysis.html](employee_attrition_analysis.html) | Rendered report containing charts and statistical outputs |
| [HR-Employee-Attrition.csv](HR-Employee-Attrition.csv) | Dataset used in the analysis |
| [HR_Data_Dictionary.pdf](HR_Data_Dictionary.pdf) | Reference information about the dataset variables |
| README.md | Project overview, findings, methods and limitations |

## How to Reproduce

**Requirements:**

- R.
- RStudio, recommended for rendering the report.
- The `rmarkdown` package and its rendering dependencies.

**Steps:**

1. Download or clone this repository.
2. Keep `HR-Employee-Attrition.csv` in the same directory as `employee_attrition_analysis.Rmd`.
3. Open the R Markdown file in RStudio.
4. Install `rmarkdown` and any missing rendering dependencies.
5. Select **Knit → Knit to HTML**.
6. Review the generated plots and statistical outputs.

The analysis itself primarily uses base R functions.

## Limitations

- This is an educational, exploratory analysis. Findings should not be assumed to represent a particular employer or the wider workforce.
- Associations do not establish causality.
- The income models omit potentially relevant variables such as job level, job role and education.
- Age and working experience are related, so their conditional coefficients require careful interpretation.
- Regression diagnostic checks are not included in the current report. Assumptions about linearity, residual variance and influential observations therefore need further assessment.
- No held-out evaluation was performed. Reported R² values describe fit to the analysed data.
- The regressions model monthly income; they do not predict employee attrition.

## Project Attribution and AI Assistance

I completed the R code and statistical analysis during guided Data Analytics Accelerator (DAA) learning, without AI assistance.

ChatGPT helped draft and format this README and explain the existing statistical outputs. The numerical findings reported here come from the saved R analysis results.

## Project Takeaway

The main lesson is that an association can change substantially when another relevant variable is included. Age was positively associated with income on its own, but that relationship changed after accounting for total working experience.

Interpreting the models requires understanding what each coefficient measures, what the model leaves out and why an association should not be presented as a causal effect.
