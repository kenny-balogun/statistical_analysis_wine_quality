# Statistical Analysis of Wine Quality  

## Overview  

The wine industry is highly competitive, and **data-driven insights** can give winemakers an edge in improving quality and increasing customer satisfaction.  
This project applies **statistical analysis, hypothesis testing, and regression modeling** to assess the physicochemical properties that influence wine quality.  

By analyzing **red and white wine variants of the Portuguese Vinho Verde wine**, this study provides actionable insights for **quality optimization and production improvements**.  

## Objectives  

- Compare the **physicochemical properties** of red and white wines to understand how they influence quality.  
- Perform **hypothesis testing** to uncover key factors affecting wine quality.  
- Develop **predictive models** to assess wine quality based on its chemical composition.  

## Dataset  

The dataset, created by **Cortez et al. (2009)**, consists of two subsets:  
- **Red Wine Data** (1,599 samples)  
- **White Wine Data** (4,898 samples)  

Each subset contains **11 physicochemical properties** as input variables and a **quality score (3-9)** as the target variable.  

### Key Features  

- **Fixed Acidity**  
- **Volatile Acidity**  
- **Citric Acid**  
- **Residual Sugar**  
- **Chlorides**  
- **Free Sulfur Dioxide**  
- **Total Sulfur Dioxide**  
- **Density**  
- **pH**  
- **Sulphates**  
- **Alcohol**  

### Ethical Considerations  

- **Data is publicly available and licensed under Open Data Commons.**  
- **Anonymized dataset** ensuring no personal data is included.  

## Exploratory Data Analysis (EDA)  

Key insights from the **data exploration phase**:  

- **No missing values** were present in the dataset.  
- **Duplicate Removal**:  
  - **240 duplicate rows** in red wine and **937 in white wine** were removed.  
- **Quality Distribution**:  
  - Most wines had a **mid-range quality score (5 or 6)**.  
  - Very few wines were rated as **excellent (9) or poor (3)**.  
- **Feature Distributions**:  
  - Red wines exhibited **higher acidity**, while white wines had **higher residual sugar and sulfur dioxide**.  

## Statistical Analysis  

### **1. Correlation Analysis**  

- **Positive Correlations with Quality:**  
  - **Alcohol:** Higher alcohol content is linked to better wine quality.  
  - **Sulphates:** Moderate positive correlation with quality.  
- **Negative Correlations with Quality:**  
  - **Volatile Acidity:** Higher levels reduce wine quality.  
  - **Density:** Lower density is associated with higher-quality wines.  
- **Wine Type Influence:**  
  - White wines have **higher residual sugar and total sulfur dioxide**, while red wines have **higher volatile acidity and chlorides**.  

### **2. Hypothesis Testing**  

Four key hypotheses were tested to uncover significant differences in wine properties.  

#### **Hypothesis 1: Association Between Wine Type and Quality**  
- **Chi-Square Test of Independence** showed a **significant association** between wine type and quality.  
- **Fewer high-quality red wines** than expected, while white wines had a **higher proportion of high-quality samples**.  

#### **Hypothesis 2: Difference in Mean pH Between Red and White Wines**  
- **Two-Sample t-Test** rejected the null hypothesis.  
- Red wines had **higher average pH levels** than white wines.  

#### **Hypothesis 3: Difference in Chloride Levels Between Red and White Wines**  
- **Mann-Whitney U Test** revealed a **significant difference**.  
- **Red wines had slightly higher chloride levels** than white wines.  

#### **Hypothesis 4: Difference in Alcohol Content by Wine Quality**  
- **Kruskal-Wallis Test** confirmed a **statistically significant difference in alcohol content** across quality levels.  
- **High-quality wines had significantly higher alcohol content**.  

## Regression Modeling  

To predict wine quality, logistic regression models were developed.  

### **1. Predicting Wine Quality (High vs. Low)**  

- **Logistic Regression Model** trained on physicochemical properties.  
- **Most important predictors:**  
  - **Alcohol** (strongest positive predictor).  
  - **Volatile Acidity** (negative impact).  
  - **Residual Sugar & Sulphates** (moderate influence).  
- **Final Model Achieved:**  
  - **Accuracy:** 74%  
  - **AUC-ROC Score:** 0.79  

### **2. Predicting Wine Type (Red or White)**  

- **Logistic Regression Model** using physicochemical properties.  
- **Key predictors:**  
  - **Volatile Acidity & Chlorides** → higher in red wines.  
  - **Residual Sugar & Sulfur Dioxide** → higher in white wines.  
- **Final Model Achieved:**  
  - **Accuracy:** 85%  

### **3. Predicting Wine Density**  

- **Multiple Linear Regression** model developed to predict wine density.  
- **Key predictors:**  
  - **Volatile Acidity, Residual Sugar, and Alcohol**.  
- **R² Score:** 0.82 (model explains 82% of variance in density).  

## Key Findings  

- **Alcohol content is the strongest predictor of wine quality** – higher alcohol leads to better ratings.  
- **Volatile acidity negatively affects quality** – reducing it can improve taste.  
- **Residual sugar is higher in white wines but does not significantly impact quality.**  
- **Wine type is significantly associated with quality.**  

## Business Implications  

- **Winemakers can optimize production by monitoring alcohol and acidity levels.**  
- **Targeted adjustments to physicochemical properties can enhance wine taste and quality.**  
- **By controlling volatile acidity and sulfur dioxide levels, manufacturers can improve customer satisfaction.**  
- **Statistical insights can guide pricing strategies based on wine quality predictions.**  

## Recommendations  

- **Enhance alcohol monitoring** during production, as it significantly influences quality.  
- **Reduce volatile acidity** in red wines to improve taste and perception.  
- **Optimize sulphate levels** to enhance stability and preservation.  
- **Use predictive models to classify wines and maintain quality consistency.**  
 

## How to Run  

### Clone the Repository  

```sh
git clone https://github.com/kenny-balogun/statistical_analysis_wine_quality.git
```

### Install Dependencies

```sh
Rscript -e "install.packages(c('tidyverse', 'caret', 'readxl', 'ggthemes', 'corrplot', 'skimr', 'FSA', 'RVAideMemoire', 'car'))"
```
### Run the Analysis

Open RStudio and load the statistical_analysis_wine.rmd file.
To knit the markdown file into a PDF, run:

```sh
rmarkdown::render("statistical_analysis_wine.rmd")
```
