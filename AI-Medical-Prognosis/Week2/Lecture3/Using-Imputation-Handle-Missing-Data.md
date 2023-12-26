# Imputation

The lesson on "Imputation" discusses an alternative approach to complete case analysis, which involves filling in missing values through imputation. Imputation is the process of replacing missing data with estimated values based on available information. The two primary imputation methods covered are mean imputation and regression imputation. The lesson emphasizes modifying a machine learning pipeline to incorporate imputation before building and evaluating models. The context for the discussion is a case study on cardiovascular disease event prediction, where a prognostic model calculates the ten-year risk of experiencing a cardiovascular event. The input variables for the model include age and systolic blood pressure. The lesson walks through the machine learning pipeline, demonstrating how imputation is applied in this context to handle missing data in the dataset.

# Mean Imputation

The lecture on "Mean Imputation" involves the following key points:

- **Data Splitting:**
   - The dataset is divided into a training set and a test set, both containing missing values.

- **Exploration of Relationships:**
   - Focus on the training set to explore the relationship between age, blood pressure (BP), and cardiovascular disease (CVD) risk.
   - Graphical representation with age on the x-axis and BP on the y-axis.
   - Differentiating between patients who had a CVD event (red) and those who did not (blue).

- **Missing Blood Pressure Measurements:**
   - Some blood pressure measurements are missing (represented by vertical lines).
   - Patients' ages are known for these missing measurements.

- **Mean Imputation Method:**
   - Introduction of mean imputation as a simple method for handling missing values.
   - Average all observable BP values in the dataset to find the mean (e.g., mean BP = 140).

- **Imputation Process:**
   - For missing BP values, assign the mean BP value obtained from the dataset.
   - Graphically represented by assigning a value of 140 to missing points in the foreground.

- **Application to Test Set:**
   - The same mean BP value (140) obtained from the training set is used to impute missing values in the test set.
   - Emphasis on not re-computing mean in the test set due to potential size limitations.

- **Quiz Scenario:**
   - Challenge to impute blood pressure values for patients 101 and 111 in the test set using mean imputation.
   - Reminder to use the mean blood pressure from the training set for imputation in the test set.

- **Rationale:**
   - Explanation of why the mean from the training set is used in the test set. The training set is considered more representative, especially if both sets are drawn from the same distribution.

# Regression Imputation

The lecture discusses the limitations of mean imputation in preserving relationships between variables, specifically in the context of blood pressure (BP) and age. Mean imputation results in a constant value for BP across all ages, neglecting the observed upward trend between age and BP. To address this, the lecturer introduces regression imputation as an alternative method.

In regression imputation, a linear model is employed to capture the relationship between age and BP. The goal is to learn a linear equation of the form y = mx + c, where y represents BP, x represents age, m is the slope of the line, and c is the y-intercept. By fitting this linear model to the training set data with missing values, the lecture demonstrates that the resulting equation, such as 0.6 times age plus 115, can effectively capture the relationship between age and systolic BP. This regression imputation method is presented as a way to preserve and reflect the underlying correlations between variables, in contrast to the limitations of mean imputation.

# Calculate Imputed Values

The speaker discusses a method for handling missing blood pressure (BP) values in a dataset. The approach involves creating a linear equation based on age to impute missing BP values. Specifically, for a given age, the BP value is calculated by multiplying the age by 0.6 and then adding 115. This equation is applied to fill in missing BP values for patients in both the training and test sets. The lecture contrasts two imputation methods: mean imputation and regression imputation. Mean imputation involves using the mean of observed BP values, while regression imputation entails learning a linear function relating age to BP. The process includes splitting the dataset into training and test sets, learning an imputation model from the training data, applying the model to fill in missing values, and subsequently building a prognostic model for predictive analysis. The speaker emphasizes that after imputation, both the training and test sets are devoid of missing values, allowing for the development and application of a prognostic model.