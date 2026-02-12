# 🚀 Meta (Facebook & Instagram) Ad Performance Dashboard

## 1. About the Project-
This project analyzes a dataset of **Meta Ads (Facebook & Instagram)** to track the effectiveness of marketing campaigns. By connecting ad spend to actual user engagement and purchases, this dashboard provides a full-funnel view of marketing performance—from "Impressions" (Awareness) to "Purchases" (Conversion).

## 2. Project Objective- 
To enable the marketing team to optimize their **$2.5M Budget** by:
   * Comparing platform performance (Facebook vs. Instagram).
   * Identifying the most profitable Ad Formats (Video, Carousel, etc.).
   * Pinpointing the peak times and demographics for maximum ROI.

## 3. Dashboard Snapshot-

Check out the dashboard here - 
 **[Dashboard](https://github.com/dataspecialist/Marketing-analysis/blob/main/meta_ads_dashboard.pbix)** 

 **FACEBOOK**
 **INSTAGRAM**

## 4. Key KPIs & Definitions-
Standard metrics used to measure campaign health.
| **KPI** | **Value** | **Definition** |
| :--- | :--- | :--- |
Impressions	| 216K	| Total number of times the ad was displayed to users.
Clicks	| 25.4K	| Number of times users clicked on the ad.
CTR (Click-Through Rate)	| 11.76%	| (Clicks / Impressions) * 100. Indicates ad creative effectiveness.
Purchases	| 1.3K	| Total number of completed transactions/conversions.
Conversion Rate	| 5.21%	| (Purchases / Clicks) * 100. Measures landing page efficiency.
Total Spend	| $2.5M	| Total budget utilized across all campaigns.

## 5. Platform-wise Performance
Comparative analysis of traffic sources.
| **Mertic** | **Facebook** | **Instagram** | **Winner** |
| :--- | :--- | :--- |:--- |
Impressions	| 216K	| 123.8K | ✅ Facebook
CTR %	| 11.76%	 | 11.70%	|✅ Facebook (slightly higher)
Purchases	| 1.3k	| 708	| ✅ Facebook
Cost Per Purchase	| 1.9K	| 3.5K	| ✅ Facebook (Lower is better)

🏆 **Final Winner: Facebook**
* 🎯 Why?
    * Higher reach
    * Slightly better CTR
    * Almost double the purchases
    * Much lower Cost Per Purchase

* 📊 Business Conclusion:
If your objective is performance marketing (conversion-focused) →
👉 Allocate more budget to Facebook

## 6. Technical Process
* **Step 1: Data Preparation (ETL)**
  * Source: 4 CSV tables (ad_events, ads, campaigns, users_data).
  * Transformation:
      * Promoted headers and corrected data types in Power Query.
      * Created a standard Date Table to enable time-intelligence analysis (Weekly/Monthly trends).
      * Merged ad_events with users_data to analyze demographics (Age/Gender).

* **Step 2: Data Modeling**
  * Built a Star Schema data model to ensure efficient filtering:
    * Fact Table: ad_events (Contains 1M+ rows of logs).
    * Dimension Tables: ads, campaigns, users, Calendar.
    * Relationships: One-to-Many relationships established between Dimensions and the Fact table.

* **Step 3: DAX Measures**
Used advanced DAX for dynamic aggregation.
  * CTR %: DIVIDE(SUM(ad_events[Clicks]), SUM(ad_events[Impressions]), 0)
  * Conversion Rate: DIVIDE(COUNT(ad_events[Purchases]), COUNT(ad_events[Clicks]), 0)
  * Dynamic Title: SELECTEDVALUE(Campaign[Name]) & " Performance Report"
 
## 7. Visuals Used & Why
| **Visual** | **Purpose** |
| :--- | :--- |
Calendar Heatmap	| To identify specific dates (e.g., 19th-21st) with engagement spikes due to promotions.
Stacked Column Chart	| To show Weekly Trends split by Ad Type (Video vs. Image).
Area Chart	| To visualize Hourly Trends (0-23 hours) and find peak user activity times.
Matrix Table	| To breakdown performance by Ad Format (Video, Carousel, Story) with conditional formatting.

## 8. Key Insights & Summary
* Video is King: Video ads achieved the highest CTR and Engagement Rate, outperforming static images and carousels.
* The "漏 Leaky Bucket": While awareness is high (11.76% CTR), the Purchase Rate is low (0.61%). This suggests the ads work, but the Landing Page needs optimization.
* Demographics: The primary audience driving engagement is Females (18-30), specifically from India and Brazil.
* Timing Matters: Engagement peaks in the Afternoon & Evening, suggesting ad spend should be weighted toward these hours.****

## 9. Decision & Action Table
Strategic recommendations based on data evidence.
| **Observation** | **Recommended Action** | **Expected Impact** |
| :--- | :--- | :--- |
High CTR (11%) but Low Conversion (5%)	| A/B test the Landing Page layout and checkout process.	| Improve conversion rate by ~2% by reducing friction.
Video Ads have highest ROI	| Shift 60% of the budget allocation to Video & Story formats.	| Maximize engagement per dollar spent.
India & Brazil driving traffic	| Create localized ad content (local language/currency) for these regions.	| Increase relevance and trust for these top markets.
Engagement spikes on 25th-27th	| Schedule "Flash Sales" or major campaigns during these specific monthly windows.	 | Align marketing push with natural user behavior.


















