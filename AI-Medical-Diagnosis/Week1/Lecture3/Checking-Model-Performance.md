# Model Testing

In this lesson, we explored the testing phase of a model, particularly in the context of medical diagnosis. We discussed the importance of appropriately using training, validation, and test sets, as well as the need for a solid "ground truth" to effectively evaluate models.

When applying machine learning to a dataset, it is common to split the dataset into training and test sets. The training set is used in model development and selection, while the test set is reserved for reporting final results. Typically, the training set is further subdivided into training and validation, with the former used for model learning and the latter for hyperparameter tuning and providing an estimate of the model's performance on the test set.

We faced three challenges when constructing these sets, especially in the context of medicine. The first challenge is ensuring independence of test sets; the second is related to the sampling of these sets, and the third is associated with defining the "ground truth."

We explored the issue of patient overlap, highlighting how repeating patients in training and test sets can lead to optimistic performance on the test set due to the model accidentally memorizing training data. This phenomenon can occur when the model memorizes specific or unique patient features during training, resulting in a model evaluation that is more optimistic than its true capability.

To address these challenges, it is crucial to understand and address patient overlap and other complexities in constructing training and test sets, thus ensuring more accurate and reliable evaluations of models in the field of medicine.

# Splitting Data by Patient

In the lesson on "Splitting Data by Patient," we addressed the issue of patient overlap in datasets. To prevent the model from memorizing specific patient features and generating optimistic evaluations on the test set, a proposed approach is to ensure that a patient's X-ray exams are present in only one of the sets (training, validation, or test).

When comparing the traditional approach of random assignment of images with the patient-based division approach, we noticed that in the former, exams from the same patient could be in different sets. This is exemplified by X-rays belonging to patient 20 distributed across the training, validation, and test sets.

On the other hand, using the patient-based division, all exams belonging to a specific patient are kept in the same set. For example, all X-rays associated with patient 20 will be in the training set, while those related to patient 32 will be in the validation set, ensuring no patient overlap between sets.

This practical approach addresses the initial challenge of patient overlap, ensuring that the model cannot benefit from the accidental memorization of specific patient characteristics when evaluating its performance on independent test sets.

# Sampling

In the discussion on "Sampling," we explored the second challenge related to set sampling. When creating a test set, determining the size of this set can vary, such as being a fixed fraction of the complete set, like 10%. In artificial intelligence studies in medicine, especially when human annotation is required, the test set's size is often limited by the capacity of human readers. Typically, test sets contain hundreds of examples in medical AI studies.

The challenge arises when randomly sampling a test set, where there is a risk of not including patients with the disease of interest. In cases of small medical datasets with few examples of each disease, this can be especially problematic. A common strategy to address this challenge is to ensure that the test set contains a minimum percentage of examples from the minority class, such as 50%. This ensures sufficient representativity to evaluate the model's performance on positive cases.

After sampling the test set, it is common to sample the validation set. To ensure that the validation set's distribution reflects the test set, the same sampling strategy can be applied. Ultimately, the remaining patients will make up the training set. Given that the test and validation sets were artificially sampled to have a large proportion of positive cases, the training set will have a smaller proportion of these cases.

This approach to set sampling overcomes the challenge of ensuring that the model is trained and evaluated appropriately, even in medical datasets with significant imbalances.

# Ground Truth and Consensus Voting

In the lesson on "Ground Truth and Consensus Voting," we explored the crucial issue of determining the correct label for an example when testing a model. The commonly used term to refer to the correct label is "ground truth" in the context of machine learning or "gold standard" in the medical context.

In cases like chest X-rays, differentiating between some diseases can be complex, leading to disagreement among experts, known as interobserver disagreement, common in medical settings. The challenge here is how to establish the necessary "ground truth" to evaluate algorithms in the presence of this disagreement.

One approach to solving this problem is the consensus voting method. This methodology involves using a group of human experts to determine the "ground truth." For example, three radiologists may examine a chest X-ray and indicate whether pneumonia is present. If two out of three agree, we consider the answer as yes. In general, the answer will be the majority vote of the three radiologists. Alternatively, radiologists can discuss their interpretations until reaching a unanimous decision, which is then used as the "ground truth."

This approach provides a robust way to handle disagreements among experts, ensuring a more accurate and reliable evaluation of algorithms in challenging medical environments.

# Additional Medical Testing

In the section on "Additional Medical Testing," we explored a second method to establish "ground truth" or a gold standard when testing a model in medical contexts. This method involves conducting more definitive tests that provide additional information. For example, when determining if a patient has a mass in a chest X-ray, a more definitive test would be a computed tomography (CT) scan. The CT scan shows the three-dimensional structure of the potential abnormality, offering more information to the radiologist. If a mass is confirmed in the CT scan, this information can be attributed as "ground truth" to the chest X-ray.

In the mentioned dermatological study, the "ground truth" for the test set was determined by a biopsy of the skin lesion. In this medical procedure, a sample of the skin with the suspected cancer is removed and tested in the laboratory. The results of this test are then used to establish the "ground truth" for the image of the skin lesion.

While this method provides a more robust "ground truth," the difficulty lies in the fact that we do not always have access to these additional tests. Not everyone who undergoes a chest X-ray also undergoes a CT scan, and not everyone with a suspicious skin lesion undergoes a biopsy. Therefore, in many cases, it is necessary to resort to the first method of reaching a consensus on the "ground truth" in existing data, which is the strategy commonly used in many medical AI studies.

In this way, we addressed the three challenges related to algorithm testing and discussed solutions in the context of medicine. The lesson concludes by congratulating for the knowledge acquired in the first week and anticipating the practical application of these concepts in the next stage of the course, where ideas and methods for evaluating the constructed models will be explored.