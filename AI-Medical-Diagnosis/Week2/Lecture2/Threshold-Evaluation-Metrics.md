# ROC Curve and Threshold

- **ROC (Receiver Operating Characteristic) Curve:**
   - The ROC curve is a valuable tool for evaluating medical models.
   - It visually plots the sensitivity of a model against its specificity at various decision thresholds.
   - Sensitivity represents the true positive rate, and specificity represents the true negative rate.

- **Decision Thresholds:**
   - A chest x-ray classification model outputs a probability of disease based on an x-ray.
   - This probability is transformed into a diagnosis using a decision threshold or operating point.
   - When the probability is above the threshold, the patient is classified as positive (having the disease), and when it's below the threshold, the patient is classified as negative (not having the disease).

- **Impact of Thresholds on Metrics:**
   - The choice of threshold significantly influences the evaluation metrics discussed earlier (sensitivity, specificity, etc.).
   - For instance, setting a threshold of 0 would classify everything as positive, resulting in sensitivity being 1 and specificity being 0.
   - Conversely, setting a threshold of 1 would classify everything as negative, making specificity 1 and sensitivity 0.

- **Understanding Operating Points:**
   - The choice of threshold, also referred to as the operating point, affects the trade-off between sensitivity and specificity.
   - Different thresholds lead to different points on the ROC curve, reflecting the model's performance under varying levels of sensitivity and specificity.

# Varying the Threshold

1. **Test Set and Output Scores:**
   - A test set of 15 chest x-rays is used, and the model produces output probabilities or scores for each x-ray.
   - These scores are plotted on a number line between zero and one.

2. **Threshold and Classification:**
   - A threshold (small t) is chosen to classify x-rays.
   - Everything to the right of the threshold is classified as positive (disease), and everything to the left is classified as negative (normal).

3. **Computing Sensitivity and Specificity:**
   - Sensitivity and specificity are computed based on the chosen threshold.
   - Sensitivity is the fraction of correctly identified disease cases among all actual disease cases.
     - Numerator: Disease cases on the right side of the threshold.
     - Denominator: Total number of disease cases.
   - Specificity is the fraction of correctly identified normal cases among all actual normal cases.
     - Numerator: Normal cases on the left side of the threshold.
     - Denominator: Total number of normal cases.

4. **Effect of Changing Threshold:**
   - Changing the threshold affects the sensitivity and specificity.
   - Increasing the threshold may decrease sensitivity and increase specificity.
   - Decreasing the threshold may increase sensitivity and decrease specificity.

5. **Extreme Threshold:**
   - Setting the threshold to one means classifying everything as negative.
     - Sensitivity is zero (no positive cases are identified).
     - Specificity is one (all cases are classified as negative).