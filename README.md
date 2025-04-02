# 🛍️ Optimizing Checkout Upsells: A/B Testing for Product Prompts in E-Commerce

## 📄 Overview

This notebook explores how **displaying an upsell prompt** during the checkout process affects **customer behavior and total order value**. Using **A/B testing**, we compare two user groups:

- **"Show Prompt" group**: Saw a prompt to add a specific product during checkout.
- **"No Prompt" group**: Did not receive any upsell prompt.

The goal is to determine whether prompting customers leads to:

- Higher **product add-to-cart rates**
- Increased **total order value**
- Changes in **conversion or cart abandonment behavior**

---

## 📦 Dataset Information

The dataset simulates user interactions in an online checkout funnel.

### 🔑 Key Features:

| Column Name                   | Description                                                        |
| ----------------------------- | ------------------------------------------------------------------ |
| `Group`                       | Whether the user saw the upsell prompt (Show Prompt vs. No Prompt) |
| `Session_Date`                | Timestamp of the session (hourly granularity)                      |
| `Existing_Cart_Value`         | Total value of products before the prompt                          |
| `Prompted_Product_Price`      | Price of the product in the prompt                                 |
| `Total_Order_Value`           | Final cart value after prompt (if added)                           |
| `Time_Spent_on_Checkout_Page` | Duration on checkout page (seconds)                                |
| `Added_Product`               | Whether the user added the upsell product (0/1)                    |
| `Conversion`                  | Whether the session resulted in a completed purchase               |
| `Device_Type`                 | Desktop, Mobile, or Tablet                                         |
| `Returning_Customer`          | Whether the user is a returning customer                           |

---

## 🧪 Project Workflow

### **1️⃣ Data Cleaning & Preparation**

- Converted timestamps to weekly bins
- Encoded categorical variables
- Handled outliers and skewed distributions
- Created new features for session-level analysis

### **2️⃣ Exploratory Analysis**

- Pairplots, boxplots, and histograms to explore distribution of key metrics
- Analyzed differences in order value, conversion, and upsell rate by group

### **3️⃣ Hypothesis Testing**

- **ANOVA and T-tests** for differences in means
- **Chi-square tests** for categorical behavior (e.g., product added vs. not)
- **Levene’s test** to assess equal variance assumptions

### **4️⃣ Bayesian A/B Testing**

- Bootstrapped Bayesian comparison of Total Order Value
- Simulated posterior distributions to calculate:
  - **Probability that showing the prompt increases value**
  - **95% Confidence Interval of uplift**
  - **Estimated revenue impact of prompt at scale**

---

## 📌 Key Findings

- ✅ **Users shown the upsell prompt are significantly more likely to add the product** to their order.
- ✅ Bayesian analysis shows a **98.25% probability** that the prompt increases **Total Order Value**.
- 💰 **Mean revenue uplift** per prompted user: **$7.74**
- 📊 **95% Confidence Interval**: ($0.60, $14.86)
- 📈 **Estimated total revenue gained from prompt**: **$7,577.46**
- ❌ The upsell prompt **did not negatively affect conversion** or increase cart abandonment.
- 📱 No significant difference in performance across **device types or returning users**.

---

## 📊 Suggested Visualizations

- 📦 **Boxplots and bar charts** of Total Order Value by group
- ⏱️ **Weekly trend line** showing revenue performance over time
- 🧠 **Bayesian uplift distribution plot** with confidence interval
- 📉 **Stacked bar charts** showing conversion vs. prompt exposure

---

## 🚀 Next Steps

- Test **different product types or price ranges** in the upsell
- Run **Bayesian analysis over time** to detect long-term patterns
- Explore **personalized upsell prompts** by user behavior or history
