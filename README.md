# RFM Customer Segmentation Analysis

## 📌 Project Overview

This project performs a complete RFM (Recency, Frequency, Monetary) customer segmentation analysis using transactional sales data to identify valuable customer groups, understand purchasing behavior, and generate business-focused marketing strategies.

The analysis was built using rule-based RFM modeling techniques commonly used in CRM, customer analytics, and retention marketing.

The dataset contains customer transaction records including:
- Order information
- Sales values
- Order dates
- Customer names
- Product and deal details

The main objective is to identify:

- High-value customers
- Loyal and repeat customers
- At-risk customers likely to churn
- Lost customers requiring reactivation
- Customer spending and engagement patterns

---

# Data Preparation

The following preprocessing steps were applied:

- Loaded the `sales_data_sample.csv` dataset using pandas
- Inspected dataset structure, data types, and missing values
- Converted `ORDERDATE` column into datetime format
- Created a reference date for Recency calculation (`2005-06-01`)
- Verified dataset consistency before customer-level aggregation
- Prepared a clean transactional dataset for RFM analysis

---

# 📊 RFM Analysis

The project calculates three key customer metrics:

### Recency
Measures how recently a customer made a purchase.

- Lower recency values indicate more active customers
- Customers with recent purchases are generally more engaged

### Frequency
Measures how often a customer places orders.

- Higher frequency indicates stronger customer loyalty
- Frequent buyers are more likely to generate recurring revenue

### Monetary
Measures total customer spending.

- High monetary values identify the most profitable customers
- Spending behavior helps prioritize retention efforts

---

# 🧮 RFM Scoring System

Quantile-based scoring was applied using `pd.qcut()`.

### Scoring Logic

| Metric | Score Meaning |
|---|---|
| Recency | 4 = Most Recent Customers |
| Frequency | 4 = Highest Purchase Frequency |
| Monetary | 4 = Highest Spending Customers |

Recency scoring was reversed because customers with more recent purchases are considered more valuable.

Each customer received:
- `R_Score`
- `F_Score`
- `M_Score`

The scores were combined into a final `RFM_Segment` code.

Example:
- `444` → Best customers
- `111` → Lowest-value customers

---

# 👥 Customer Segmentation

Customers were grouped into business-focused segments including:

- Champions
- Loyal Customers
- At Risk
- Needs Attention
- Lost Customers

The segmentation framework helps businesses create personalized marketing and retention strategies.

---

# 📈 Key Business Insights

### Champions Drive Significant Revenue
Top-performing customers contribute a disproportionately large share of total sales.

- Champions account for approximately **28% of total revenue**
- These customers represent the highest-value segment

→ Retaining Champions is critical for long-term profitability.

---

### Customer Engagement Varies Significantly
Customer purchasing behavior differs across the dataset.

Key RFM statistics include:

- Recency ranges from **1 to 532 days**
- Frequency ranges from **1 to 43 orders**
- Monetary value ranges from approximately **$482 to $276K**

→ Customer segmentation enables more targeted business strategies.

---

### At-Risk Customers Require Immediate Attention
Some customers previously showed strong purchasing behavior but became inactive.

→ Win-back campaigns can help prevent permanent customer churn.

---

### Lost Customers Show Low Engagement
A noticeable portion of customers exhibit:
- Long inactivity periods
- Low order frequency
- Minimal spending behavior

→ Reactivation campaigns may recover a portion of inactive customers.

---

### Loyal Customers Present Growth Opportunities
Loyal customers maintain consistent purchasing patterns.

→ Cross-selling, upselling, and loyalty rewards can increase customer lifetime value.

---

# 📊 Visualizations

The project includes multiple business-focused visualizations:

- Customer segment distribution bar chart
- Recency vs Monetary scatter plot
- Heatmap of average RFM metrics by segment
- 3D customer segmentation visualization

These visualizations help identify behavioral patterns and segment-level differences.

---

# 🎯 Marketing Recommendations

### Champions
- Offer VIP rewards and exclusive benefits
- Launch referral programs
- Provide personalized premium experiences

### Loyal Customers
- Encourage repeat purchases
- Use cross-sell and upsell campaigns
- Deliver personalized product recommendations

### At Risk
- Run win-back campaigns
- Offer limited-time discounts
- Send reactivation emails

### Needs Attention
- Increase engagement through promotions
- Use reminder campaigns and targeted communication

### Lost Customers
- Launch aggressive reactivation offers
- Conduct customer feedback campaigns
- Reduce acquisition costs where recovery is unlikely

---

# 🛠️ Technologies Used

- Python
- pandas
- matplotlib
- seaborn

---

# 🚀 Conclusion

This project demonstrates how RFM analysis can transform raw transactional data into actionable customer intelligence.

The segmentation framework helps businesses:

- Improve customer retention
- Identify high-value customers
- Reduce churn risk
- Personalize marketing strategies
- Increase customer lifetime value
- Optimize CRM and retention campaigns

By combining data analysis with business strategy, companies can make smarter customer-focused decisions and drive sustainable revenue growth.
