# cyclistic-casual-rider-conversion-analysis
Analyzing Cyclistic bike-share data to understand rider behavior and drive casual rider to annual member conversion.

## 1. Project Overview 

This case study, part of the Google Data Analytics Professional Certificate, focuses on **Cyclistic**, a fictional bike-share company in Chicago. The core business problem is to **maximize the number of annual memberships** by understanding how casual riders and annual members use Cyclistic bikes differently.

My analysis aims to:
* Identify key distinctions in ride patterns, duration, and station usage between casual riders and annual members.
* Uncover actionable insights that can inform a new marketing strategy.
* Propose data-backed recommendations to convert casual riders into annual members, thereby contributing to Cyclistic's long-term success and revenue growth.
  
## 2. Business Problem

Cyclistic's director of marketing, Lily Moreno, believes the company's future success hinges on converting casual riders into annual members. While casual riders generate immediate revenue, annual members provide a consistent, recurring income stream and foster customer loyalty. Understanding the behavioral differences between these two customer segments is crucial for designing effective marketing campaigns that target casual riders and encourage them to opt for a full membership.

## 3. The Data

The dataset used for this analysis is Cyclistic's historical trip data, provided by Google. It contains detailed information about individual bike trips, including:
* Trip ID
* Bike Type (classic, electric, docked)
* Start and End Times
* Start and End Station Names & IDs
* Geographical Coordinates (latitude, longitude)
* User Type (casual or member)

*Initial observation: The raw data contains millions of rows across multiple CSV files (for each month), requiring significant cleaning and aggregation to prepare for analysis.*

## 4. Tools Used

The following tools were utilized throughout this project:

* **Data Collection & Storage:** Google Cloud / Google BigQuery (for SQL querying of the public dataset)
* **Data Cleaning & Transformation:** SQL (BigQuery), Google Sheets / Microsoft Excel, R (dplyr, tidyr)
* **Data Analysis:** SQL (BigQuery), R (dplyr, ggplot2, tidymodels - if applicable)
* **Data Visualization:** Tableau Public / Google Looker Studio (or Microsoft Excel, if you plan to use it for visualizations), R (ggplot2)
* **Reporting & Documentation:** R Markdown (for R code and narrative), GitHub Markdown (`README.md`)

## 5. Analysis Process

My analysis will follow the six-phase data analysis process to answer the business question and inform a marketing strategy.

### 5.1. Ask (Define the Business Problem)
* **Business Task:** Design marketing strategies aimed at converting casual riders into annual members. This requires a thorough understanding of how annual members and casual riders use Cyclistic bikes differently.
* **Guiding Questions:**
    * How do annual members and casual riders use Cyclistic bikes differently?
    * What are the key distinctions in ride patterns, ride duration, and station usage between the two groups?
* **Stakeholders:** Lily Moreno, the Director of Marketing, and the Cyclistic Executive Team.

### 5.2. Prepare (Data Collection & Storage)
* **Data Source:** Cyclistic's historical trip data, provided by Google through the Google Data Analytics Professional Certificate. The data is public and anonymized to protect user privacy.
* **Data Selection:** I will download and use the previous 12 months of trip data, organized in separate CSV files.
* **Data Storage:** The data will be initially stored locally and planned for upload to a cloud environment (e.g., Google BigQuery) for efficient SQL querying and subsequent analysis in R or direct visualization tool import.
* **Data Integrity:** The data is current, cited, and original, but it must be checked for reliability.

### 5.3. Process (Data Cleaning & Transformation)
* **Data Consolidation:** I will combine the 12 monthly CSV files into a single dataframe using R.
* **Data Cleaning:**
    * Identify and remove rows with missing values, particularly in station name and station ID columns.
    * Check for and remove duplicate entries.
    * Filter out illogical ride durations, such as negative values or rides exceeding a full day.
* **Feature Engineering:**
    * Calculate `ride_length` by subtracting the ride's start time from its end time.
    * Extract new columns from the `started_at` timestamp, including `day_of_week`, `month`, and `year`, to facilitate further analysis.
* **Data Formatting:** Ensure all columns have the correct data types, especially for dates, times, and numerical values.

### 5.4. Analyze (Explore & Find Patterns)
* **Exploratory Data Analysis (EDA):** I will calculate descriptive statistics, such as the mean, median, and mode, for both casual and member riders.
* **Usage Patterns:**
    * Compare the total number of rides and average ride duration for casual riders versus annual members.
    * Analyze ride frequency by day of the week, month, and hour of the day for each user group.
    * Identify the top 10 most popular start and end stations for both user types.
* **Hypothesis Testing:** I will use the analysis to test the hypothesis that casual riders' bike usage is primarily for leisure, while annual members' usage is for commuting.

### 5.5. Share (Visualize & Communicate Findings)
* **Data Storytelling:** I will use R Markdown to create a coherent narrative that presents the findings.
* **Key Visualizations:**
    * Bar charts showing ride duration and ride count by rider type.
    * Line charts to illustrate usage trends over the days of the week, months, and hours.
    * Maps or bar charts highlighting popular station locations for each user group.
* **Dashboard:** An interactive dashboard will be created using Tableau Public to allow stakeholders to explore the data.

### 5.6. Act (Recommendations & Next Steps)
* **Recommendations:** I will provide a clear set of actionable recommendations to Cyclistic's marketing team, directly supported by the data analysis and visualizations. These recommendations will focus on converting casual riders to members.
* **Next Steps:** I will conclude the report by outlining limitations of the current analysis and suggesting avenues for future research, such as incorporating external data like weather or surveying riders directly.

## 6. Key Findings & Insights

*This is where you summarize the most important discoveries from your analysis. Use bullet points for clarity. This section should directly address the "how do they use bikes differently?" question.*

* **Ride Duration:** Casual riders consistently have significantly longer average ride durations (e.g., X minutes) compared to annual members (e.g., Y minutes), suggesting leisure use.
* **Time of Week:** Casual riders exhibit peak usage during weekends and holidays, whereas annual members show more consistent weekday usage, indicative of commuting.
* **Popular Stations:** While some stations are popular with both groups, casual riders show higher concentrations around recreational areas (e.g., parks, tourist spots) on weekends.
* **Bike Type Preference:** [Your finding, e.g., Classic bikes are preferred by casual riders for longer leisure rides, while electric bikes might appeal to members for commutes.]
* **Seasonal Trends:** [Your finding, e.g., Casual rider activity peaks significantly in warmer months, while member activity remains relatively stable year-round.]

## 7. Recommendations

*Based on your findings, what specific, actionable steps should Cyclistic take to convert casual riders? Try to quantify the potential impact if you can.*

Based on the analysis, I recommend the following strategies for Cyclistic to increase annual memberships:

1.  **Weekend & Holiday Membership Promotions:** Offer discounted weekend passes or a "first month free" trial specifically targeted at casual riders observed during peak weekend usage times. *This aligns with casual riders' leisure-oriented behavior.*
2.  **Targeted Marketing at Leisure Hubs:** Place prominent advertising (digital and physical) at popular casual rider start/end stations near parks, lakeshores, and tourist attractions, emphasizing the cost-effectiveness of membership for frequent leisure rides.
3.  **Flexible Membership Tiers:** Explore offering shorter-term (e.g., 3-month or seasonal) membership options that cater to casual riders who might not commit to a full year but use bikes heavily during specific seasons.
4.  **Highlight "Long Ride" Savings:** Create marketing collateral that clearly demonstrates the cost savings of an annual membership for longer, leisure-oriented rides, directly addressing casual rider behavior.
5.  **Gamification/Loyalty Program:** Implement a loyalty program that rewards casual riders with points for each ride, leading to discounts on a full membership once certain ride thresholds or durations are met.

## 8. Next Steps & Limitations

### Limitations:
* The current dataset lacks demographic information (e.g., age, income, residential area) for riders, which could offer deeper insights into casual rider segmentation and targeted marketing.
* External factors such as weather conditions, special events, or public transport disruptions were not included in this analysis but could significantly influence rider behavior.
* The analysis relies solely on trip data; qualitative data (e.g., user surveys on motivations, satisfaction, or barriers to membership) was not available.

### Future Work:
* Integrate external datasets such as weather data, local events, or public holidays to enrich the analysis and identify further correlations with rider behavior.
* Conduct user surveys or focus groups to gather qualitative insights into casual riders' needs, pain points, and reasons for not purchasing a full membership.
* Perform a profitability analysis to quantify the exact return on investment for converting casual riders into annual members.
* Explore advanced analytical techniques such as customer segmentation (e.g., using clustering algorithms) to identify distinct casual rider groups for highly tailored marketing campaigns.
* Conduct user surveys to gather qualitative data on why casual riders haven't converted and what incentives would be most appealing.
* Perform a profitability analysis to quantify the exact value of converting casual riders to members.
* Explore advanced statistical modeling (e.g., clustering) to identify distinct casual rider segments for even more tailored marketing.
