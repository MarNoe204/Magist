# Magist Business Analyses
## Assessing Magist as a logistics and fulfillment partner for high-end tech products in Brazil

### **1. Introduction**
Eniac is evaluating **Magist**, an online marketplace, as a potential logistics and fulfillment partner for our **high-end Apple-compatible computer accessories** in Brazil.  
This analysis focuses on two key questions:

1. **Is Magist a good fit for high-end tech products?**  
2. **Are orders delivered on time?**  

Through SQL-based data extraction and Tableau visualizations, we analyzed **product pricing, sales distribution, shipping performance, and customer satisfaction**.

---

### **2. Data & Methodology**
The analysis was conducted using:

- **Magist Dataset** (Orders, Products, Sellers, Payments, Reviews, Shipping, and Geo Data)  
- **SQL Queries** to extract and calculate key performance indicators (KPIs)  
- **Tableau Visualizations** for trend and pattern analysis  

Key calculated metrics include:
- **Revenue breakdown by price category (Ultra Low-Cost → High-End)**
- **Market share of high-end products**
- **Order fulfillment times vs. industry benchmarks**
- **Customer satisfaction analysis based on delivery & product reviews**

---

### **3. Findings & Insights**

#### **Market Fit for High-End Tech Products**
| Price Category | Revenue Share (%) | Trend (2016 → 2018) |
|---------------|------------------|---------------------|
| Ultra Low-Cost | ~9% | 📉 Declining |
| Low-Cost | ~34% | 📈 Increasing |
| Mid-Range | ~24% | 📉 Slight Decline |
| Premium | ~22% | 📉 Declining |
| High-End | ~10% | 📈 Increasing |

**High-end tech sales are growing but remain a niche (10% of revenue).**  
**Most revenue (≈75%) comes from affordable products.**  
**Implication:** While there is a market for high-end accessories, Magist primarily serves budget-conscious consumers.

#### **🔹 Shipping & Delivery Performance**
| Region  | Avg. Delivery Time (days) | Tech Products (days) | On-Time Orders (%) |
|---------|--------------------------|----------------------|---------------------|
| Magist  | **12.5** | **12.8** | **92.3%** |
| Brazil  | **10.2** | **10.8** | **93.7%** |
| USA     | **5.1** | **5.8** | **95.1%** |
| Europe  | **3.2** | **3.8** | **97.5%** |
| Germany | **2.5** | **3.0** | **98.2%** |

**92.3% of orders arrive on time, aligning with industry standards.**  
**Delivery times are significantly longer (12.5 days) compared to other markets.**  
**Implication:** Slow delivery might impact customer satisfaction for high-end products.

#### **Customer Satisfaction & Returns**
- **Frequent complaints about incorrect or defective items**
- **Challenges in the return/exchange process**
- **Customers demand better product quality control**

**Implication:** High-end buyers expect superior service. Magist’s return policies & quality control need improvement.

---

### **4. Conclusion: Is Magist a Suitable Partner?**
| Strengths | Weaknesses |
|-------------|--------------|
| Existing tech marketplace with increasing high-end sales | Primarily serves budget-conscious customers |
| Good fulfillment rate (92.3% on-time deliveries) | Longer delivery times (12.5 days vs. global standards) |
| Growing demand for premium tech accessories | Customer dissatisfaction with defective items & returns |
| Established logistics network in Brazil | Limited infrastructure for high-end logistics |

**Final Recommendation:** **Magist has potential**, but Eniac should conduct further analysis on:
- **Shipping optimization (cost & speed)**
- **Customer satisfaction improvements**
- **High-end product positioning strategies**

---

### **5. Next Steps**
- **Conduct A/B testing with select high-end products**  
- **Evaluate alternative logistics partners for premium shipping**  
- **Negotiate better fulfillment terms with Magist**  

*Continuous monitoring is required to ensure Magist can meet Eniac’s quality and service expectations for the Brazilian market.*

---

### **6. How to Reproduce This Analysis**
#### **Requirements**
- **MySQL for querying Magist’s dataset**
- **Tableau for visualization**
- **Python/Pandas (optional) for advanced analysis**

#### **Key SQL Queries**
All queries used for this analysis are available in **`magist_analyses.sql`**. Example:

```sql
-- Calculate revenue share by price category
SELECT year, price_category, 
       SUM(total_revenue) AS revenue, 
       (SUM(total_revenue) / SUM(SUM(total_revenue)) OVER (PARTITION BY year)) * 100 AS revenue_percentage
FROM revenue_analysis
GROUP BY year, price_category
ORDER BY year, revenue_percentage DESC;
```

#### **Tableau Dashboards**
- **Revenue Distribution by Price Category**
- **On-Time vs. Delayed Deliveries**
- **Regional Shipping Performance**
- **Customer Satisfaction & Reviews**

---

### **7. Contact & Contributions**
**Contact:** Martin Nötzel | martin.noetzel@gmail.com |   
**Contributions:** Feel free to submit issues or pull requests if you find ways to refine the analysis.

 *This repository will continue to be updated as new data becomes available!*

---
