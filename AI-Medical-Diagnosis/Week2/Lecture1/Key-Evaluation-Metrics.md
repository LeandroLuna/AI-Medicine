# Key Evaluation Metrics

## Sensitivity, Specificity and Evaluation Metrics

- **Sensitivity:**
   - Definition: Sensitivity, also known as True Positive Rate or Recall, measures the ability of a model to correctly identify positive instances among all actual positive instances.
   - Application: In medical contexts, sensitivity indicates how well a model identifies patients with a particular condition among those who actually have the condition.

- **Specificity:**
   - Definition: Specificity measures the ability of a model to correctly identify negative instances among all actual negative instances.
   - Application: In the medical field, specificity indicates how well a model identifies healthy individuals among those who are actually healthy.

- **Evaluation Metrics:**
    - Context: The lecture emphasizes the importance of evaluating deep learning models in medicine due to the high impact of decisions.
    - Metrics Covered: Apart from sensitivity and specificity, the lecture mentions other evaluation metrics like predictive values and the ROC (Receiver Operating Characteristic) curve.

**Example Illustration:**
An example scenario involving a test set with normal and disease cases is presented to illustrate the computation of accuracy and showcase how models with the same accuracy can differ in practical usefulness.

The example demonstrates that, despite having the same accuracy, a model attempting to distinguish between healthy and disease patients may be considered more useful.

## Accuracy in Terms of Conditional Probability

Accuracy is seen as the probability of the model being correct in its predictions. This probability is further broken down into two components: the probability of the model being correct when the patient has the disease and the probability of the model being correct when the patient is normal.

The law of conditional probability is then introduced, stating that the probability of both A and B is equal to the probability of A given B multiplied by the probability of B. This law is applied to expand the two components of accuracy. For instance, the probability of being correct given the patient has the disease is equivalent to the probability of predicting positive given a patient has the disease. Similarly, the probability of being correct when the patient is normal is equivalent to the probability of predicting negative given a patient is normal.

## Sensitivity, Specificity and Prevalence

- **Sensitivity:**
   - Sensitivity is defined as the probability that the model correctly classifies a patient as having the disease given that they actually have the disease.
   - It is also referred to as the true positive rate, and it is calculated as the fraction of disease examples that are correctly identified as positive.

- **Specificity:**
   - Specificity is the probability that the model correctly classifies a patient as being normal given that they are actually normal.
   - It is also known as the true negative rate and is calculated as the fraction of normal examples that are correctly identified as negative.

- **Prevalence:**
   - The prevalence is the probability of a patient having the disease in a given population.
   - It is the fraction of disease examples over the total number of examples.

The accuracy is expressed as a weighted average of sensitivity and specificity, where the prevalence acts as the weight for sensitivity, and one minus the prevalence acts as the weight for specificity.

The formula for accuracy in terms of sensitivity, specificity, and prevalence is provided, allowing for a comprehensive understanding of how these metrics are interconnected. The example calculations demonstrate how sensitivity and specificity are computed using the given data and how accuracy can be derived from these metrics, considering the prevalence of the disease in the population. This approach allows for a nuanced evaluation of diagnostic AI models by considering their performance in different aspects of disease detection and normal classification.

## PPV, NPV

- **Positive Predictive Value (PPV):**
   - PPV answers the question: Given the model predicts positive on a patient, what is the probability that the patient actually has the disease?
   - It is calculated as the fraction of positive predictions that are correctly identified as having the disease.
   - The formula for PPV is the number of true positive cases divided by the total number of positive predictions.

- **Negative Predictive Value (NPV):**
   - NPV addresses the question: Given the model predicts negative on a patient, what is the probability that the patient is actually normal?
   - It is computed as the fraction of negative predictions that are correctly identified as normal.
   - The formula for NPV is the number of true negative cases divided by the total number of negative predictions.

## Confusion Matrix

**Confusion Matrix:**
- The confusion matrix is a tabular representation that provides a comprehensive view of a classifier's performance.
- The rows of the matrix correspond to the ground truth (actual classes), and the columns represent the model predictions or outputs.
- Each cell in the matrix contains the count of elements for a specific combination of ground-truth and model prediction.
- Four key counts in the confusion matrix:
   1. True Positives (TP): Cases where the ground truth is positive, and the model predicts positive.
   2. False Positives (FP): Cases where the ground truth is negative, but the model predicts positive.
   3. False Negatives (FN): Cases where the ground truth is positive, but the model predicts negative.
   4. True Negatives (TN): Cases where the ground truth is negative, and the model predicts negative.
- The sum of all cells in the matrix equals the total number of examples.

**Metrics in Terms of Confusion Matrix:**
- Metrics like Positive Predictive Value (PPV) and Specificity can be directly derived from the confusion matrix.
- PPV, for instance, is calculated as true positives divided by the sum of true positives and false positives. This corresponds to counts in the top left cell and the entire positive prediction column in the confusion matrix.
- Specificity involves the count of true negatives divided by the sum of true negatives and false positives, corresponding to the bottom right cell and the entire normal ground-truth row in the confusion matrix.
- The confusion matrix serves as a tool to calculate various evaluation metrics, providing a clear connection between the metrics and the counts within the matrix.

## Calculating the PPV in terms of sensitivity, specificity, and prevalence

1. **PPV Equation:**
   - The PPV is denoted as P(pos∣pos^), meaning the probability of being actually positive given a positive prediction.
   - By Bayes' rule, it is expressed as:

     \[ PPV = \frac{P(pos^∣pos) \times P(pos)}{P(pos^)} \]

2. **Numerator Terms:**
   - **Sensitivity:** \( P(pos^∣pos) \) - This is the probability that the model predicts positive given that the actual condition is positive.
   - **Prevalence:** \( P(pos) \) - It represents the prevalence of the actual positive cases in the population.

3. **Denominator Term:**
   - \( P(pos^) \) - This is the sum of true positives and false positives. In other words, it is the model's positive predictions.

4. **True Positives (TruePos):**
   - TruePos is expressed in terms of sensitivity and prevalence:

     \[ TruePos = Sensitivity \times Prevalence \]

5. **False Positives (FalsePos):**
   - FalsePos is expressed in terms of specificity and the complement of prevalence (1 - prevalence):

     \[ FalsePos = (1 - Specificity) \times (1 - Prevalence) \]

6. **Substituting into PPV Equation:**
   - Substitute the expressions for TruePos and FalsePos into the PPV equation:

     \[ PPV = \frac{Sensitivity \times Prevalence}{Sensitivity \times Prevalence + (1 - Specificity) \times (1 - Prevalence)} \]

This final equation represents PPV in terms of sensitivity, specificity, and prevalence. It allows for the calculation of PPV based on the model's performance in correctly identifying positive cases, the prevalence of the condition, and the model's specificity in correctly identifying negative cases.