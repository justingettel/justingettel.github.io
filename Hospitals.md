# Hospitals – An Exploratory SQL Analysis

As I sat down to analyze patient data from hospitals across the United States, I found myself reflecting on my own experiences with healthcare—those long waits, the myriad of questions upon admission, and the relief of finally getting the care I needed. This project, titled “Hospitals - An Exploratory SQL Analysis,” not only sharpened my SQL skills but also opened my eyes to the realities of the institutions we rely on throughout our lives.

## Why this project?

This project analyzes hospital patient demographic and health data to answer questions about hospital operations and patient outcomes.

It’s partially motivated by the contentious state of the healthcare system in the United States and although my analysis was limited in scope and primarily focused on developing my SQL skills, it provided meaningful insights into how hospitals function and serve diverse populations.

By reading this article, you’ll discover patterns in hospital stay durations, the performance of various medical specialties, and how race factors into treatment decisions.

## Key Takeaways

Nearly half (48%) of patients stay in the hospital for just 1-3 days, indicating a right-skewed distribution of hospital stay durations.

Surgical specialties, radiology, and cardiology perform the most procedures on average, highlighting them as both sources of healing and cost in hospitals.

There is no significant difference in lab procedures based on race, suggesting equitable treatment across demographics.

## Dataset Details

The data I examined came from Kaggle and the UC Irvine Machine Learning Repository. The database (named Patient) includes two main tables: Demographics and Health. The dataset spans ten years and includes records from 130 hospitals across the United States and can be accessed through the following links:

Kaggle: https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/data?select=diabetic_data.csv
UC Irvine Machine Learning Repository: https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008#

## Analysis Process

One of the most surprising aspects of the process was how well SQL helped me connect different datasets. Although SQL is not a visual tool, it proved to be powerful for querying large amounts of data quickly and efficiently, which is where other data tools (i.e., Excel) fail.

## Visuals and Insights

### Hospital Stay Duration Histogram

The histogram visualizes the distribution of hospital stays. As observed, about 48% of patients stay between one and three days, while 85% stay for a week or less. This suggests that many patients receive prompt care, but it also raises questions about those who stay longer—what complexities do they face?

<img src="images/1 Hospitals Histogram.png?raw=true"/>

### Procedures by Medical Specialty

Surgical specialties, radiology, and cardiology stand out as the top performers in terms of average procedures. This insight indicates that these areas may simultaneously represent sources of healing and cost for hospitals, warranting further investigation into their efficiency and outcomes.

<img src="images/2 Hospitals Medical Specialty.png?raw=true"/>

### Lab Procedures by Race

My findings revealed little variation in the number of lab procedures across different racial demographics, suggesting that hospitals are treating patients fairly in this regard. This was a reassuring outcome and indicates strides towards equitable healthcare.

<img src="images/3 Hospitals Race.png?raw=true"/>

### Correlation of Lab Procedures and Hospital Stay

A deeper dive into the data revealed a correlation between the number of lab procedures and the length of hospital stays. This could imply that patients requiring more extensive testing tend to have more complex health issues, which require longer hospital stays.

<img src="images/4 Hospitals Correlation.png?raw=true"/>

### Patient Summary Data 

To summarize the patient data effectively, I created easily readable sentences that combined demographics, medications, and lab procedures. This succinct format allowed for quick insights at a glance, streamlining the understanding of patient profiles.

<img src="images/7 Hospitals Summary.png?raw=true"/>

## Main Takeaways

The analysis highlighted several important trends in hospital operations and patient care. While the majority of patients experience short stays, the correlation between lab procedures and longer stays suggests that hospitals must be mindful of the complexity of cases they handle. Furthermore, the equitable treatment across racial demographics is promising, but ongoing monitoring is crucial to ensure this remains the case.

I invite you to connect with me on LinkedIn! I would love to hear your thoughts or questions about my project.
