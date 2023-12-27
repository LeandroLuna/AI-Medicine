# Survival Models

In this week's lesson on survival models, the focus is on models that specifically consider the time to the occurrence of an event, such as the duration from treatment to recurrence or from diagnosis to death. These models address questions commonly posed by doctors, such as the likelihood of a patient's survival over the next five or ten years. The lesson emphasizes that survival models are an extension of previously studied prognostic models. Additionally, the session covers the utilization of survival data in constructing these models.

# Survival Function

In this lesson on survival analysis, the focus is on the survival function, a crucial tool in addressing the broader question of the probability of survival beyond a specific time (t). Previously, the discussion centered around the probability of death within a given time frame, such as five years. The model built for this purpose can also be used to compute the probability of survival past that time, simply by subtracting the probability of death from one. The extension introduced in survival models involves considering the probability of survival past any time point, not limited to specific durations like five years.

Survival models overcome the need for building separate models for different time horizons. Instead, a single model can answer questions like the probability that the time to death exceeds a certain duration (e.g., two years, five years, or ten years). The key concept is the survival function, representing the probability that the time to death is greater than a specific number of years. This function is defined for each time point (t), and the lesson emphasizes its significance in survival analysis.

# Valid Survival Functions

The lecture on "Valid Survival Functions" discusses the concept of survival models that analyze patients and produce survival functions, representing the probability that an event will occur after a certain time (e.g., 1 year, 5 years, 10 years). The survival function is graphically represented with time on the x-axis and survival probability on the y-axis. Two key properties of valid survival functions are highlighted.

Firstly, the survival probability at any time 'u' is less than or equal to the survival probability at any time 'v' if 'u' is greater than or equal to 'v.' This implies that as time progresses, the survival probability should either remain the same or decrease but should never increase. Secondly, valid survival functions typically start with a survival probability of 1 and decrease to 0 as time extends to infinity.