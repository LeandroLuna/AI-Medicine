# Decision Trees for Prognosis

In this week's class, the focus was on building the first machine learning model using decision trees. Decision trees are particularly advantageous in medical applications due to their ability to handle both continuous and categorical data, their interpretability, and fast training speed. The objective was to use decision trees to model nonlinear relationships often observed in medical data. The specific application discussed was the creation of machine learning tree-based models for predicting short-term mortality in hospital patients.

The instructor highlighted the practical challenge of dealing with missing data when training machine learning models. Various approaches to handling missing data in machine learning pipelines were explored, emphasizing the consequences of not addressing this challenge appropriately.

The latter part of the week was dedicated to discussing the interpretation of machine learning models. While machine learning models are often perceived as black boxes due to their complex inner workings, in the medical field, the ability to explain and interpret models is crucial for gaining human acceptance and trust. The class covered methods for interpreting prognostic models, providing students with tools to make their models more transparent.

# Decision Trees

In this lesson on Decision Trees, the instructor covers the topic of mortality prediction, specifically focusing on predicting the ten-year risk of death. The session begins with an overview of the process of building a decision tree at a high level and addresses the common machine learning problem of overfitting. The discussion then transitions to random forests, a powerful classifier that builds multiple decision trees to enhance predictive performance. Random forests are highlighted as a popular and effective out-of-the-box learning algorithm requiring minimal tuning.

The practical application involves building a prognostic model using age and systolic blood pressure, with systolic blood pressure defined as the pressure in blood vessels during heartbeats. The goal is to predict the ten-year mortality risk. The instructor emphasizes graphical exploration of the relationship between age, blood pressure, and death. A graph is described, with age on the x-axis and blood pressure on the y-axis. Each point on the graph represents a patient, with red indicating patients who die within ten years and blue representing patients who survive beyond ten years.

To illustrate the concept of a linear model for classification, the instructor prompts the audience to consider how a linear model would separate patients who die from those who survive based on age and blood pressure. The overall focus is on understanding decision trees, addressing overfitting issues, and introducing the concept of random forests for improved predictive performance in mortality prediction.

# Dividing the Input Space

In this lecture, the discussion revolves around the comparison of linear models and decision trees for classifying patients into high-risk and low-risk categories based on certain features. The linear model is depicted as fitting a line to separate high-risk (red background) and low-risk (blue background) patients. However, it is noted that this may lead to misclassification.

The focus then shifts to decision trees, which divide the input space using vertical and horizontal boundaries to create regions of high-risk and low-risk. Decision trees are presented as classifiers that ask a series of questions, classifying patients based on their answers. An example is given, illustrating how three patients are classified based on age and blood pressure criteria.

The advantage of decision trees is highlighted in their ability to capture nonlinear associations in the data, unlike linear models that can only draw straight lines through the feature space. Decision tree boundaries are discussed as always being vertical or horizontal, allowing for easy identification of decision tree-constructed boundaries in the input space.

In the concluding part, the lecture involves a practical exercise where the audience is asked to determine which among provided boundaries could be generated by a decision tree. The correct choice is identified based on the observation that decision tree boundaries are always vertical or horizontal.

# Building a Decision Tree

In the "Building a Decision Tree" lecture, the process of constructing a decision tree is explained. The speaker discusses the algorithm used to learn decision trees and provides a high-level overview of the steps involved. The first step is to select a variable and a corresponding value that partitions the data into two groups, one predominantly red and the other predominantly blue. The choice of variable and value depends on how effectively they separate the red and blue points. The example uses the variable "age" and a partition at the age of 60.

The process is repeated within each partition, selecting variables and values to further separate the data. The goal is to continue until the partitions are mostly red or blue. The speaker demonstrates this by adding a horizontal line based on systolic blood pressure.

The risk estimate is the fraction of patients who are deceased within each partition. The output is binarized to indicate whether an area is low or high risk. A simple approach is to predict high risk if the estimated probability is greater than 50%, and low risk otherwise. The lecture concludes by highlighting the red partitions with risk greater than 50% and the blue partition with risk less than 50%.

# How to Fix Overfitting

The lecture on "How to Fix Overfitting" discusses the challenge of overfitting in decision tree models. Overfitting occurs when the tree becomes overly complex and fits the training data too closely, resulting in poor performance on new or test data. The speaker demonstrates that controlling the maximum depth of the decision tree can help combat overfitting. For example, setting a maximum depth of 4 produces a simpler tree with balanced training and test accuracies.

Another approach to address overfitting is building a random forest, which consists of multiple decision trees. Random forests use a random sample of patients and modify the splitting procedure with a subset of features to construct each tree. The ensemble learning method of random forests improves predictive performance over single decision trees. The lecture also mentions other ensemble learning algorithms like Gradient Boosting, XGBoost, and LightGBM, which achieve high performance, especially in structured data applications in medicine and other domains.