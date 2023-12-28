# Evaluation of Survival Model

In this lesson on the evaluation of survival models, the focus is on Harrell's concordance index as a tool to assess the performance of such models. The instructor explains that Harrell's C-index is a modification of the regular concordance index tailored for survival data. The goal is to evaluate the survival models that have been introduced.

The lesson begins by revisiting the concept of evaluating prognostic models, which assess how well a model predicts a certain outcome. The familiar approach involves risk scores and pairwise comparisons, which is captured by the C-index. However, survival models introduce two key differences:

- **Time to Event as Ground Truth:**
   - In survival models, the target variable is the time to an event (denoted as \(T\)).
   - The focus is on modeling when an event occurs, such as a patient experiencing an event after a specific time, like 30 months.

- **Censored Observations:**
   - Survival models deal with censored observations, where the exact time of an event is unknown.
   - Evaluation needs to account for handling these censored observations.

The instructor then delves into the concept of concordance in the context of time-to-event problems. A "concordant pair" is defined as a scenario where the patient with a worse outcome (experiencing the event earlier) should have a higher risk score. However, when the time to an event is the same for two patients, an ideal risk score would indicate equal risk for both, making it another case of concordance.

The lecture distinguishes between concordant pairs, not concordant pairs (where a patient with a longer survival time has a lower risk score), and risk ties (instances of the same risk score for patients with different time-to-event outcomes). The concept of risk ties is explored in scenarios where time to events is different, but risk scores are either the same or different.

Ultimately, the instructor emphasizes the need to consider these nuances in the evaluation of survival models, particularly when dealing with time-to-event data and censored observations.

# Permissible and Non-Permissible Pairs

The lecture on "Permissible and Non-Permissible Pairs" discusses the concept of permissible pairs in the context of survival data. In binary outcomes, a permissible pair was defined as having different outcomes (one gets a zero, the other gets a one). The concept is extended to survival data, and the key point is that pairs with the same time to an event are considered permissible in this context.

The lecturer provides an example where two patients experience an event at the same time, and unlike binary outcomes, this is considered a permissible pair in survival data analysis. The discussion then moves to censored observations. When one patient is censored after a certain time (40 plus), it is still possible to compare outcomes because the censored patient's event time is known to be later than the other patient. However, if the censored patient's event time is earlier (censored at 20 plus), making a comparison becomes impossible because the actual survival time is uncertain.

# Possible Permissible Pairs

The lecture on "Possible Permissible Pairs" discusses the concept of permissible pairs in the context of survival analysis. Permissible pairs are pairs of patients where both individuals experience an event, and the length of the line represents the event time. The speaker illustrates that permissible pairs allow for meaningful comparisons, such as identifying which patient had the worst outcome or determining if both patients had events at the same time.

The lecture distinguishes permissible pairs from non-permissible pairs. In non-permissible pairs, comparisons cannot be made due to factors like censoring. For instance, if one patient's observation is censored before the other experiences an event, or if both have equivalent censored times, meaningful comparisons cannot be drawn.

The Harrell's C-Index is introduced as a metric for evaluating survival models. For every permissible pair that is concordant (indicating the model correctly predicts the order of survival times), a score of plus one is assigned. A score of 0.5 is given for a permissible pair that is a risk tie (both patients have events at the same time). The formula for the C-Index remains the same, but the definition of concordant pairs, risk ties, and permissible pairs is adjusted for survival data.

# Example of Harrell's C-Index

In the lecture on "Example of Harrell's C-Index," the speaker discusses the computation of Harrell's C-Index for a risk model using a set of patients. The risk scores are derived from either a Cox Proportional-Hazards Model or survival trees. The objective is to evaluate the model's performance on the given data. The steps involved in this evaluation are outlined:

- **Identification of Permissible Pairs:**
   - The speaker emphasizes the importance of permissible pairs in the population.
   - For each pair (denoted as A, B, C, D, and E), the speaker determines whether it is permissible or not based on the relationship between censoring and event times.

- **Permissible Pairs Evaluation:**
   - For pair A, B, the censoring occurs before the event time, making it impermissible.
   - For pair A, C, the event time occurs before censoring, making it a permissible pair.
   - For pair A, D, both times are censored, making it impermissible.
   - For pair A, E, an event occurs before an observation is censored, making it a permissible pair.
   - Similar evaluations are made for pairs B, C, B, D, B, E, C, D, C, E, and D, E.

- **Outcome Comparison:**
   - The speaker explains that the comparison is made based on event and censoring times, without considering the risk column at this stage.
   - The example illustrates cases where events occur, are censored, or the censoring happens before the event, influencing the permissibility of pairs.

- **Final Count:**
   - The speaker concludes that there are six permissible pairs based on the outlined evaluations.

# Example of Concordant Pairs

The lecture on "Example of Concordant Pairs" discusses the calculation of concordant pairs and the C-index using a set of risk scores and survival outcomes. The focus is on identifying concordant pairs, which are pairs where the patient with the worse outcome also has the higher risk score.

The analysis considers permissible pairs, emphasizing that only these pairs are comparable. The speaker evaluates several pairs:

1. **A, C:** Risk scores are 0.65 and 0.7, and the worse outcome is for patient C. A, C is concordant.

2. **A, E:** Patient E has the worse outcome and a higher risk score. A, E is concordant.

3. **B, C:** Both have events, but B has a higher risk score and longer survival time, making it a non-concordant pair.

4. **B, E:** B has a higher risk score, but the longer survival time makes it a non-concordant pair.

5. **C, D:** The worse outcome is for patient C, and C has the higher risk. C, D is concordant.

6. **C, E:** The worse outcome is for patient C, but the higher risk is for E, making it a non-concordant pair.

The analysis reveals three concordant pairs. The C-index formula is then applied, considering concordant pairs and risk ties. Since there are no ties, the C-index is calculated as 3 (concordant pairs) divided by 6 (permissible pairs), resulting in a C-index of 0.5.