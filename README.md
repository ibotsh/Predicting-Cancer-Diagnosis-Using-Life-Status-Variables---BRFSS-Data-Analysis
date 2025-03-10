# Predicting Cancer Diagnosis Using Life Status Variables: BRFSS 2021 Data Set Usinf R and Rstudio

## Overview:

This project explores whether certain life status factors are associated
with a cancer diagnosis (excluding skin cancer) using the **Behavioral
Risk Factor Surveillance System (BRFSS) 2021** dataset from the
**Centers for Disease Control (CDC)**. The main goal was to see if
variables like **exercise participation, health insurance provider, and
metropolitan status** had any significant relationship with cancer
diagnosis.

The idea was to build a model that could predict cancer diagnosis based
on these variables. I cleaned the data, ran some visualizations, and
eventually compared two logistic regression models to determine which
factors had the most predictive power.

![000016](https://github.com/user-attachments/assets/0bf8f32d-efd4-469c-a1d0-a424bf4ed20e)
![000010](https://github.com/user-attachments/assets/c97ed126-ad8d-4e4c-8af4-44b211ede06e)

### **Approach:**

-   **Data Cleaning:** Removed missing values and irrelevant responses
    (e.g., refused to answer).

-   **Data Transformation:** Converted categorical variables into
    factors with clear labels for easier interpretation.

-   **Exploratory Data Analysis:** Created visualizations (bar charts,
    stacked charts) to identify patterns.

-   **Statistical Modeling:** Built and compared two logistic regression
    models using Akaike Information Criterion (AIC) to determine which
    set of variables most accurately predicted cancer diagnosis.

-   **Key Outcome:** The model including **insurance provider, exercise
    participation, and residential status** was the best predictor for
    cancer diagnosis.

## Data Source:
**IMPORTANT:**
- Must download **'brfss2021.csv'** from website provided below in order to run analysis in R. Data file could possably be renamed, if that is the case rename the 'brf <- read_csv("brfss2021.csv", show_col_types = FALSE)' under "Loading data" within the project file, to the approprate file name.

-   **Dataset:** CDC BRFSS 2021 (Behavioral Risk Factor Surveillance
    System)

-   **Source Link:**
    <https://www.cdc.gov/brfss/annual_data/annual_2021.html>

## Objective:

The primary goal of this project was to explore the correlation between
having a cancer diagnosis (not skin-related) and three life status
factors:

-   **Exercise Participation:** Whether the respondent engaged in any
    exercise within the last month.

-   **Primary Health Insurance:** The primary type of health insurance
    the respondent has.

-   **Metropolitan Residential Status:** Where the respondent lives in
    relation to a major city (city center, suburbs, rural, etc.).

I wanted to see if there were any patterns in these variables that might
help predict a cancer diagnosis.

## Process:

### 1. **Data Cleaning**

The raw data had a lot of missing, refused, or irrelevant responses, so
the first step was cleaning it up. I removed any rows where respondents
either refused or had uncertain response. I also dropped some insurance
types (like Children's Health Insurance) since it wasn't relevant to
adults.

Key Cleaning Steps:

-   Removed NAs and irrelevant responses.

-   Combined the four key variables (cancer diagnosis, exercise,
    insurance type, metro status).

-   Converted categorical variables to factors to make visualization and
    modeling easier.

### 2. **Exploratory Data Analysis**

I started by visualizing each variable to get a sense of the
distribution of responses. I used bar charts to visualize:

-   **Cancer Diagnosis Rates** (Yes/No)

-   **Exercise Participation Rates** (Yes/No)

-   **Metropolitan Status** (City center, suburbs, rural)

-   **Primary Insurance Coverage**

I also created bivariate graphs to see if there were any visible trends
between cancer diagnosis and the predictor variables. For example,
comparing exercise participation vs. cancer diagnosis.

### 3. **Modeling**

I built two logistic regression models to predict the likelihood of a
cancer diagnosis based on the predictor variables:

-   **Model 1:** Used only **Metropolitan Status** as the predictor.

-   **Model 2:** Included **Metropolitan Status, Exercise Participation,
    and Health Insurance Type**.

I compared the models using the **Akaike Information Criterion (AIC)**
to see which model was a better fit. Model 2 performed better, likely
because adding Exercise and Insurance provided more predictive power.

## Main Findings:

-   People with **Medicare, Medicaid, or Medigap** had a higher
    likelihood of a cancer diagnosis. This makes sense as these plans
    typically serve older adults or those with disabilities.

-   Exercise participation showed a slight negative relationship with
    cancer diagnosis, meaning those who exercised monthly had a lower
    chance of reporting cancer.

-   People living in metro city centers had a lower reported rate of
    cancer, which may be tied to better healthcare access or higher
    income levels, though further analysis would be needed to confirm.

## Issues:

-   **Limited Scope:** The BRFSS dataset does not capture all lifestyle
    factors (like diet or family history) that could significantly
    impact cancer risk.

-   **Self-Reported Data:** Responses were self-reported, which can
    introduce bias.

-   **Age Factor:** While insurance type gave some hints about age
    (since Medicare users are often older), I did not have seamless age
    data to control for age effects.

## Future Improvements:

-   **Add More Predictors:** Including variables like diet, income, age
    or healthcare access would yield more insights.

## How to Run It:

1.  Clone the repository.

2.  Load the **BRFSS 2021 dataset** in CSV format into your working
    directory.

3.  Run the scripts below as is.
