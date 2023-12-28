# Hazard Functions

In the upcoming lesson on "Hazard Functions," the focus will be on strategies for constructing and evaluating survival prediction models to compare the risks of individual patients. Two models, the Cox proportional hazards model and survival trees, will be covered. Additionally, the lesson will introduce Harrell's C-index for assessing the prediction performance of the built survival models. This week's content will integrate previously learned concepts. Specifically, the lesson will delve into two tools associated with the survival function: the hazard function and the cumulative hazard function. The instructor emphasizes that these functions are interconnected and can provide insights into various aspects of survival analysis.

# Hazard

In the lecture on "Hazard," the focus is on understanding and representing the concept of hazard in survival analysis. Unlike previous discussions on survival models, which dealt with the probability of survival past a certain time \(t\), the speaker now introduces the notion of a patient's immediate risk of death if they reach a specific time \(t\).

The hazard, denoted by the Greek letter small lambda (\(\lambda\)), is defined as the probability that the time to an event is at \(t\), given that it is at or after \(t\). The hazard represents the immediate risk of death for a patient at time \(t\). Graphically, the hazard function can be plotted with time (\(t\)) on the x-axis and the hazard (\(\lambda t\)) on the y-axis. The shape of the hazard function reveals the patient's instantaneous risk of death over time.

The speaker introduces the concept of a "bathtub curve," where the risk of death is high immediately at time zero, decreases rapidly, and then may increase again over time. This pattern may be observed in certain medical treatments, such as surgery, where the risk of complications is initially high but decreases over time, only to potentially rise again later in the treatment process.

# Survival to Hazard

The lecture on "Survival to Hazard" explores the relationship between the survival function and the hazard function. The speaker introduces the concept that there is a formula linking the hazard function to the survival function, although the details of the formula are not extensively discussed. The key takeaway is that this formula allows for the derivation of the survival curve from the hazard curve and vice versa.

The survival curve is depicted as a tool for easily determining the probability of survival beyond a specific time (\(t\)). For instance, the speaker illustrates how one can read off the graph to find the probability of survival past time 4. Additionally, the survival curve enables the assessment of the immediate risk of death at a given time (\(t\)) by examining the corresponding hazard value.

The relationship between the survival and hazard functions is bidirectional, meaning one can derive the hazard from the survival curve. The hazard is described as the rate of death at age \(t\), and the speaker mentions that a constant hazard function implies a constant immediate risk of death given survival to any time \(t\).

While the specific formula for the relationship between survival and hazard is not delved into, the lecture emphasizes the practical utility of these functions in understanding the probability of survival and the immediate risk of death in a given population over time.

# Cumulative Hazard

The lecture on "Cumulative Hazard" delves into the concept of accumulated risk or hazard up to a specific time point (\(t\)). The speaker introduces the Greek letter capital lambda (\(\Lambda\)) to represent the patient's accumulated hazard. This accumulated hazard is closely related to the hazard at a specific time (\(\lambda\)), and the relationship is expressed as \(\Lambda(t) = \sum_{i=0}^{t} \lambda(i)\) for discrete time values.

For continuous time values, the cumulative hazard is represented as the integral from 0 to \(t\) of \(\lambda(i) \,di\). The lecture emphasizes that the cumulative hazard can be seen as the sum of hazards over time, providing a measure of the patient's accumulated risk.

The cumulative hazard is illustrated graphically, showing its relationship with the hazard curve. The speaker notes that the cumulative hazard curve can be derived from the hazard curve using specific formulas, and both curves are essential in understanding the instantaneous risk and accumulated risk over time.