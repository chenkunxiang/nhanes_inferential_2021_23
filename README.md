# NHANES Data Analysis Assignment

This project examines relationships between demographic, behavioral, and health variables using data from the National Health and Nutrition Examination Survey (NHANES). All analyses were completed in Google Colab, with each step following the structure and workflow used in the course notebooks.

## Objectives

The goal of this project is to analyze associations and differences across key NHANES variables using appropriate statistical methods. The project includes several guided research questions as well as one original, student-designed analysis.

---

## Questions and Analysis

### **Question 1** 
**Is there an association between marital status and education level?**  

- **Variables**: `DMDMARTZ` (Marital Status), `DMDEDUC2` (Education Level)  
- **Recoding**:
  - Kept valid marital status and education codes only
	- Recoded marital status into two categories:
	  - Married (1, 6)
	  - Not Married (2–5)
	- Recoded education level into:
	  - Bachelor or Higher (code 5)
  	- Less than Bachelor (codes 1–4)
- **Test Used**: Chi-square test of independence  
- **Purpose**: To examine whether educational attainment differs between married and non-married adults.
- **Analysis**: A contingency table was created comparing marital status to education level, and a chi-square test was performed to determine whether the distribution of education levels differed across marital groups. A bar plot was included to show the count of individuals in each education category for married vs non-married groups.
This analysis evaluated whether marital status is associated with higher or lower educational attainment in the NHANES population.

---

### **Question 2**  
**Is there a difference in mean sedentary behavior time between married and non-married individuals?**  

- **Variables**: `DMDMARTZ` (Marital Status), `PAD680` (Sedentary Behavior Time)  
- **Recoding**:
  - Removed invalid or missing codes for marital status and sedentary time (e.g., 7777, 9999)
  - Recoded marital status into two groups: Married (1, 6) and Not Married (2–5)
- **Test Used**: ANOVA
- **Purpose**: To determine whether married and non-married individuals differ in their average amount of daily sedentary behavior.
- **Analysis**: The ANOVA compared mean sedentary time between the two marital status groups. On average, married individuals reported lower sedentary time than those who were not married. The F-statistic and p-value indicated whether this difference was statistically significant. A boxplot was included to visualize the distribution of sedentary time across the two groups.
---

### **Question 3**  
**How do age and marital status affect systolic blood pressure?**  

- **Variables**: `RIDAGEYR` (Age), `DMDMARTZ` (Marital Status), `BPXOSY3` (Systolic BP)  
- **Recoding**:
  - Removed invalid codes for marital status (77, 99) and missing blood pressure values
  - Recoded marital status into two groups: Married (1, 6) and Not Married (2–5)
  - Created a simple age grouping (0–79 vs 80+) to account for older adults in the data
- **Test Used**: ANOVA  
- **Purpose**: To compare whether systolic blood pressure differs between married and non-married individuals.
- **Analysis**: The ANOVA tested mean systolic blood pressure across marital groups. Married adults showed a lower average systolic blood pressure (mean ≈ your output) compared to non-married adults. The F-test examined whether this difference was statistically significant. A boxplot was included to visualize the distribution of systolic blood pressure across the two groups.

---

### **Question 4**  
**Is there a correlation between self-reported weight and minutes of sedentary behavior?**  

- **Variables**: `WHD020` (Weight), `PAD680` (Sedentary Behavior Time)  
- **Cleaning**:
  - Removed invalid entries for both variables (7777, 9999)
  - Ensured both columns were numeric and dropped remaining missing values
  - Merged the relevant datasets using SEQN
- **Test Used**: Pearson correlation
- **Purpose**: To measure the strength and direction of the linear relationship between sedentary time and weight.
- **Analysis**: The Pearson correlation between sedentary behavior time and weight was 0.16, with a statistically significant p-value. While the association is positive, it is very weak, indicating that individuals who spend more time sedentary tend to weigh slightly more — but the effect is minimal and not practically strong. A scatterplot with a regression line was included to visualize the relationship.

---

### **Question 5 (Creative Analysis)**  
**Is there a difference in average weight between married and non-married individuals?**  
I designed this analysis independently to explore whether marital status is associated with meaningful differences in self-reported weight.

- **Variables**: `DMDMARTZ` (Marital Status), `WHD020` (Self-Reported Weight)  
- **Recoding**:
  - Removed invalid or missing marital status and weight codes
  - Recoded marital status into two groups: Married (1, 6) vs Not Married (2–5)
- **Test Used**: Independent samples t-test
- **Purpose**: To compare whether married and non-married individuals differ in average weight.
- **Analysis**: The t-test showed the mean weight for married individuals compared to non-married individuals and evaluated whether this difference was statistically significant. This analysis allowed me to explore a simple but meaningful relationship between social factors and physical health using continuous outcome data.

---

## How to Run

1.	Open the notebook using Google Colab.
2.	Follow the instructions in the notebook to download and process the necessary NHANES datasets, including DEMO_L.xpt, WHQ_L.xpt, DPQ_L.xpt, and others.
3.	Execute each analysis cell in order to clean, merge, and analyze the data.
4.	Review the results and visualizations to interpret your findings and extract insights.

---

## Notes

- All variables were cleaned and recoded according to NHANES documentation before running any analysis.
- All .xpt files were converted to .csv using R for consistency and ease of use in Python.
- Invalid or special NHANES missing codes (e.g., 7777, 9999, 77, 99) were removed to prevent incorrect statistical results.
- Analyses were performed entirely in Google Colab for reproducibility, with clear documentation in each step.
- Statistical tests were selected based on variable type and research question (e.g., chi-square for categorical associations, t-test/ANOVA for mean comparisons, Pearson correlation for continuous variables).
- Visualizations such as boxplots, bar charts, regression plots, and contingency tables were included to support interpretation of each statistical result.
- This project demonstrates the ability to work with real-world public health data, apply statistical methods, and interpret findings in context.

---

