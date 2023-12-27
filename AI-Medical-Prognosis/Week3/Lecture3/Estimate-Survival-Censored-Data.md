# Estimating the Survival Function

In this lesson, the focus is on estimating the survival function. The survival models discussed involve patients, and the survival function, denoted as S(t), represents the probability of survival at a given point in time, visually represented on a graph. The survival probability is essentially the likelihood that the time to an event occurs after a specified duration, such as one year, five years, or ten years. Survival data is examined, consisting of patient outcomes with recorded event times. Some observations include events, while others are right-censored data, indicating instances where the event was not observed. The goal is to use this information to estimate a general survival function for the entire population. At this stage, the emphasis is not on creating individualized survival functions for each patient, but rather on applying a single survival curve to the entire population, determining the probability of survival for any given time t.

# Died Immediately, or Never Die

The lecture titled "Died Immediately, or Never Die" explores the estimation of the probability of survival to a specific time point, denoted as \(t\) months. The focus is on a fixed time point, \(t = 25\) months, and the probability of survival to this duration (\(s\) at 25 months). The speaker explains that this probability is determined by the number of individuals who survive to 25 months relative to the total number of patients in the dataset.

However, the estimation becomes complex due to right-censored observations, where the exact time of an event is unknown, creating a lower bound on the time to the event. Two assumptions are considered to handle right-censored observations:

- **Immediate Death Assumption:**
   - Assumes that individuals who are censored die immediately after the last contact.
   - In this case, the estimate of survival probability to 25 months is calculated based on the known survival times (patients 3 and 6) divided by the total number of patients.
   - The resulting estimate is approximately 0.29.

- **Never Die Assumption:**
   - Assumes that individuals who are censored never experience the event and live indefinitely beyond 25 months.
   - In this scenario, additional patients (2, 5, and 7) contribute to the estimate of survival probability, resulting in a larger value.
   - The updated estimate is approximately 0.71.

The speaker emphasizes that the actual survival probability lies between these two extreme assumptions. The analysis highlights the impact of different assumptions about right-censored observations on the estimation of survival probabilities.

# Somewhere in-between

The lecture titled "Somewhere in-between" explores the challenge of estimating the probability of survival beyond a specified time point (in this case, 25 months) when faced with right-censored observations. The speaker introduces a hypothetical scenario where they can obtain the real values for censored observations by making calls to patients.

Upon acquiring the actual survival information, it is revealed that two patients survived beyond 25 months, one did not, and one had an event before 25 months. This new information leads to a refined estimate of survival at 25 months, taking into account patients 2, 3, 5, and 6. The speaker emphasizes that this estimate falls between the previously discussed extreme assumptions: two out of three censored patients survived beyond 25 months, while one did not.

The lecturer acknowledges that obtaining the real event times for censored observations is not always feasible. Therefore, the central question is raised: How can one estimate the probability of survival beyond a specific time point, such as 25 months, when faced with censored observations without direct access to the real event times? This question sets the stage for the subsequent exploration of survival models in the lecture.    

# Using Censored Data

The lecture on "Using Censored Data" focuses on estimating the probability of survival beyond 25 months while considering censored observations. The speaker introduces a number line representing discrete time points from zero to 25 and beyond, emphasizing that events occur at specific intervals.

The probability of survival past 25 months, denoted as \(S\) at 25, is defined as the likelihood that the time to an event occurs after 25 months. To express this probability, the speaker modifies it to consider events happening after or at 26 months, allowing for a more convenient representation.

The expansion of the probability involves breaking down the possibility of the time to an event occurring after or at 26 months. This breakdown is articulated as the event happening after 26, after 25, after 24, and so forth, all the way to right after or at zero. The speaker explains the logical implication of these conditions and emphasizes the significance of this formulation in understanding and estimating survival probabilities in the context of censored data.

# Chain Rule of Conditional Probability

In the lecture on the "Chain Rule of Conditional Probability," the focus is on expressing the survival probability \(S(25)\) in terms of conditional probabilities. The speaker begins with \(S(25)\) representing the probability that the survival time (\(T\)) is greater than or equal to 26, 25, and so on, down to zero.

The chain rule of conditional probability is introduced as a tool to further break down the expression. It states that the probability of two events occurring is the product of the probability of one event given the other and the probability of the other event. This rule is extended to multiple events, leading to a formula involving conditional probabilities.

Applying the chain rule to the survival probability expression, the speaker breaks it down into a series of conditional probabilities. For example, \(P(T \geq 26 \mid T \geq 25)\) is one of the terms. The process continues until reaching \(P(T \geq 1 \mid T \geq 0)\), and the final term involves \(P(T \geq 0)\).

Emphasizing that all events occur at or after zero, the speaker notes that the term \(P(T \geq 0)\) is equal to one, and therefore, it doesn't need to be explicitly included in the multiplication.

# Deriving Survival

The lecture titled "Deriving Survival" delves into representing survival probability through a series of conditional probabilities. The initial expression defines the probability of surviving to a specific time, say 25 months, as a product of probabilities. These probabilities represent the chance of surviving from one time point to the next, starting from time 0 up to the desired time.

To further break down the expression, the speaker introduces the probability that the event occurs after time \(t\), denoted as \(T \geq t\). This probability is equated to the probability that the event occurs after \(t-1\) and is given by \(1 -\) the probability that the event happens exactly at time \(t\), considering it occurred at or after \(t\). This concept is applied iteratively, extending the expression for survival probability.

The modified expression for survival probability at time 25 months (\(S(25)\)) is presented as a series of terms, each involving the complement of the probability of an event occurring at a specific time given that it occurred at or after that time. This representation is considered useful for understanding and deriving survival probabilities along a timeline.

# Calculating Probabilities from the Data

In the lecture on "Calculating Probabilities from the Data," the speaker discusses how to represent the survival function using an expression that allows for direct estimation from data. The probability that the time to an event is at a given time is calculated by considering the number of patients who died at that time in the numerator and the number of patients known to survive to that time in the denominator.

Using the example of \(t = 25\) months, the speaker illustrates the estimation process. Since no patients died exactly at 25 months, the numerator is 0. Patient three and patient six are known to survive to 25 months, resulting in a denominator of 2. This leads to an expression of \(1 - 0\), simplifying to 1, indicating that there were no deaths at 25 months.

The speaker generalizes the process for other times and emphasizes that most times will result in a numerator of 0, except for instances when patients died before the specified time. The expression is then further simplified for times when deaths occurred before the given time.

In a specific example with times \(t = 20\) and \(t = 10\), the speaker demonstrates the calculation. Patient four died at 20 months (numerator is 1), and patients three, four, and six are known to survive to 20 months (denominator is 3). Similarly, at time 10, one patient died (numerator is 1), and there are six patients known to have survived to 10 months (denominator is 6).

The final computation involves evaluating the expression, resulting in a probability of 0.56, or 56%. The lecture highlights the practical application of the survival function expression and its estimation using real data.

# Comparing Estimates

The lecture on "Comparing Estimates" introduces a new estimate of survival probability at time 25, which is calculated to be 0.56. The speaker then compares this new estimate to two previously discussed extreme assumptions regarding right-censored observations:

- **Immediate Death Assumption:**
   - Survival probability estimate was 0.29 when assuming all censored patients died immediately.

- **Never Die Assumption:**
   - Survival probability estimate was 0.71 when assuming all censored patients lived indefinitely beyond 25 months.

The speaker emphasizes the significance of the new estimate, noting that it is much closer to a hypothetical real estimate obtained by having access to actual event times in the data. The comparison highlights the impact of considering censored observations in survival probability estimation, demonstrating that the new estimate is a more realistic approximation.

The lecture then transitions to discussing the generalization of survival probability estimation beyond 25 months (\(t\)). The expression for survival probability at any time \(t\) is presented as a product notation involving the probability that the time to an event is greater than \(i\) given it is at or after \(i\). The speaker explains how to estimate this quantity from data, using the number of patients who died at time \(i\) divided by the number known to survive up to \(i\). The final expression for the survival function is given as the product from \(i = 0\) to \(t\) of \(1 - \frac{d_i}{n_i}\), where \(d_i\) represents the shorthand notation for the numerator and \(n_i\) for the denominator.

# Kaplan Meier Estimate

The "Kaplan-Meier Estimate" lecture discusses the methodology of estimating survival functions from population survival data. The Kaplan-Meier model allows the creation of survival curves applicable to an entire population rather than specific individuals. The speaker explains that survival curves can be computed for different populations, enabling comparisons.

For instance, the lecture mentions the example of comparing the prognosis for patients with stage 3 and stage 4 cancer. The Kaplan-Meier estimate produces survival curves for each stage, represented on a plot for visual comparison. The y-values on the curves provide survival probabilities at specific times, allowing clinicians to assess differences in survival probabilities between populations.

The lecture emphasizes the significance of the Kaplan-Meier estimator in addressing right-censoring, a form of missing data in survival analysis where the time to an event is not observed due to study termination or patients leaving before experiencing an event. The Kaplan-Meier estimator considers censored observations to estimate a survival function for the entire population.