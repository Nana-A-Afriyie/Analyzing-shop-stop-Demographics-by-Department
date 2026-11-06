# Analyzing-shop-stop-Demographics-by-Department
This project analyzes customer demographic, income, location, and loyalty tier data for Shop &amp; Stop (4,000 unique customers). The primary goal is to evaluate customer segment distributions, regional revenue patterns, loyalty program engagement, and historical customer acquisition trends from 2018 through 2026.
# 🛒 Shop & Stop Demographics & Customer Segmentation Analysis

## 📌 Introduction
This project provides an end-to-end exploratory data analysis (EDA) and demographic segmentation for **Shop & Stop**, a major retail department store chain. By analyzing customer demographics, income distributions, geographical spread, and loyalty program participation, this project aims to uncover key consumer traits, evaluate loyalty program ROI, and identify high-value customer segments to inform targeted marketing and retention strategies.

---

## 📅 About the Dataset
The raw dataset (`shoppers_stop_demographics_RD.csv`) consists of **5,000 customer records** capturing demographic, financial, and loyalty engagement details across major metropolitan retail locations in India.

### **Dataset Features**
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `customer_id` | String | Unique identification code assigned to each customer |
| `full_name` | String | First and last name of the customer |
| `gender` | String | Customer gender designation |
| `age` | Integer | Customer age in years |
| `dob` | Date / String | Customer date of birth |
| `email` | String | Recorded primary email contact |
| `phone_number` | Numeric / String | Customer mobile contact number |
| `annual_income` | Float | Estimated annual income (in INR) |
| `marital_status` | String | Marital status (Single, Married, Divorced, Widowed, Unknown) |
| `membership_tier` | String | Loyalty membership tier (Silver, Gold, Platinum, First Citizen, None) |
| `city` | String | Primary urban retail location |
| `postal_code` | String / Integer | Local area postal code |
| `join_date` | Date / String | Date customer registered with the Shop & Stop network |

---

## 🧹 Data Cleaning Process (Excel Workflow)
To prepare the raw CSV data for Power BI dashboard modeling, systematic data cleaning was performed in Microsoft Excel:

1. **Deduplication:**
   * Applied **Data > Remove Duplicates** on `customer_id` to eliminate **800 duplicate records**, filtering the dataset from 5,000 raw rows to **4,000 unique customer profiles** to ensure accurate KPI aggregation.
2. **Text Normalization & Whitespace Removal:**
   * Used `=TRIM()` and `=PROPER()` to fix inconsistent capitalization and eliminate trailing/leading whitespace.
   * Standardized city names (e.g., converted `HYDERABAD`, `hyderabad`, and ` Mumbai ` into proper proper-cased format).
   * Consolidated city naming aliases by renaming `Bangalore` to `Bengaluru`.
3. **Categorical Standardization:**
   * **Gender:** Unified diverse string representations (`M`, `m`, `Male`, `MALE`) to **Male** and (`F`, `f`, `Fem`, `Female`) to **Female**.
   * **Marital Status:** Mapped shorthand codes like `S` to **Single** and `M` to **Married**.
   * **Membership Tier:** Standardized tier levels (`Silver`, `Gold`, `Platinum`, `First Citizen`).
4. **Missing Value Imputation (`NULL` Handling):**
   * Replaced blank loyalty fields with `"None"` to represent non-cardholders.
   * Imputed missing `annual_income` values using mean aggregation (~₹1.20M).
   * Replaced blank phone numbers with `"N/A"`.
5. **Data Type Standardization:**
   * Formatted `dob` and `join_date` as Short Date format (`MM/DD/YYYY`).
   * Stripped invalid negative signs from numeric phone numbers.

---

## 📊 Analysis & Key Findings

### **1. Executive Key Performance Indicators (KPIs)**
* **Total Customer Base:** 4,000 unique active customers[cite: 2].
* **Average Customer Age:** 45.37 years old[cite: 2].
* **Average Annual Income:** ₹1.20M across all member tiers[cite: 2].

### **2. Demographic Distribution**
* **Balanced Gender Ratio:** Customer base exhibits an almost equal 50/50 split (~50.07% Female vs. ~49.93% Male)[cite: 2]. Total age volume distribution across genders sits equally at ~100K combined[cite: 1].
* **Marital Status Trends:** **Single** (~1,400+) and **Married** (~1,400+) customers make up over 70% of the entire customer base[cite: 2]. Divorced, Widowed, and Unknown statuses account for smaller, equal proportions (~400–500 each)[cite: 2].

### **3. Loyalty Program Performance**
* **Tier Prevalence:** **Silver** (~1,250 members) and **Gold** (~1,150 members) are the dominant membership tiers[cite: 2].
* **Income Contribution:** **Silver** (~1.6bn) and **Gold** (~1.5bn) tiers drive the vast majority of cumulative annual customer income, vastly outperforming Platinum and First Citizen tiers due to higher volume[cite: 2].

### **4. Geographic Penetration**
* **Top Metro Markets:** **Pune**, **Ahmedabad**, **Kolkata**, **Chennai**, and **Hyderabad** represent the highest volume markets (~500–600 customers per city)[cite: 2].
* **Steady Regional Spending:** Average income across cities stays consistently balanced around ₹6M per tier stack across all primary hubs[cite: 1].

---

## ❓ Analytical Questions & Strategic Insights

### **Q1: Which customer tier drives the most business revenue potential?**
* **Insight:** While **Platinum** and **First Citizen** tiers cater to premium spenders, **Silver** and **Gold** members represent over 60% of total customer volume and drive over **₹3.1bn** in combined annual customer income[cite: 2]. 
* **Action:** Retail strategies should focus on upsell campaigns to migrate active Silver/Gold members into higher-tier programs.

### **Q2: Is there a specific demographic target for upcoming promotional events?**
* **Insight:** With an average customer age of **45 years** and a core base of **Single and Married** working adults, marketing messaging should focus on household lifestyle goods, career-focused apparel, and family reward packages[cite: 2].

### **Q3: What do acquisition trends over time reveal?**
* **Insight:** Annual customer onboarding remained remarkably stable from **2018 through 2025** at ~500–550 new customers per year[cite: 1]. The drop observed in **2026** (~100 customers) reflects YTD partial-year data collection rather than churn[cite: 1].

---

**Stop & Shop Customer Demographics Dashboard Explanation**

1. Dashboard Overview
The Stop & Shop Customer Demographics Dashboard analyzes customer characteristics, membership patterns, and geographic distribution to help the business better understand its customers.

The dashboard focuses on six areas: customer age, gender, income, membership tiers, yearly customer trends, and city distribution.

It also includes filters for Department, Gender, Age Group, Membership Tier, Year, and City, allowing users to explore specific customer segments.
2. Dashboard Filters
The dashboard currently displays the following selections:
Filter	Selected Value
Department	Groceries
Gender	Female
Age Group	30–39
Membership Tier	All
Year	All
City	All

These filters are intended to allow users to examine particular customer groups and understand their characteristics.
3. Key Performance Indicators (KPIs)
Average Age34.27
Years


Total Customers658
Customers


Average Income$1.18M
Displayed value



The KPI cards provide a quick overview of the selected customer segment. The average age is 34.27 years, while the total customer count is 658. The dashboard also displays an average income of $1.18 million, although the income calculation and unit should be verified.
4. Dashboard Visual Analysis
A. Total Customers by Gender
The donut chart displays the gender distribution:
- Female: 341 customers (51.8%)
- Male: 317 customers (48.2%)
The chart suggests that female customers slightly outnumber male customers, although the difference is relatively small.
B. Total Customers by Age Group
The age-group chart highlights the 30–39 category with 658 customers.

This suggests that customers aged 30–39 represent an important demographic segment in the displayed analysis.
C. Total Customers by Membership Tier
Silver

236 (35.9%)




Gold

200 (30.4%)




Platinum

104 (15.8%)




First Citizen

68 (10.3%)




Unknown

50 (7.6%)





Silver membership has the highest customer count, followed by Gold. Together, these two categories represent 66.3% of the displayed customers.

This indicates that Silver and Gold membership segments deserve attention when developing customer loyalty and retention strategies.
D. Total Customers by Year
The chart tracks customer counts from 2018 to 2026.
- 2023 recorded the highest displayed count of 104 customers.
- Customer counts fluctuate across the reporting years.
- 2026 shows the lowest count at 18, although this may represent incomplete-year data.
These variations can help the business investigate changes in customer acquisition and engagement.
E. Total Customers by City
Pune has the highest displayed customer count at 110, followed by Ahmedabad at 98 and Kolkata at 95.

This suggests that these cities represent important customer locations within the displayed data and could be considered for targeted marketing campaigns.

**. Key Findings**
1. The selected dashboard view highlights 658 customers, with an average age of 34.27 years.
2. Female customers slightly outnumber male customers in the displayed gender breakdown.
3. Silver and Gold are the leading membership categories.
4. Customer counts vary across years, with 2023 showing the highest displayed count.
5. Pune, Ahmedabad, and Kolkata lead the city distribution.
   
**Business Recommendations**

Improve customer targeting: Develop marketing strategies based on customer age groups, purchasing behavior, and department preferences.

Strengthen membership programs: Introduce personalized offers and rewards to improve Silver and Gold member retention.

Focus on important locations: Investigate customer demand in Pune, Ahmedabad, and Kolkata to identify opportunities for business growth.

Monitor customer trends: Analyze yearly changes in customer counts to understand acquisition, retention, and possible seasonal patterns.

Improve customer segmentation: Use demographic filters to compare customer groups and support better business decisions.
**. Conclusion**

The Stop & Shop Customer Demographics Dashboard provides insights into customer characteristics, membership patterns, and geographic distribution. By analyzing these metrics, the business can identify important customer segments, improve marketing strategies, and support customer retention initiatives.


<img width="1672" height="941" alt="Stop Shop Demographics Dashboard (1)" src="https://github.com/user-attachments/assets/bc72c278-0ba8-47ff-ba2d-b324b1e357f3" />
<img width="1672" height="941" alt="Stop   Shop Demographics Dashboard" src="https://github.com/user-attachments/assets/74619722-90a8-42a9-b2dd-6a5b7bd3aa04" />


[ST&SP_Demographics.csv](https://github.com/user-attachments/files/33639197/ST.SP_Demographics.csv)



Recommendation: Implement automated validation rules and drop-down menus at point-of-sale (POS) and online registration portals to prevent typos, duplicate city names, and inconsistent formatting at the point of ingestion.
