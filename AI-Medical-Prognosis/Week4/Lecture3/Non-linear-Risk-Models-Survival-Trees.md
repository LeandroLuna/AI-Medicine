# Intro to Survival Trees

In the "Intro to Survival Trees" lesson, the instructor introduces survival trees as a method for considering patient variables to assess the risks for different patients. Survival trees are compared to binary decision trees and are highlighted for their ability to capture nonlinear relationships in patient data. The lesson revisits previous survival models that incorporated hazard functions individualized for each patient based on specific variables such as age and smoking status.

The discussion delves into the limitations of linear functions and the Cox Proportional Hazards Model. It emphasizes that linear functions cannot effectively capture scenarios where risk decreases and then increases over time, which is a drawback of the Cox Proportional Hazards Model. Additionally, the model assumes proportional hazard functions for similar patients, overlooking potential variations in risk curves.

To address these limitations, the lesson introduces the concept that survival trees aim to create hazard functions tailored to different types of people within a population. The example of chemotherapy treatment is used to illustrate situations where risk curves may vary, emphasizing the need for models that can accommodate such complexities. The ultimate goal discussed is to develop hazard functions that differ for distinct groups within a population, recognizing the dynamic nature of risk over time. The instructor notes that the focus will be on modeling the cumulative hazard function to achieve this goal.

# Survival Tree

The "Survival Tree" lecture discusses the application of decision tree methodology in the context of survival analysis. The instructor uses a graphical representation with age and blood pressure as variables to illustrate the construction of a survival tree. Each data point represents a patient, annotated with survival time (blue for events, white for censored observations).

The process involves manually classifying patients into groups based on similar survival times. A decision tree is then constructed, where each split corresponds to a rule based on variables such as age and blood pressure. For example, if age is greater than or equal to 60, the patient falls into Group C, and a cumulative hazard estimate is determined for that group. If age is less than 60, the analysis considers blood pressure, creating further splits.

The resulting decision tree structure resembles a traditional decision tree but is adapted for survival analysis. The key differences highlighted in the lecture include the focus on time-to-event models, where risk is assessed at different time points using cumulative hazard estimates. Additionally, the data involves survival times and censored observations, representing patients who have not yet experienced the event by the end of the study.

The lecture emphasizes the practical application of the survival tree in estimating risk for new patients based on their characteristics, using the tree structure to determine the appropriate cumulative hazard estimate for risk assessment.

# Nelson Aalen Estimator

In the lecture on the "Nelson-Aalen Estimator," the focus is on estimating the cumulative hazard for a given population. The speaker begins by representing data points in the form of a survival table, containing event times and censoring times for a group of patients. The table includes both censored and non-censored observations.

The Kaplan-Meier method is briefly mentioned as one way to estimate survival, but the main emphasis is on the Nelson-Aalen estimator, which is an alternative method for estimating the cumulative hazard of the population. The Nelson-Aalen estimator formula involves the sum of the ratio of the number of deaths (\(d_i\)) to the number of individuals who survived up to time \(i\) (\(n_i\)).

The speaker illustrates the application of the Nelson-Aalen estimator through an example. They consider a cumulative hazard estimate at a specific time, such as 33 months. The estimation involves summing the ratios for the relevant time points where deaths occur. The example includes three time points (5, 30, and 32 months) with non-zero numerators. The resulting computation yields an estimate of the cumulative hazard at 33 months, which is 0.75.

The lecture emphasizes that this estimation process can be applied to any time point between 0 and infinity, providing cumulative hazard estimates for various time intervals.

# Comparing Risks of Patients

The lecture on "Comparing Risks of Patients" discusses the methodology of comparing the risk profiles of two patients using survival analysis. The example involves two patients with different ages and blood pressure levels.

- **Patient Information:**
   - Patient 1: Age 50, BP 162
   - Patient 2: Age 61, BP 140

- **Utilizing Survival Tree:**
   - The survival tree is employed to categorize patients into groups based on their age and blood pressure.
   - Patient 1 (Age < 60, BP > 160) belongs to Group A.
   - Patient 2 (Age > 60) belongs to Group C.

- **Cumulative Hazard Estimation:**
   - Cumulative hazard functions for Group A and Group C are used to estimate the cumulative hazard for each patient.
   - Graphs depict the cumulative hazards for Patient 1 (blue curve) and Patient 2 (orange curve).

- **Comparing Cumulative Hazards:**
   - The comparison of cumulative hazards reveals that, at all time points, the blue patient has a higher cumulative hazard than the orange patient.
   - However, the lecture addresses the challenge when cumulative hazards cross, meaning that, for certain time points, one patient may have a higher cumulative hazard, while the other surpasses it beyond a certain point.

- **Consideration of Time Points:**
   - To determine which patient is more at risk, the specific time point of interest becomes crucial.
   - Cumulative hazards may intersect at different time intervals, and the choice of the time point for comparison is essential for accurate risk assessment.

# Mortality Score

The lecture on "Mortality Score" introduces the concept of comparing the risks of patients based on cumulative hazard functions at observed event times. The key idea is to focus on the times where events occur in the population and compare the cumulative hazards of patients at those specific times.

Using a population of patients, the speaker illustrates that comparing risks is particularly relevant in the time period where events are observed. They use the example of two patients, one represented by an orange curve and the other by a blue curve, and demonstrate that, at observed event times, the orange patient consistently has a higher risk.

To formalize this comparison, the speaker introduces the concept of a mortality score. Using a simplified population of five patients with four observed events, the cumulative hazard at specific event times is evaluated for each patient. Patients with observed event times contribute to the comparison, while those with only censoring times are excluded. The cumulative hazard values at these times are summed up for each patient, resulting in a mortality score. This score serves as a single value that facilitates the comparison of risks between two patients based on their cumulative hazard functions at the relevant event times. Ultimately, the mortality score allows for a meaningful comparison of the risks of different patients in the context of observed event times.