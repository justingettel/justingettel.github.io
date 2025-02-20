# Development Debt: World Bank Lending

Against the backdrop of modern-day abundance, billions of people globally still suffer from a lack of basic necessities. The World Bank Group (WBG) strives resolve this irony, with a stated mission “to end extreme poverty and boost shared prosperity on a livable planet.” That is an admirable mission, but it raises questions:

"How much money has been lent in support of that mission?”

“How has lending to recipient countries changed over time?”

“What has the money been spent on?”

Before we answer those questions, it's important to understand the WBG's organizational structure to put the analysis that follows into perspective.

### 1. WBG Organizational Structure

The WBG is a family of five international organizations, while the World Bank is considered to be a grouping of two of those organizations:

<img src="images/WBG Org Structure.png?raw=true"/>

To narrow the focus of this project, the analysis focuses exclusively on the IDA, which defines itself as “the part of the World Bank that helps the world’s lowest income countries”, and its lending relationship with India. The dataset is the IDA’s publicly available Statement of Credits, Grants and Guarantees, which can be accessed here: IDA Statement Of Credits, Grants and Guarantees - Historical Data.

### 2. About the Dataset 

A quick glance at the dataset shows there are 1,379,049 rows, 30 columns (for detailed column descriptions, click the link above), and that the CSV file available for download is 456.05 MB. The file size is too large to be analyzed exclusively in Excel, so SQL was used to carve out specific sections of the data while Excel was used to produce insights. For technical SQL queries used in the analysis, please refer to the Methodology section at the end of this article.

### 3. Key Takeaways

Insights from the analysis fall into three categories: geographic, lending, and project.

Geographically, South Asia, and more specifically, India, borrow the most money.

From a lending perspective, relative to historical levels, in recent years there have been less loans signed up between the IDA and India. Also, the basic terms of that debt, such as interest rates and years to maturity, have varied with time since the 1960s.

The money issued to India has been used for a wide variety of projects spanning all facets of the economy. In 2011, there was a particular emphasis on disaster related projects.

### 4. Detailed Analysis

### Geographic

To gauge the IDA’s lending from a global perspective, the following heat map reveals a high concentration of outstanding debt in the South Asian region, with a clear share of that belonging to India.

<img src="images/Global Debt Proportions.png?raw=true"/>

Collectively, the South Asian countries of India, Bangladesh, Pakistan, and Vietnam owe about 40% of the debt due to the IDA, with India topping the charts. Of the $25,252,817,700,963.97 in total outstanding debt, $3,792,308,509,697.59, or 15%, is owed by India. Because this represents the greatest proportion of outstanding debt, India’s relationship to the IDA became the focus of the analysis.

<img src="images/Top 5 Borrowers.png?raw=true"/>

### Lending - Loan Agreements and Sizes

<img src="images/Signed Indian Loan Agreements.png?raw=true"/>

Using Excel to count the number of times each distinct year since the 1960s shows up as the date on loan agreements, we see that the number of loan agreements signed over time by India has been steadily decreasing in recent years.

<img src="images/Cumulative Principal Amount Borrowed by Year.png?raw=true"/>

Unsurprisingly, the number of loan agreements signed in one year can be roughly correlated with the amount borrowed in one year. As more agreements are signed, more money is borrowed and we see periods in the 1980s, 1990s and 2010s when lending spiked. The most money borrowed in any single year was in 2011, totaling $556 billion. Included in that number are 162 monster loans for $1 billion each!

### Lending - Interest Rates and Loan Lengths

<img src="images/Avg. Interest Rate of Indian IDA Debt.png?raw=true"/>

The average interest rate on loans to India remained constant from the 1960s at 0.75%. Around 2011, we see the average interest rate begin to spike until 2019 when it normalized to 1.00%. In recent years (2022 – 2024), loans have been issued with more than one interest rate, indicating a distinct change in lending relative to constant, historical rates, and were excluded from the visual as they'd be displayed as '0', but aren't truly interest-free.

<img src="images/Average Loan Length.png?raw=true"/>

The average length of a loan, as measured by the difference between the year of the last principal repayment date and the first principal repayment date, comes out to 29.95 years. Let’s call it 30 years. Is it coincidental this is the length of a typical home mortgage? 

A shift in loan lengths between 1987 and 1988 indicates yet another clear change to lending policy. Average loan lengths became markedly shorter within this time frame, changing from over 30 years to under 30 years within the span of one year. Since 1988, they've only gotten shorter.

### 5. Projects

Financing to India supports projects spanning transportation infrastructure (i.e. roads, railways, etc.), agriculture, irrigation and flood control, telecommunications, power transmission, education, public health, and more, as revealed by the following word clouds (complements of ChatGPT).

<img src="images/All Projects.png?raw=true"/>

Zooming in to 2011, the $556 billion borrowed as indicated above on the Cumulative Principal chart appears to have been used primarily for flood-related disaster recovery and/or mitigation purposes.

<img src="images/2011 Projects.png?raw=true"/>

### 6. Closing Thoughts

This analysis was descriptive in nature and has revealed that trillions of dollars, issued with time-varying characteristics, have been dished out in support of global economic development since the 1960s. This analysis does not attempt to diagnose the results of that lending as good or bad, which are multifaceted and debatable and would require other data. You can read more about the World Bank’s involvement in India, including its strategy in supporting the country, here: https://www.worldbank.org/en/country/india.

This was a difficult project for me until I realized multiple data tools can be used in conjunction with one another. At first, I was trying to rely solely on SQL, which by itself is powerful for carving large quantities of data that can’t be stored and efficiently analyzed in Excel alone. However, once SQL has been used to query specific portions of the dataset, Excel becomes the most effective way to manipulate and visualize it to gain insights. My next project will place more emphasis on SQL. 

### 7. Methodology

This logic/pattern was followed for the analysis: query India-focused data from the dataset using SQL, then transport it to and analyze it in Excel. For quick reference, here’s the downloadable dataset: IDA Statement Of Credits, Grants and Guarantees - Historical Data

Step 1 – Obtain global debt proportions to decide which country to focus the analysis on:

SELECT DISTINCT("Country / Economy"), SUM("Due to IDA (US$)") AS "Due to IDA (US$)" FROM banking_data GROUP BY "Country / Economy" ORDER BY "Due to IDA (US$)" DESC;

Step 2 – Select all columns where India is a country:

SELECT * FROM banking_data WHERE "Country / Economy" = 'India';

Step 3 – Transfer step 2 data to Excel and use pivot tables and charts to generate visuals.

Step 4 – One more query to pull project names for India specifically:

SELECT YEAR("Agreement Signing Date") AS 'Agreement Signing Date Year', "Project Name" FROM banking_data WHERE "Country / Economy" = 'India';

Step 5 – Use ChatGPT to quickly produce a word cloud from the project name data sourced in the prior step.
