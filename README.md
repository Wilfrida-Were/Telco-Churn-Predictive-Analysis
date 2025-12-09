# Telco Churn Predictive Analysis

## Project Goal: Helping Telco Founders Predict, Prevent, and Prioritize Churn

This project is built for **telco founders and product leads** who need fast, interpretable insights to reduce churn, protect revenue, and guide retention strategy.

Common Business Problems I Hear:

> *“We know customers are leaving, but we don’t know who, when, or why.
> We don’t have time to dig through dashboards or build predictive models.
> We need clear, actionable insights to prevent churn before it happens.”*

This project explores a fictional telco dataset to uncover churn risk signals, segment-level revenue exposure, and retention opportunities designed to help teams act faster, smarter, and with confidence.

## Business Impact Summary
- Identified high-risk customer segments for targeted retention campaigns
- Quantified revenue at risk to prioritize churn prevention efforts
- Simulated retention impact to guide strategic resource allocation
- Revealed behavioral and contractual churn drivers for proactive outreach
- Delivered founder-grade recommendations aligned with revenue protection and customer lifetime value growth

For those who want to explore the full code on Kaggle:

👉 [Telco Churn Predictive Analysis](https://www.kaggle.com/code/wilfridawere/telco-churn-predictive-analysis)

## 📑 Table of Contents
* [Interactive Dashboard](#dashboard)
* [Key Insights](#key-insights)
* [Recommendations](#recommendations)
* [Client Scenario:Applying the Recommendations](#client-scenario)
* [Who Can Use This Project](#who-can-use-this-project)
* [Tech Stack](#tech-stack)
* [Workflow](#workflow)
* [Let’s Connect](#lets-connect)

<a id="dashboard"></a>
## Interactive Dashboard

👉 [View the Interactive Dashboard on Metabase](http://metabase-dashboard.fly.dev/public/dashboard/833e66ef-1d4d-403a-8cdf-64b16ad82eda)  

Preview (click image to open dashboard):  
[![Telco Churn Dashboard](https://raw.githubusercontent.com/Wilfrida-Were/Telco-Churn-Predictive-Analysis/main/Telco%20Churn%20Predictive%20Analysis.png)](http://metabase-dashboard.fly.dev/public/dashboard/833e66ef-1d4d-403a-8cdf-64b16ad82eda)

---

<a id="key-insights"></a>  
## 🔑 Key Insights

The goal isn’t just to describe churn. It’s to anticipate it, segment it, and eventually act on it. 

Here’s what the data reveals:

### Key Performance Indicators (KPIs)

These headline metrics summarize the current state of customer churn and revenue impact:

| KPI | Value |
|-----|-------|
| **Total Revenue** | 16.1M | 
| **Revenue Lost** | 2.86M | 
| **Revenue at Risk** | 3.29M |
| **Total Customers** | 7,043 | 
| **Ongoing Customers** | 7,032 | 
| **New Customers** | 11 | 
| **Actual Churn Rate** | 26.58% |
| **Expected Churn Rate** | 36.39% | 

### 1. Churn Is Already Costing Us and the Bigger Risk Is Still Ahead
- We’ve lost **2.86M** in revenue from churned customers.
- But **3.29M** is still at risk—tied to ongoing customers flagged as likely to churn.
- Out of **7,032 ongoing customers**, **5,163** are still active (haven’t churned yet), and **1,879** of them (36%) are expected to churn.
- The model’s expected churn rate (**36.39%**) is higher than the actual (**26.58%**), suggesting either delayed churn or early retention success.
- This gap is a warning signal but also an opportunity. These active, at-risk customers are the ones we can still save. This is the core retention battleground.

---

### 2. Medium Risk = Maximum Leverage
- **High Risk** customers are few (303), but **Medium Risk** customers (1,108) hold the largest share of revenue at risk.
- This challenges the assumption that High Risk is always the most urgent.
- Medium Risk is where financial leverage lives. Retention here yields the biggest savings.

---

### 3. Month-to-Month Contracts: The Structural Weak Spot
- These customers account for **90.63%** of total expected churn.
- Predicted to churn: **76.71%** of the month-to-month segment.
- They’re flexible but fragile. This segment dominates churn volume and risk.

---

### 4. Long Tenure Doesn’t Guarantee Loyalty
- Highest expected revenue losses come from:
  - **Month-to-month contracts**
  - **Customers with tenure ≥ 12 months**
- These customers have been with the business long enough to generate meaningful revenue but they’re still flagged as risky.
- This signals a loyalty gap. Tenure alone doesn’t protect against churn.

---

### 5. Payment Friction Is a Churn Signal
- **Electronic check** users represent **47.68%** of total expected churn.
- Predicted to churn: **69.24%** of this segment.
- Manual payment flows correlate with higher churn. This is a behavioral red flag.

---

### 6. Missing Support Services = Missing Loyalty
- **OnlineSecurity = No** → **64.78%** predicted churn  
- **TechSupport = No** → **65.55%** predicted churn  
- Each contributes over **70%** of total expected churn.
- These features aren’t just upsells, they’re anchors. Their absence consistently signals churn across models and segments.

---

### 7. Fiber Optic Users: High Expectations, High Risk
- Fiber users contribute **56.47%** of total expected churn.
- Predicted to churn: **58.98%** of this segment.
- This challenges assumptions about product quality and pricing. Expectations may not be met.

---

### 8. Senior Citizens: High Risk, Low Volume
- **SeniorCitizen = 1** → **59.31%** predicted churn  
- **SeniorCitizen = 0** → **33.00%** predicted churn  
- Yet younger customers contribute **78.98%** of total expected churn.
- This reframes targeting logic and volume can be just as risky as rate.

---

### 9. No Partner / No Dependents = Elevated Risk
- **No Partner** → **49.32%** predicted churn  
- **No Dependents** → **45.34%** predicted churn  
- These groups contribute **64.02%** and **81.80%** of total expected churn, respectively.
- These customers are less anchored and more mobile so relationship status is a meaningful signal.

---

### 10. DSL & Mailed Check Users: Relative Stability
- **DSL users** → **32.81%** predicted churn  
- **Mailed check** → **32.02%** predicted churn  
- These segments show lower churn probabilities. They’re not immune, but they’re more stable than their counterparts.

---

### 11. Retention Simulation Shows Clear Financial Leverage
- At a 50% churn reduction rate:
  - **Medium Risk**: 2.1M at risk → 1.0M retained  
  - **Low Risk**: 932.9k at risk → 466.4k retained  
  - **High Risk**: 285.2k at risk → 142.6k retained
- Medium Risk offers the highest ROI. This is where strategic investment yields the biggest savings.

---

### 12. New Customers: Silent Risk, Early Opportunity
- Only **11 new customers** appear in the latest snapshot, and none have churned yet.
- But this is a fragile window and early drop-off often happens silently.
- Tenure = 0 is a critical engagement phase that must be monitored closely.

---

### ⚠️ Strategic Insight: Volume Can Be Just as Risky as Rate
- Some segments churn more often (e.g. senior citizens), but others churn in larger numbers (e.g. younger customers, month-to-month contracts).
- This reframes how we think about risk. It’s not just about probability, it’s about impact.

---

<a id="recommendations"></a>  
## ✅ Recommendations

These actions target the highest-risk segments identified in the churn analysis. Estimated impact is based on retention simulation and segment-level churn probabilities, reflecting how much churn could be reduced if targeted interventions succeed.

| Segment | Recommended Action | Estimated Impact |
|--------|---------------------|------------------|
| **12+ month tenure + month-to-month contracts** | Flag for proactive retention outreach | ↓ churn by 2–3% |
| **Month-to-month contracts** | Incentivize upgrades to longer terms | ↓ churn by 4–6% |
| **Electronic check users** | Promote auto-pay and flag for outreach | ↓ churn by 5–7% |
| **No support services** | Bundle TechSupport & OnlineSecurity during onboarding | ↓ churn by 3–5% |
| **Fiber optic users** | Audit onboarding, pricing, and satisfaction flows | ↓ churn by 2–4% |
| **Seniors & singles** | Personalized retention flows and check-ins | ↓ churn by 2–4% |
| **Multi-service adoption** | Use as a retention KPI and upsell anchor | ↓ churn by 3–5% |
| **New customers** | Add onboarding tracking and activation nudges | ↓ early drop-off |

<a id="client-scenario"></a>  
## 🧩 Client Scenario: Applying the Recommendations

A CEO opens the churn dashboard and sees **3.29M in revenue at risk**. Instead of guessing, they act with precision:

### 🎯 Goal: Retain High-Value Customers Before They Churn

1. **Upgrade Contracts for Long-Tenure Customers on Month-to-Month**  
   These are high-value relationships at risk. Loyalty without commitment is fragile so contract upgrade incentives are deployed immediately.

2. **Target Month-to-Month + Electronic Check Users**  
   This segment drives the bulk of churn. A retention campaign rolls out with auto-pay nudges and personalized outreach.

3. **Embed TechSupport + OnlineSecurity in Onboarding**  
   These features anchor loyalty. Their absence correlates with high churn so they’re offered early and prominently.

4. **Flag Fiber optic users with High Charges + Low Tenure**  
   Premium expectations aren’t being met. Satisfaction outreach helps diagnose and resolve early friction.

5. **Personalize Messaging for Seniors and Singles**  
   These customers are more mobile and less anchored. Retention flows are tailored to their needs and behaviors.

6. **Track Multi-Service Adoption as a Loyalty Signal**  
   More services mean more stickiness. This metric guides upsell campaigns and onboarding nudges.

7. **Monitor New Customer Activation (Tenure = 0) prevent silent drop-off**  
   Tenure = 0 is a fragile phase. Onboarding flows are enhanced to boost early engagement and reduce first-month churn

---

<a id="who-can-use-this-project"></a>
## 👥 Who Can Use This Project?

1. **Business Leaders / Founders**  
Make fast, strategic decisions on customer retention, revenue risk, and loyalty gaps.

2. **Customer Success & Retention Teams**  
Identify at-risk segments, prioritize outreach, and design targeted retention flows.

3. **Product Managers**  
Spot loyalty gaps, refine onboarding flows, and align product features with retention signals.

4. **Data Analysts / Consultants**  
Practice predictive modeling, segmentation, and interpretability in a real-world business context.

5. **Learners / Students**  
Explore how data science powers customer strategy from churn prediction to financial impact.

---

<a id="tech-stack"></a>
## ⚙️ Tech Stack

| Tool / Platform         | Purpose                                                                 |
|--------------------------|-------------------------------------------------------------------------|
| **Python**               | Data cleaning, feature engineering, EDA, correlation and predictive modeling        |
| **Kaggle Notebook**      | End-to-end workflow with code, analysis, and documentation              |
| **DBT (Data Build Tool)**| Transforms raw tables into enriched views for interpretability and segmentation |
| **PostgreSQL (Supabase)**| Cloud-hosted warehouse for storing snapshots, predictions, and customer data |
| **Metabase (Fly.io)**             | Cloud-hosted Interactive dashboard visuals for churn insights and retention strategy |
| **n8n**                  | Workflow automation—triggers scripts, syncs data, and orchestrates tasks across tools |

---

<a id="workflow"></a>
## 🔄 Workflow

### Automated Churn Prediction Flow (Simulated via n8n)

This project demonstrates how lean teams can automate churn prediction using free, open-source tools. It assumes a daily CSV drop into a shared folder with consistent schema.

> **While this runs manually for now, it’s architected for full automation via n8n.**  
> Airflow suits large-scale data engineering; n8n offers lightweight orchestration ideal for fast, interpretable workflows.

**Raw Data** → [Kaggle Dataset: Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  

| Step | Tool | Action | Trigger |
|------|------|--------|---------|
| 1. Data Dump | Shared Folder | New CSV added | Manual or external |
| 2. File Detection | n8n | Check for new file | Daily at 6 AM |
| 3. Schema Validation | Python | Validate column structure | If file is found |
| 4. Prediction | Python | Clean data + predict churn | If schema matches |
| 5. Ingestion | Python + Supabase | Append to PostgreSQL | Embedded in script |
| 6. View Refresh | DBT | Update views | Auto after ingestion |
| 7. Dashboard Update | Metabase | Auto Refresh Dashboard | Daily at 7 AM |

**n8n Demo Workflow**
![n8n Demo Workflow](https://github.com/Wilfrida-Were/Telco-Churn-Predictive-Analysis/blob/main/n8n%20Telco%20Churn%20Prediction%20demo.jpeg?raw=true)

<a id="lets-connect"></a>
## 🔗 Let’s Connect

Feel free to connect, follow, or support:  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://linkedin.com/in/wilfridawere/)  

[![Website](https://img.shields.io/badge/Website-Visit-orange?style=flat&logo=google-chrome)](https://www.wilfridawere.com/)  

[![Kaggle](https://img.shields.io/badge/Kaggle-Follow-blue?style=flat&logo=kaggle)](https://kaggle.com/wilfridawere)  

[![GitHub](https://img.shields.io/badge/GitHub-Projects-black?style=flat&logo=github)](https://github.com/Wilfrida-Were)  
