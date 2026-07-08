# E-Commerce Customer Retention & Segmentation Analysis

## Project Overview
End-to-end customer analytics on 541,909 real transactions from a UK-based 
online retailer — combining RFM segmentation, cohort retention analysis, and 
revenue concentration to identify where the business is losing customers and 
what to do about it.

**Tools:** Python, Pandas, Matplotlib, Seaborn
**Dataset:** UCI Online Retail Dataset (Kaggle)
**Records analysed:** 397,924 (after cleaning)
**Total revenue analysed:** £8,911,407

---

## Business Problem
Three questions drive this analysis:
1. Which customers are most valuable and how do we protect them?
2. How well does the business retain customers over time?
3. Where is the biggest revenue opportunity?

---

## Data Cleaning
Starting with 541,909 rows:
- Removed 135,080 rows with missing CustomerID (unidentifiable customers)
- Removed 10,624 rows with negative quantities (returns)
- Removed 9,288 cancelled orders (InvoiceNo starting with 'C')
- Removed zero-price items
- Created Revenue column: Quantity × UnitPrice
- Created InvoiceMonth column for cohort analysis

**Clean dataset: 397,924 rows across 4,338 unique customers**

---

## Part 1: Cohort Retention Analysis

### Methodology
Every customer was assigned to a cohort based on their first purchase month.
Retention rate = % of that cohort who returned in subsequent months.

### Key Findings

**Finding 1: 80% of customers never return after their first purchase**
Month 1 average retention is only 20.6%. This is the single biggest 
revenue leak in the business — 4 in 5 customers buy once and disappear.

**Finding 2: Customers who survive month 1 stay for 12+ months**
Retention stabilises at 20-25% from month 2 onwards. Customers who 
return once tend to keep returning — making month 1 conversion the 
highest-leverage intervention available.

**Finding 3: December 2010 cohort shows best long-term retention (50% at month 12)**
Christmas/seasonal buyers show significantly higher loyalty than other 
monthly cohorts — suggesting gifting behaviour or seasonal promotions 
drive stronger customer relationships.

### Cohort Recommendations

**1. First-purchase follow-up sequence (highest priority)**
Improving month 1 retention from 20% to 30% would add thousands of 
returning customers annually. Recommended action: personalised email 
at day 3, day 7, and day 14 post-purchase with a second-purchase 
incentive (free shipping or 10% discount).

**2. Focus retention budget on first 30 days only**
Customers who don't return in month 1 rarely return at all. 
Recommended action: reallocate re-engagement spend from lapsed 
customers toward new-to-second-purchase conversion — significantly 
higher ROI.

**3. Replicate December cohort conditions year-round**
Analyse what drove December cohort loyalty — product mix, gifting 
behaviour, or seasonal promotions — and replicate those conditions 
in other months to raise baseline retention.

---

## Part 2: RFM Customer Segmentation

### Methodology
Every customer was scored 1-5 on three dimensions:
- **Recency** — how many days since their last purchase
- **Frequency** — how many times they purchased
- **Monetary** — total £ spent

Customers were segmented into 6 groups: Champion, Loyal, At Risk, 
Potential, New Customer, Lost

### Customer Segments

| Segment | Customers | Revenue | % of Total Revenue |
|---|---|---|---|
| Champion | 962 | £5,809,341 | 65.2% |
| Loyal | 998 | £1,474,128 | 16.5% |
| At Risk | 643 | £800,532 | 9.0% |
| Lost | 1,065 | £519,409 | 5.8% |
| Potential | 351 | £161,833 | 1.8% |
| New Customer | 320 | £146,167 | 1.6% |

### Key Findings

- **Champions (22% of customers) generate 65.2% of total revenue (£5.8M)**
- 643 At Risk customers represent £800,532 in revenue at immediate risk
- 1,065 Lost customers — the largest segment by count
- Only 320 new customers (7%) — acquisition funnel is critically weak
- Average customer bought 4.27 times and spent £2,053 total

### RFM Recommendations

**1. Win-back campaign for At Risk customers (immediate priority)**
643 customers representing £800,532 showing early churn signals.
Recommended action: personalised email campaign with time-limited 
discount (10-15%) within 30 days. Recovering 30% would retain 
~£240,000 in revenue.

**2. VIP programme for Champions**
962 customers generate 65% of all revenue (£5.8M). Losing even 10% 
would cost £580,000. Recommended action: introduce a VIP tier — 
early access, free shipping, exclusive offers. Cost is low; 
risk of not doing it is enormous.

**3. Referral programme targeting Champions**
New customers are only 7% of the base — acquisition is critically weak.
Recommended action: incentivise Champions to refer friends with store 
credit or discounts. Referral programmes convert at 3-5x higher than 
cold acquisition channels.

**4. Investigate Lost customers before spending on re-acquisition**
1,065 customers left — understand why before spending budget on 
win-back. Recommended action: analyse Lost customers' last purchases 
— was it price, product quality, or experience?

**5. Improve new customer onboarding**
Only 320 new customers in this period. Those who do join need a 
strong first experience. Recommended action: welcome sequence — 
first purchase discount, product recommendations, follow-up at 
day 7 and day 30.

---

## Project Structure
- `ecommerce-rfm-analysis.ipynb` — full analysis notebook
- `cohort_retention_heatmap.png` — monthly cohort retention heatmap
- `avg_retention_curve.png` — average retention curve by month
- `customer_segments.png` — customer count by segment
- `revenue_by_segment.png` — revenue distribution by segment

---

## Skills Demonstrated
- Data cleaning and preparation (Pandas)
- Cohort retention analysis
- RFM customer segmentation
- Data visualisation (Matplotlib, Seaborn)
- Business recommendations with quantified £ impact
- Product analytics thinking — retention, acquisition, revenue concentration
- Python (Google Colab)
