# Different Populations and Diagnostic Technology

Understanding the challenges and opportunities associated with integrating AI algorithms, particularly classification and segmentation models for medical imaging, into routine medical practice. The question is: why these systems are not yet widely used in hospitals or clinics?

The main challenge is achieving reliable generalization of AI algorithms in clinical settings. This difficulty arises due to various factors. Using the example of a chest x-ray model developed on US data, illustrates that applying the same model to a hospital in a different country, such as India, may be problematic. The patient population in India might exhibit x-rays with differences from the training data, emphasizing the need for testing the model's ability to detect conditions prevalent in the specific population, such as tuberculosis.

Another example involves a brain tumor segmentation model, where the challenge lies in the variation of MRI technology globally and over time. The resolution of MRI scanners can differ significantly, with newer scanners offering higher resolution than older ones. Therefore, before applying a segmentation model in a new hospital, it is crucial to ensure that the model can generalize to the specific scanner resolution used at that location.

# External Validation

The focus is on evaluating the generalization of a model to a population it hasn't encountered before. This process is termed external validation and is distinguished from internal validation, where the test set is drawn from the same distribution as the model's training set.

If it's found that the model is not generalizing well to the new population, it's suggested obtaining more samples from the new population to create a small training and validation set. This allows for fine-tuning the model on this new data to improve its performance on the specific population.

The distinction between studies that use retrospective data, historically labeled data for training and testing algorithms, and the need for prospective data to assess the real-world utility of AI models. In the context of a chest x-ray model, applying the trained model to interpret x-rays as they are taken for new patients is discussed as an example of working with real-world, prospective data.

Also, there is potential differences in results between retrospective and prospective data. One reason for such variations is that retrospective data often undergoes processing and cleaning steps, whereas real-world data includes raw, unprocessed information. As an illustration, the common occurrence of taking lateral x-rays from the side of the patient in the real world, which might not be represented in the filtered dataset used for model training. Adjustments, such as filtering out lateral x-rays or tuning the model to accommodate them, may be necessary before deploying the model in real-world scenarios.

# Measuring Patient Outcomes

Challenges of deploying AI models in real-world clinical settings and the importance of metrics that reflect clinical application. While traditional evaluation methods like AUROC curves and dice scores are mentioned, the focus shifts to assessing the impact of AI models on actual patient outcomes.

Decision curve analysis as a means to quantify the net benefit of using a model to guide patient care. Another approach involves randomized control trials, where patient outcomes are compared between those subjected to AI algorithm application and those not. The setup of such trials is explored in a subsequent course.

In the real world, it is emphasized that the analysis should not only be on an overall scale but also consider subgroups based on factors like age, sex, and socioeconomic status. This approach helps identify algorithmic blind spots and unintended biases, such as skin cancer classifiers showing different performance levels on different skin tones.

Algorithmic bias is acknowledged as a critical research area, and potential biases arising from scenarios like misusing missing data in medical prognosis models.

The last challenge and opportunity are understanding how AI algorithms interact with clinicians' decision-making processes.