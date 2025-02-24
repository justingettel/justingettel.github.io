# Hospitals – An Exploratory SQL Analysis

As I sat down to analyze patient data from hospitals across the United States, I found myself reflecting on my own experiences with healthcare—those long waits, the myriad of questions upon admission, and the relief of finally getting the care I needed. This project, titled “Hospitals - An Exploratory SQL Analysis,” not only sharpened my SQL skills but also opened my eyes to the realities of the institutions we rely on throughout our lives.

### Why this project?

This project analyzes hospital patient demographic and health data to answer questions about hospital operations and patient outcomes.

It’s partially motivated by the contentious state of the healthcare system in the United States and although my analysis was limited in scope and primarily focused on developing my SQL skills, it provided meaningful insights into how hospitals function and serve diverse populations.

By reading this article, you’ll discover patterns in hospital stay durations, the performance of various medical specialties, and how race factors into treatment decisions.

### Key Takeaways

Nearly half (48%) of patients stay in the hospital for just 1-3 days, indicating a right-skewed distribution of hospital stay durations.

Surgical specialties, radiology, and cardiology perform the most procedures on average, highlighting them as both sources of healing and cost in hospitals.

There is no significant difference in lab procedures based on race, suggesting equitable treatment across demographics.

### Dataset Details

The data I examined came from Kaggle and the UC Irvine Machine Learning Repository. The database (named Patient) includes two main tables: Demographics and Health. The dataset spans ten years and includes records from 130 hospitals across the United States and can be accessed through the following links:

Kaggle: https://www.kaggle.com/code/iabhishekofficial/prediction-on-hospital-readmission/data?select=diabetic_data.csv
UC Irvine Machine Learning Repository: https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008#

### Analysis Process

One of the most surprising aspects of the process was how well SQL helped me connect different datasets. Although SQL is not a visual tool, it proved to be powerful for querying large amounts of data quickly and efficiently, which is where other data tools (i.e., Excel) fail.

### Visuals and Insights

Hospital Stay Duration Histogram

The histogram visualizes the distribution of hospital stays. As observed, about 48% of patients stay between one and three days, while 85% stay for a week or less. This suggests that many patients receive prompt care, but it also raises questions about those who stay longer—what complexities do they face? 

<img src="images/WBG Org Structure.png?raw=true"/>
