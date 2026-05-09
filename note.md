## Methodology

- Loaded the `sales_data_sample.csv` dataset using pandas and performed initial data inspection
- Checked dataset structure, data types, missing values, and verified overall data quality
- Converted `ORDERDATE` column into datetime format for accurate time-based customer analysis
- Defined a reference date using the latest transaction date plus one day (`2005-06-01`) for Recency calculation
- Created RFM metrics at the customer level using `groupby()` aggregation:
  - **Recency** → Days since last purchase
  - **Frequency** → Number of unique orders
  - **Monetary** → Total sales amount generated
- Built a complete RFM table for 92 unique customers
- Used `pd.qcut()` to generate quantile-based RFM scores ranging from 1–4
- Applied reverse scoring for Recency where lower recency values receive higher scores
- Created combined `RFM_Segment` codes by concatenating Recency, Frequency, and Monetary scores
- Developed a rule-based customer segmentation system including:
  - Champions
  - Loyal Customers
  - At Risk
  - Needs Attention
  - Lost Customers
- Performed customer profiling analysis to understand purchasing behavior across segments
- Created multiple visualizations including:
  - Segment distribution bar charts
  - Recency vs Monetary scatter plots
  - Heatmaps of average RFM metrics
  - 3D customer segmentation analysis
- Exported the final customer segmentation report for business usage and marketing strategy planning

---

## RFM Scoring Logic

### Recency Scoring
Recency measures how recently a customer made a purchase.

- Customers with recent purchases are more likely to engage again
- Lower recency values indicate higher engagement
- Reverse scoring was applied:
  - **4 = Most recent customers**
  - **1 = Least recent customers**

### Frequency Scoring
Frequency measures how often a customer places orders.

- Customers with frequent purchases are considered more loyal
- Higher order counts receive higher scores:
  - **4 = Highest purchase frequency**
  - **1 = Lowest purchase frequency**

### Monetary Scoring
Monetary measures total customer spending.

- High-spending customers generate the most business value
- Customers with larger total sales receive higher scores:
  - **4 = Highest spending customers**
  - **1 = Lowest spending customers**

### RFM Segment Code
The final RFM segment was created by combining all three scores.

Example:
- `444` → Best customers across all metrics
- `111` → Lowest engagement and spending customers

---

## Business Insights

### High-Value Customer Concentration
A small portion of customers contributes a significant share of total revenue.

- Champions alone contribute approximately **28% of total sales**
- These customers represent the company's most valuable customer base

→ Retaining high-value customers should be a top business priority.

---

### Customer Activity Distribution
Customer engagement levels vary significantly across the dataset.

- Recency ranges from **1 day to 532 days**
- Frequency ranges from **1 to 43 orders**
- Monetary value ranges from approximately **$482 to $276K**

→ This variation highlights the importance of customer segmentation for targeted marketing strategies.

---

### At-Risk Customer Detection
Several customers previously demonstrated strong purchasing behavior but became inactive.

- At Risk customers typically have:
  - Low Recency scores
  - High Frequency and Monetary scores

→ Re-engagement campaigns can help recover valuable customers before complete churn occurs.

---

### Lost Customer Segment
A noticeable portion of customers fall into the Lost category.

- Lost customers generally show:
  - Low purchase frequency
  - Low spending
  - Long inactivity periods

→ Reactivation campaigns and promotional offers may help recover some inactive customers.

---

### Loyal Customer Potential
Loyal customers consistently interact with the business and generate stable revenue.

→ Personalized communication, loyalty rewards, and upselling strategies can increase customer lifetime value.

---

## Segment Actions and Marketing Recommendations

### Champions
**Customer Behavior:**
Highly engaged customers with recent purchases, strong spending behavior, and frequent transactions.

**Recommended Actions:**
- Offer VIP loyalty programs
- Provide early access to new products
- Launch referral and ambassador campaigns
- Deliver personalized premium experiences

---

### Loyal Customers
**Customer Behavior:**
Consistent and reliable customers with healthy purchasing activity.

**Recommended Actions:**
- Cross-sell and upsell related products
- Send personalized product recommendations
- Provide loyalty discounts and rewards
- Encourage repeat purchases through email campaigns

---

### At Risk
**Customer Behavior:**
Previously valuable customers who have become inactive recently.

**Recommended Actions:**
- Run win-back campaigns
- Offer limited-time discounts
- Send personalized reactivation emails
- Highlight newly launched products or services

---

### Needs Attention
**Customer Behavior:**
Moderately active customers showing signs of declining engagement.

**Recommended Actions:**
- Increase engagement through targeted promotions
- Offer special incentives for repeat purchases
- Use reminder campaigns and personalized communication
- Monitor future activity closely

---

### Lost Customers
**Customer Behavior:**
Inactive customers with low purchasing activity and minimal spending.

**Recommended Actions:**
- Launch reactivation campaigns
- Offer aggressive promotional discounts
- Conduct customer feedback surveys
- Reduce marketing spend if reactivation attempts fail
```
