# Examples of Prognostic Tasks

In the "Examples of Prognostic Tasks" lesson, the instructor explores clinical scenarios where prognosis is a routine practice. The lesson aims to provide an understanding of what inputs and outputs are involved in prognostic tasks and how different inputs may be weighted. Prognostic models are described as systems that take a patient's profile as input and generate a risk score as output. The patient profile encompasses clinical history (major illnesses, previous procedures), physical exam findings (vital signs, temperature, blood pressure), and various tests (lab tests like complete blood count, imaging such as CT scans).

Prognostic models evaluate one or more elements from the patient profile and produce a risk score, which can be either arbitrary numbers or probabilities. An example is presented to illustrate a prognostic model for heart disease. In this model, two patient features (smoking status and age) are used to calculate the risk score. For instance, a patient over the age of 75 who is a smoker might receive a score of two (one for smoking, one for age). The lesson then introduces the concept of assigning weights or coefficients to features, reflecting their relative importance. In this example, being over 75 is considered twice as risky as smoking, so the age feature is assigned a coefficient of 2, while smoking is assigned a coefficient of 1. The final risk score is calculated by multiplying the coefficients by the corresponding feature values, resulting in a total risk score of three. This example demonstrates how prognostic models can incorporate weighted factors to provide a more nuanced risk assessment.

# Atrial Fibrillation

In the "Atrial Fibrillation" lesson, the focus is on a risk calculator used for patients with atrial fibrillation (AF), a common abnormal heart rhythm associated with an increased risk of stroke. The specific model discussed is the CHA2DS2-VASc score, which predicts the one-year risk of stroke for patients with AF. The acronym represents the features used in the patient profile.

The instructor walks through an example involving a 70-year-old male patient diagnosed with AF, hypertension, and diabetes. The goal is to calculate this patient's one-year risk of stroke using the CHA2DS2-VASc score. The lesson emphasizes that while there are medical terms involved, the key is to recognize them as features within the patient profile.

The prognostic model provides coefficients or weights associated with each feature. The process involves entering the patient's values into the table, activating relevant features (such as age, hypertension, and diabetes), and multiplying each value by its corresponding coefficient. The final step yields the risk score. In this specific example, the patient's risk score is calculated to be three.

This exercise demonstrates a practical application of a prognostic model in clinical practice, highlighting how such models use patient profiles to generate risk scores for specific health outcomes.

# Liver Disease Mortality

In the "Liver Disease Mortality" lesson, the instructor discusses a score used for patients over the age of twelve who are on liver transplant waiting lists. The score in focus is the Model for End-Stage Liver Disease (MELD) Score, which estimates the three-month mortality for patients and influences the speed at which a patient might receive a liver transplant.

The example involves computing the MELD score for a 50-year-old woman based on lab studies showing specific values. The MELD model introduces two noteworthy features. Firstly, the natural logarithm (log) of certain lab values is used as features in the model. This transformation is applied when there is a belief that the relationship between risk and features is linear in the natural log of the features. Secondly, an intercept feature is present with a value of 1, representing the expected risk score when all other values are 0.

The computation involves entering the natural log of relevant lab values, multiplying them by their coefficients, and summing up the results to obtain the MELD score. In the example, the resulting score is 1.01, and for convention, this score is multiplied by 10 and rounded, yielding an output MELD score of 10. The lesson emphasizes that the MELD score, in isolation, does not directly indicate the probability of survival at three months. Instead, it is valuable for making comparisons among patients based on their MELD scores.

# Risk of Heart Disease

In the "Risk of Heart Disease" lesson, the focus is on estimating the ten-year risk of heart disease for patients aged twenty years or older who do not already have heart disease, using the ASCVD Risk Estimator Plus. The instructor walks through the computation of the ASCVD score for a specific patient—a 55-year-old African-American woman—with various features.

Key points from the lesson include:

- **New Features:**
   - **Natural Log Transformation:** Similar to previous examples, some features involve taking the natural logarithm of certain values.
   - **Interaction Terms:** The model introduces features that are the product of two values, such as the natural log of age multiplied by the natural log of HDL-C. These are termed "interaction terms."

- **Negative Coefficients:**
   - Some features have negative coefficients, indicating that their contribution lowers the overall risk score. For example, the natural log of HDL-C (high-density cholesterol) has a negative coefficient. This aligns with the understanding that higher levels of HDL-C, often considered "good cholesterol," are associated with a lower risk of heart disease.

- **Risk Score Computation:**
   - The process of computing the risk score involves filling in values based on the patient's information, multiplying each value by its corresponding coefficient, and summing up the results.

- **Conversion to Risk Probability:**
   - The sum obtained from the computation is converted to a risk score using a specific formula. The instructor mentions that the details of the formula are not crucial for understanding the concept, but it is utilized to arrive at a ten-year probability of heart disease for the patient. In the given example, the calculated probability is 3%.

The lesson provides insights into how features, transformations, interaction terms, and coefficients are employed in a predictive model to estimate the risk of heart disease over a ten-year period for a specific patient.