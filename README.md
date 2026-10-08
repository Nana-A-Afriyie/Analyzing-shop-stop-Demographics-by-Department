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

## 🖥️ Dashboard Explained (Power BI View)

The Power BI dashboard is structured into three main visual blocks designed for rapid executive review:
|                         SHOP & STOP DEMOGRAPHICS DASHBOARD                       |
+---------------------------------------------------------------------------------+
|  [ KPI 1: 4K Customers ]   [ KPI 2: Avg Income 1.20M ]   [ KPI 3: Avg Age 45.37 ] |
+------------------------------------+--------------------------------------------+
|  Annual Income by Membership Tier  |  Customer Count by Marital Status          |
|  (Bar Chart: Silver/Gold Lead)     |  (Bar Chart: Single/Married Lead)          |
+------------------------------------+--------------------------------------------+
|  Customer Count by City            |  Customer Count by Loyalty Tier            |
|  (Bar Chart: Top Cities)           |  (Bar Chart: Silver > Gold > Platinum)     |
+------------------------------------+--------------------------------------------+
|  Sum Age / Customers by Gender     |  Total Customers Onboarded by Year         |
|  (Stacked Column: 50/50 Split)     |  (Bar Chart: 2018–2026 Trend)              |
Top Header & KPI Cards:** Highlights macro business metrics including Total Customers (4K), Average Income (1.20M), and Average Age (45.37) for quick snapshot context[cite: 2].
2. **Loyalty & Financial Breakdown:**
   * **Sum of Annual Income by Tier (Bar Chart):** Compares total income capacity by loyalty status, identifying Silver and Gold as top drivers[cite: 2].
   * **Customers by Tier (Bar Chart):** Maps customer distribution across Silver, Gold, Platinum, First Citizen, and non-members
3. **Demographic & Geographic Panels:**
   * **Marital Status & Gender Visuals:** Highlights demographic splits across single vs. married consumers and gender parity
   * **Customer Count by City:** Ranks urban performance from high-volume cities like Pune and Ahmedabad down to smaller hubs
   * **Yearly Onboarding Trend (2018–2026):** Tracks historical growth consistency over an 8-year span
   * **Core strategic reccomendation**
   * 1. Loyalty Program Optimization & Tier Progression
Capitalize on Mid-Tier Value (Silver & Gold): Silver and Gold members account for over 60% of total customers and generate over ₹3.1bn in combined annual income capacity.   
Recommendation: Create targeted upgrade campaigns offering double reward points or exclusive perks for 3–6 months to transition active Silver and Gold cardholders into Platinum and First Citizen tiers.

Convert Non-Members ("None" Tier): Over 500 customers currently hold no membership tier.   
Recommendation: Implement a low-barrier, automated sign-up initiative at checkout (e.g., instant 5% off first order upon joining) to convert non-members into tracked loyalty accounts.
2. Demographic-Targeted Merchandising & Marketing
Focus on Core Age Group (Avg. Age ~45 Years): The primary customer base is mature working professionals with mid-to-high annual incomes (~₹1.20M).   


Recommendation: Tailor marketing campaigns around premium quality, durability, career apparel, home goods, and health/wellness product lines rather than discount-heavy fast fashion.

Leverage Household & Lifestyle Bundles: Single and Married consumers form over 70% of the customer base.   
Recommendation: Offer dual-person or family reward packages, weekend shopping events, and targeted promotions on home essentials, kitchenware, and seasonal gifting.

3. Geographic & Regional Expansion Strategy
Nurture High-Volume Regional Hubs: Cities like Pune, Ahmedabad, Kolkata, Chennai, and Hyderabad show strong customer density (~500–600 customers per city).   
Recommendation: Strengthen localized marketing, store inventory availability, and regional promotional events in these top 5 high-density cities.

Target Low-Penetration Metros: Markets like Mumbai, Bangalore, and New Delhi exhibit relatively lower customer volume in this dataset despite being major metropolitan hubs.   
Recommendation: Conduct targeted digital ad campaigns and localized brand partnerships in these underperforming metro regions to capture untapped market share.

4. Data Governance & Analytics Infrastructure
Cleanse & Standardize Master Data: Duplicate city records (e.g., Bangalore vs. Bengaluru, Mumbai vs. Mumbai) and casing inconsistencies in raw records indicate gaps in data collection hygiene.   

[shoppers_stop_demographics_RD.csv](https://github.com/user-attachments/files/33227564/shoppers_stop_demographics_RD.csv)
[shoppers_stop_demographics_cleaned.csv](https://github.com/user-attachments/files/33227559/shoppers_stop_demographics_cleaned.csv)
<img width="868" height="469" alt="Screenshot 2026-10-08 183106" src="https://github.com/user-attachments/assets/666174aa-3112-40e8-9ec9-e2e0bce00955" />
<img width="815" height="449" alt="Screenshot 2026-10-08 183159" src="https://github.com/user-attachments/assets/d569edb6-6a3f-4292-b6bc-2f633abedd09" />

Recommendation: Implement automated validation rules and drop-down menus at point-of-sale (POS) and online registration portals to prevent typos, duplicate city names, and inconsistent formatting at the point of ingestion.
