# Survival Data

In this lesson on survival data, the instructor discusses the challenge of handling missing data, particularly sensor data, in healthcare data analysis. The focus is on instances where variables (X's) have missing values, with an example involving blood pressure measurements denoted by "NA." The instructor walks through a machine-learning pipeline, starting with a train-test split, and highlights a common practice of excluding records with missing data.

The instructor emphasizes a problem with this approach, explaining that excluding incomplete rows can lead to biased models. To illustrate this point, the instructor uses a case study where a random forest classifier is trained on data with missing blood pressure measurements. The classifier achieves high train and test accuracy. However, when applied to a new test set without missing data, the accuracy drops significantly. This discrepancy raises questions about the model's generalizability and highlights the importance of addressing missing data in a more robust way to avoid biased predictions.

# Different Distributions

The lecture on "Different Distributions" discussed the analysis of a pipeline involving a dataset with missing values. The speaker explained that they performed a train-test split, and both the training and test data had missing values, which were addressed by removing cases with missing data. A prognostic model was then built to predict death using age and blood pressure.

The speaker observed high accuracy on both the training and test datasets. However, when the model was applied to a new test dataset without missing values, it showed low performance. The discrepancy between the datasets' performance was attributed to differences in their distributions.

To investigate, the speaker focused on the distribution of the input variable "age." They compared the age distribution of the original test set (with high accuracy) and the new test set (with low accuracy). The analysis revealed a notable difference in the number of patients below the age of 40, with fewer examples in the old test set.

The speaker then questioned whether the low performance on the new test set, especially for patients under 40, was due to the lack of sufficient examples in that age range. They evaluated the model separately for patients under 40 and those above 40, finding a significantly lower accuracy for younger patients, which was influenced by the limited number of examples in that age group.

# Missing Data Example

The content of the "Missing Data Example" class is about identifying and addressing issues related to missing data in a dataset. The instructor discusses a problem where the performance of a model is poor for patients under 40. The issue is traced back to an old test set that lacked patients under 40 due to the removal of cases with incomplete blood pressure measurements. The instructor suggests graphing the distribution of the old test set before and after dropping incomplete cases to visualize the impact on young patients.

The graph reveals that many young patients were eliminated during the removal of cases with missing blood pressure measurements. The instructor explains that this systematic missingness in the data may arise from the clinic's practice of irregularly recording blood pressure for young patients. Such patterns can introduce bias in models, and the lesson emphasizes the importance of understanding missing data mechanisms.

In the latter part of the class, a quiz is presented, focusing on the appropriateness of complete-case analysis. The instructor explains that complete-case analysis may be inappropriate for groups associated with missing data. Using the example of non-smoking women not on blood pressure treatment, the instructor illustrates how this group would likely have the most missing data, making a model built with complete-case analysis unsuitable for this patient subgroup. The class concludes with a preview of future lessons on missing data mechanisms and a more systematic approach to handling missing data.

# Missing Completely at Random

The lecture discusses the concept of "Missing Completely at Random" (MCAR) in the context of missing data analysis. The instructor begins by explaining that to determine if a complete case analysis introduces bias, it is crucial to understand the reasons behind missing data. There are three broad categories of missing data: missing completely at random, missing at random, and missing not at random.

The focus is then on missing completely at random, illustrated through an example involving a physician deciding whether to record blood pressure measurements by flipping a coin for each patient. If the coin lands heads, the blood pressure is recorded; if tails, it is not. The probability of missing data in this scenario is constant (0.5), making it completely at random.

The lecture emphasizes that in MCAR situations, the probability of missing data is not dependent on any factors, such as a patient's age. The example suggests that the distributions of age groups for patients with and without missing blood pressure data should be similar since the decision to record or not is unrelated to age.

The instructor contrasts MCAR with other types of missing data, noting that most missingness is not completely at random. Despite this, the key takeaway is that in cases of missing completely at random, a complete case analysis, where only cases with complete data are considered, does not lead to biased models. The expectation is that bias is not introduced when dealing with missing completely at random data, though it is acknowledged that such cases are relatively rare compared to other types of missingness.

# Missing at Random

In the discussed lesson on "Missing at Random," the scenario involves doctors measuring blood pressure based on the age of patients. If the age is greater than 40, blood pressure is always measured. However, for patients under 40, a coin flip determines whether blood pressure is recorded or not. This introduces a condition that influences the coin flip and, consequently, the recording of blood pressure.

The simulation illustrates that for patients older than 40, blood pressure is always recorded, while for those under 40, it depends on a coin flip. The frequency distribution of age differs between patients with missing and non-missing blood pressure values. Specifically, for those under 40, there's a 50% chance of missing blood pressure, while for those over 40, it's always recorded.

The key point is that the probability of missing a blood pressure measurement is not constant; it depends on age. The concept of "missing at random" is explained as missingness being determined solely by available information, in this case, age. This is in contrast to scenarios where additional factors beyond available information influence whether something is missing.

# Missing Not at Random

The lecture discusses the concept of "Missing Not at Random" (MNAR) in the context of data analysis. In a missing not at random scenario, the missingness of data is dependent on unobservable variables. The example used involves a doctor recording blood pressure based on whether other patients are waiting. If no other patients are waiting, blood pressure is recorded for everyone. However, if other patients are waiting, a coin is flipped, and if it lands on heads, blood pressure is recorded; otherwise, it is not.

The crucial point is that the information about whether other patients are waiting is not traditionally collected as part of the study, making it an unobservable variable. The missingness of data is not constant, as it depends on this unavailable information. The probability of blood pressure data being missing is 0.5 when other patients are waiting and 0 when no other patients are waiting.

The challenge with MNAR is that the unobservable variables influencing missingness are not part of the final dataset. When comparing the distribution of variables like age between cases with missing and non-missing blood pressure values, they may appear similar, making it challenging to distinguish MNAR from missing completely at random. Understanding these different missing data categories is crucial, as dropping missing records without consideration can lead to biased models.