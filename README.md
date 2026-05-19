# Google Merchandise Store: E-commerce Funnel Optimization & Unit Economics Analysis

A comprehensive data analytics project focused on evaluating user behavior, product funnel conversion efficiency, cross-platform technical health, and marketing ROI for the Google Merchandise Store using raw event-level GA4 data.

---

## 🛠️ Project Ecosystem & Tech Stack
* **Data Warehouse & Processing:** Google BigQuery (SQL) using advanced techniques (`UNNEST` for parsing event parameters, Window Functions for marketing touchpoints, and Cohort Analysis).
* **BI Visualization:** Looker Studio (Interactive Executive Dashboard featuring key KPI scorecards, multi-step funnels, and retention heatmaps).
* **Framework:** Pure E-commerce Analytics (Session tracking, Product performance, Conversion diagnostics, and Unit Economics).

---

## 📁 Repository Structure
```text
├── Google_Merchandise_Store_SQL_Queries.pdf  # Comprehensive technical archive with all SQL queries
└── README.md                                 # Main portfolio presentation, dashboard link, and business analysis report

---

## 💻 SQL Data Analysis & Key Insights

### 1. E-commerce Purchase Funnel Performance
By parsing nested raw GA4 logs, I mapped the complete user journey from landing to purchase to isolate the exact friction points.

| Funnel Stage | Unique Users | Step Conversion Rate | Total Drop-off Rate |
| :--- | :--- | :--- | :--- |
| **1. Session Start** | 78,383 | 100.00% | 0.00% |
| **2. View Item** | 21,089 | 26.91% | -73.09% |
| **3. Add to Cart** | 2,042 | 9.68% | -90.32% |
| **4. Begin Checkout** | 1,047 | 51.27% | -48.73% |
| **5. Purchase** | 445 | 42.50% | -57.50% |

* **Analytical Insight:** The primary bottleneck is located strictly between **View Item** and **Add to Cart**, experiencing an intense **90.32% drop-off**. Once a user successfully adds an item to the cart, their purchase intent spikes, leading to a strong checkout-to-purchase conversion rate of 42.50%.

---

### 2. Cross-Platform Technical Diagnostics (Hypothesis Testing)
I segmented the final purchase stage by operating systems to test the hypothesis of a potential technical or payment gateway failure on mobile platforms.

| Platform OS | Total Sessions | Successful Purchases | Session-to-Purchase CR (%) |
| :--- | :--- | :--- | :--- |
| **iOS** | 12,352 | 183 | **1.48%** |
| **Android** | 9,459 | 142 | **1.50%** |

* **Analytical Verdict:** The initial hypothesis regarding a platform-specific bug or payment failure on Android was **completely refuted**. Both mobile operating systems display near-identical, stable conversion performance (~1.5%). The minor variance falls strictly within the statistical margin of error, proving that the checkout infrastructure is technically sound across platforms.

---

### 3. Cohort Retention & Cumulative LTV Modeling
I tracked the user cohort acquired in November 2020 over a 6-month observation window (through April 2021) to analyze user retention alongside revenue velocity.

* **Product Retention (Cohort Size: 79,421 Users):**
  * **Day 7 Retention Rate:** 2.69% (2,138 returning users)
  * **Day 30 Retention Rate:** 1.16% (918 returning users)

* **6-Month Cumulative LTV Expansion (Google Traffic Group):**
  * Month 1 Cumulative LTV: **$2.47**
  * Month 3 Cumulative LTV: **$3.10** *(+25.5% expansion)*
  * Month 6 Cumulative LTV: **$3.16**

* **Analytical Insight:** Despite a steep drop-off in user retention by Day 30 (1.16%), the returning core segment drives reliable repeat transactions. This increases cumulative LTV by 25.5% by Month 3, validating that long-term cohort monetization effectively mitigates high Customer Acquisition Costs (CAC).

---

### 4. Marketing Attribution & Traffic Source Performance
To evaluate the true value of acquisition channels, I mapped user paths to analyze how customers initially discover the store (First-Touch) versus which touchpoints directly precede their sessions and final interactions (Last-Touch).

| First-Touch Source | Last-Touch Source | Tracked Users Cohort | % of Cohort |
| :--- | :--- | :--- | :--- |
| **Organic Search** | **Direct** | 24,152 | 30.41% |
| **Direct** | **Direct** | 18,491 | 23.28% |
| **Organic Search** | **Organic Search** | 12,043 | 15.16% |
| **Referral** | **Direct** | 5,832 | 7.34% |
| **Youtube** | **Direct** | 3,114 | 3.92% |

* **Analytical Insight & Channel Decay Effect:** The data reveals a strong brand recall and intent retention pattern. A dominant segment of users (**30.41%**) find the store via **Organic Search** but return to execute final actions via **Direct** traffic. This proves that organic positioning effectively feeds a high-retention pipeline, transforming casual searchers into users who bookmark the site or enter the URL directly.
* **Top-of-Funnel Value of YouTube:** While YouTube shows lower bottom-funnel direct attribution, it acts as a critical top-of-funnel awareness builder, successfully introducing 3.92% of the total tracked cohort who later navigate back to purchase directly.

---

## 📊 Actionable Strategic Recommendations

1. **Optimize Product Card UX/UI:** Focus engineering and design resources on the 90% friction gap between product viewing and cart addition. Run A/B tests on "Add to Cart" button prominence and streamline the product detail layout.
2. **Global Checkout Optimization:** Since iOS and Android perform uniformly, future checkout enhancements (e.g., one-click checkout or immediate Apple Pay/Google Pay placement) should be deployed globally rather than targeting platform-specific codebases.
3. **Triggered Post-Purchase Retargeting:** Revenue expansion stalls significantly between Month 3 and Month 6 ($3.10 to $3.16). Launch automated lifecycle email tracks and personalized win-back offers around day 60–90 to stimulate repeat purchases.

---

## 📈 Dashboard Preview
<img width="900" height="675" alt="Product_Funnel_ _Marketing_ROI_Performance" src="https://github.com/user-attachments/assets/8687d5af-bc0a-4274-9203-a5c215576d26" />


---

## 📊 Live Interactive Dashboard
To explore the data insights, filters, and dynamic metrics components built for this project, access the live Looker Studio report:

[![View Live Dashboard](https://img.shields.io/badge/Looker_Studio-View_Live_Dashboard-0f2c59?style=for-the-badge&logo=googleanalytics&logoColor=white)](https://datastudio.google.com/s/n3c7M_UwKWo)

*Alternative link:* [Open Looker Studio Report](https://datastudio.google.com/s/n3c7M_UwKWo)
