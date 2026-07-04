# E-Commerce Customer Segmentation & RFM Analysis

## Project Overview
Analysis of 541,909 real transactions from a UK-based online retailer to identify 
customer segments, revenue concentration, and retention opportunities using RFM 
(Recency, Frequency, Monetary) analysis.

**Tools:** Python, Pandas, Matplotlib
**Dataset:** UCI Online Retail Dataset (Kaggle)
**Records analysed:** 397,924 (after cleaning)
**Total revenue analysed:** £8,911,407

---

## Business Problem
Which customers are most valuable? Which are about to churn? 
And what should the business do about it?

---

## Data Cleaning
Starting with 541,909 rows, the following were removed to ensure data quality:
- 135,080 rows with missing CustomerID (unidentifiable customers)
- 10,624 rows with negative quantities (returns)
- 9,288 cancelled orders (InvoiceNo starting with 'C')
- Created a Revenue column: Quantity × UnitPrice

**Clean dataset: 397,924 rows across 4,338 unique customers**

---

## Methodology: RFM Analysis
Every customer was scored on three dimensions:

- **Recency** — how many days since their last purchase
- **Frequency** — how many times they purchased
- **Monetary** — total £ spent

Customers were then segmented into 6 groups:
Champion, Loyal, At Risk, Potential, New Customer, Lost

---

## Key Findings

- **Champions (22% of customers) generate 65.2% of total revenue (£5.8M)**
- 643 At Risk customers represent £800,532 in revenue at immediate risk
- 1,065 Lost customers — the largest segment by count
- Only 320 new customers (7%) — acquisition funnel is weak
- Average customer bought 4.27 times and spent £2,053 total

---

## Customer Segments

| Segment | Customers | Revenue | % of Total Revenue |
|---|---|---|---|
| Champion | 962 | £5,809,341 | 65.2% |
| Loyal | 998 | £1,474,128 | 16.5% |
| At Risk | 643 | £800,532 | 9.0% |
| Lost | 1,065 | £519,409 | 5.8% |
| Potential | 351 | £161,833 | 1.8% |
| New Customer | 320 | £146,167 | 1.6% |

---

## Business Recommendations

**1. Launch a win-back campaign for At Risk customers (immediate priority)**
643 customers representing £800,532 are showing early churn signals — 
they used to buy frequently but haven't returned recently. 
Recommended action: personalised email campaign with a time-limited 
discount (10-15%) within the next 30 days. Even recovering 30% of these 
customers would retain ~£240,000 in revenue.

**2. Protect the Champion base with a VIP programme**
962 customers generate 65% of all revenue (£5.8M). Losing even 10% of 
Champions would cost £580,000. Recommended action: introduce a VIP tier — 
early access to new products, free shipping, exclusive offers. 
Cost is low; risk of not doing it is enormous.

**3. Launch a referral programme targeting Champions**
New customers are only 7% of the base — acquisition is weak. Champions 
already love the product and have high trust. Recommended action: 
incentivise Champions to refer friends with store credit or discounts. 
Referral programmes typically convert at 3-5x higher than cold acquisition.

**4. Investigate why 1,065 customers are Lost**
Before spending on re-acquisition, understand why they left. 
Recommended action: exit survey or analysis of Lost customers' last 
purchases — was it price, product quality, or a bad experience? 
Fix the root cause before spending budget on win-back.

**5. Improve new customer onboarding**
Only 320 new customers in this period signals weak acquisition. 
Those who do join need a strong first experience to become Loyal or Champion. 
Recommended action: introduce a welcome sequence — first purchase discount, 
product recommendations, follow-up email at day 7 and day 30.

---

## Project Structure
- `ecommerce-rfm-analysis.ipynb` — full analysis notebook
- `customer_segments.png` — customer count by segment
- `revenue_by_segment.png` — revenue distribution by segment

---

## Skills Demonstrated
- Data cleaning and preparation (Pandas)
- Customer segmentation (RFM Analysis)
- Data visualisation (Matplotlib)
- Business recommendations from data insights
- Python (Google Colab)
