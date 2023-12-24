# Evaluating Prognostic Models

In the "Evaluating Prognostic Models" lesson, the instructor walks through the process of evaluating prognostic models, emphasizing the fundamental concept of comparing risk scores assigned to pairs of individuals. The key points from the lesson are as follows:

- **Basic Idea of Evaluation:**
   - The primary goal of evaluating a prognostic model is to assess how well it performs on pairs of patients. The instructor uses a simple analogy with two apples, one already stale and the other fresh, to illustrate the desired outcome. The ideal scenario is for the model to assign a higher risk score to the apple that will expire sooner.

- **Comparing Risk Scores:**
   - In the context of human patients, the evaluation involves comparing risk scores assigned by the model to pairs of individuals. The example focuses on the event of death within ten years. The objective is to determine whether a patient experienced the event or not.

- **Definition of a Good Prognostic Model:**
   - A good prognostic model, in the context of the example, is one that assigns a higher risk score to an individual who experienced the event (e.g., death within ten years) compared to an individual who did not. The absolute values of the risk scores do not necessarily need to fall within a specific range; the key is the relative ranking of risk scores for pairs of individuals.

- **Risk Scores Need Not Be Probabilities:**
   - The lesson clarifies that risk scores assigned by the model do not have to be constrained between 0 and 1, nor do they have to represent probabilities. The critical criterion is that the model appropriately ranks individuals based on their risk of experiencing the specified event.

# Concordant Pairs, Risk Ties, Permissible Pairs

In the "Concordant Pairs, Risk Ties, Permissible Pairs" lesson, the instructor provides a framework for evaluating prognostic models based on the concepts of concordant pairs, not concordant pairs, and ties. The key points from the lesson are as follows:

- **Concordant Pairs:**
   - A pair of patients is termed concordant when the patient with the worst outcome has the higher risk score. This indicates that the model is correctly predicting the higher risk for the patient experiencing the adverse event.

- **Not Concordant Pairs:**
   - If the patient with the worst outcome does not have the higher risk score in the pair, it is labeled as not concordant. This suggests a discrepancy between the model's predictions and the actual outcomes.

- **Determining Concordance:**
   - The lesson provides examples to illustrate the determination of concordance. If the patient with the worst outcome (e.g., death within 10 years) has the higher risk score, the pair is concordant. Conversely, if the patient with the worst outcome has a lower risk score, the pair is not concordant.

- **Risk Ties:**
   - When two patients have different outcomes but share the same risk score, the pair is classified as a risk tie. Ties are neither considered concordant nor discordant.

- **Permissible Pairs:**
   - In the evaluation of prognostic models, only pairs with different outcomes are considered. These pairs are termed permissible pairs, and they are used to assess the model's performance.

- **Scoring System:**
   - A scoring system is introduced for evaluating prognostic models. A score of +1 is assigned for every permissible pair that is concordant, indicating correct prediction. A score of +0.5 is assigned for a permissible pair that is a risk tie, acknowledging partial correctness. Ties are given half the weight of concordant pairs in the evaluation process.

# C-Index

In the "C-Index" lesson, the instructor introduces the concept of the C-index as a metric for evaluating prognostic models. The key points from the lesson are as follows:

- **C-Index Formula:**
   - The C-index is computed using a formula that involves the number of concordant pairs, 0.5 times the number of risk ties, and dividing by the total number of permissible pairs.
   - `C-index = (number of concordant pairs + 0.5 * number of risk ties) / total number of permissible pairs`

- **Interpretation of C-Index:**
   - The C-index provides a measure of how well a prognostic model performs in correctly ranking pairs of patients based on their risk scores. It is interpreted as the probability that, given two random patients with different outcomes, the model correctly assigns a higher risk score to the patient with the worse outcome.

- **Random Model vs. Perfect Model:**
   - A completely random model would guess correctly half the time, resulting in a C-index of 0.5. A perfect model, on the other hand, would guess correctly every time, yielding a C-index of 1.

- **Example Calculation:**
   - The instructor walks through an example with five patients, listing all possible pairs and determining permissible pairs with different outcomes. Concordant pairs and risk ties are identified within the permissible pairs. The C-index is then calculated using the provided formula.

- **Calculation Steps:**
   - The steps involve identifying concordant pairs (where the patient with the worse outcome has the higher risk score), risk ties (where patients have different outcomes but the same risk score), and calculating the C-index using the formula.

- **Example Result:**
   - In the given example, the C-index is computed as 0.75, indicating the model's performance in correctly ranking pairs of patients.