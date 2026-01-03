---
date: "2023-03-16T21:41:10+00:00"
title: "Wrist Actigraphy Algorithms: The Key to Understand Sleep"
---

Wrist actigraphy is a popular non-invasive and cost-effective method for monitoring sleep and physical activity patterns. With the widespread adoption of smartwatches, wrist actigraphy has become even more prevalent. Several algorithms have been developed to analyze wrist activity data and classify sleep and wake periods accurately. This post explores some of the most widely used wrist actigraphy algorithms.

## Cole–Kripke Algorithm

The **Cole–Kripke algorithm**, developed by Cole and Kripke in 1991, is one of the most widely used methods in sleep research.

The algorithm first filters wrist activity data to remove high-frequency noise. The filtered signal is analyzed to calculate activity counts for each minute. These counts are converted into a binary representation by applying a threshold: values above the threshold are classified as active, while those below are classified as inactive.

The threshold is calculated using the individual’s mean and standard deviation of activity counts. Each minute’s activity count is normalized by subtracting the mean and dividing by the standard deviation. A predefined number of standard deviations above the mean is then used as the threshold, depending on study requirements.

Once binarized, the algorithm applies heuristic rules to classify sleep and wake periods. These rules consider:

- The number of consecutive minutes of activity or inactivity
- The time of day
- The duration and continuity of sleep periods
- The proportion of sleep and wake epochs during the night
- Time spent in bed

Periods of sustained inactivity during expected sleep hours are classified as sleep.

## Sadeh Algorithm

The **Sadeh algorithm**, developed by Avi Sadeh in 1994, operates on principles similar to the Cole–Kripke algorithm. It also relies on wrist activity counts and threshold-based classification of sleep and wake periods.

A second version, commonly referred to as **Sadeh-2**, introduces refinements to improve classification accuracy, particularly in specific populations such as children and adolescents.

## Tudor-Locke Algorithm

The **Tudor-Locke algorithm**, developed by Catrine Tudor-Locke in 2002, focuses primarily on physical activity classification rather than direct sleep–wake detection.

The algorithm filters wrist activity data and computes activity counts per minute, which are then categorized into four activity intensity levels:

- **Sedentary:** Minimal movement (e.g., sitting or lying down)
- **Light:** Low-intensity movement (e.g., standing or slow walking)
- **Moderate:** Moderate activity (e.g., brisk walking or cycling)
- **Vigorous:** High-intensity movement (e.g., running or jumping)

Thresholds for these categories are derived from calibration studies that correlate wrist activity data with energy expenditure. Based on these classifications, the algorithm computes metrics such as:

- Time spent in each activity category
- Number and duration of activity bouts
- Intensity-weighted activity counts

These metrics are used to estimate overall physical activity levels and assess longitudinal changes.

## Actiware Algorithm

The **Actiware algorithm**, developed by Philippe Jean-Louis and colleagues in 1999, is widely used in clinical and research settings.

Its core methodology is similar to the Cole–Kripke and Sadeh algorithms. In addition to sleep–wake classification, Actiware incorporates **sleep stage scoring** by integrating data from additional sensors. This allows approximate estimation of sleep stages such as light sleep, deep sleep, and REM sleep.

## Bayes Actigraphy Sleep Algorithm (BASA)

The **Bayes Actigraphy Sleep Algorithm (BASA)** is a machine learning–based approach that uses Bayesian modeling to classify sleep and wake periods from wrist actigraphy data. It was developed by researchers at the University of Michigan and is used in both clinical and research contexts.

BASA begins by extracting features from raw wrist activity data, including:

- Duration and frequency of wrist movements
- Rate of change in activity
- Regularity and patterns of movement over time

These features are fed into a Bayesian model that classifies each minute as sleep or wake. Bayesian modeling allows prior knowledge and assumptions to be incorporated into the classification process, improving robustness and accuracy.

A key strength of BASA is its **personalized modeling**, which adapts classification criteria based on an individual’s typical sleep patterns. Additional rule-based constraints are applied to reduce false positives and false negatives, such as excluding isolated activity spikes during sleep periods.

## Adaptive Sleep–Wake Classifier (ASWC)

The **Adaptive Sleep–Wake Classifier (ASWC)** was developed by researchers at the University of Surrey. It is conceptually similar to BASA but employs a different modeling strategy to adaptively distinguish sleep and wake states based on individual activity patterns.

## Conclusion

Wrist actigraphy algorithms have significantly advanced our understanding of sleep and physical activity. As sensor technology and modeling techniques continue to evolve, ongoing research will further improve the accuracy and reliability of these methods. The future of wrist actigraphy holds promise for uncovering deeper insights into sleep behavior and human health.

---

## References

- <https://www.researchgate.net/publication/336875230_Performance_comparison_of_different_interpretative_algorithms_utilized_to_derive_sleep_parameters_from_wrist_actigraphy_data>
- <https://www.researchgate.net/publication/364571720_Actigraphy-Based_Sleep_Detection_Validation_with_Polysomnography_and_Comparison_of_Performance_for_Nighttime_and_Daytime_Sleep_During_Simulated_Shift_Work>
- <https://www.researchgate.net/publication/341423063_Application_of_Deep_Learning_to_Improve_Sleep_Scoring_of_Wrist_Actigraphy>
