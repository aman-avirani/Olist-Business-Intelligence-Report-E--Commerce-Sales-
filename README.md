# Olist E-Commerce Business Intelligence Dashboard

## Overview:
A 5-page Power BI dashboard analyzing -> 100K orders from Olist, a Brazilian 
e-commerce marketplace, covering the period Sept 2016 – Oct 2018. Built to 
answer the questions a marketplace analyst/BI team would actually ask: 
growth drivers, customer retention, delivery performance, and seller 
concentration risk.

## Dataset:
Olist Brazilian E-Commerce Public Dataset (Kaggle) — 9 relational tables 
covering orders, payments, reviews, products, customers, geolocation and sellers.

## Tools & Tech Used:
Power BI · Power Query (M) · DAX

## Pages
1. **Overview** — Headline KPIs: Revenue, Orders, AOV, SLA Adherence*, CSAT**
2. **Growth & Category Performance** — YoY trends, category revenue, payment mix
3. **Customer Analytics** — Repeat purchase rate, city/state revenue distribution
4. **Logistics & Fulfillment** — SLA adherence by state, delivery performance
5. **Seller / Marketplace Health** — Seller concentration, leaderboard, growth

* SLA — Service Level Agreement
  A promised standard of performance — in this context, the delivery timeline a company commits
  
**CSAT — Customer Satisfaction (Score)
  A standard measure of how happy customers are with their experience.

## Key Insights
 1.Revenue grew from $6.2M (2017) to $7.4M (2018) despite 2018 data being incomplete (cuts off mid-October) — indicating stronger underlying growth than the raw YoY figure suggests once annualized.
 
2. The Black Friday spike (Nov 2017) drove a simultaneous surge in both revenue and order volume — confirming it's a genuine demand event, not a data anomaly, since both metrics moved together rather than one being a single inflated transaction.

3.Only 3.1% of customers are repeat buyers (3.0K of 96K), signaling this is an acquisition-driven marketplace, not a retention-driven one — a strategic flag for where growth investment should go.

4. Revenue is heavily geographically concentrated — São Paulo alone drives ~38% of total revenue ($5.2M of $13.6M), with the top 3 states (SP, RJ, MG) accounting for the majority of GMV.

5. A clear SLA-to-region gap exists: top-performing states hit ~97% SLA adherence, while the bottom states (AL, MA, SE) sit as low as 78.6% — nearly a 20-point gap, pointing to specific regional logistics bottlenecks worth investigating.

6. Credit card dominates payment behavior at 78.3% share, with boleto (a Brazilian bank-slip payment method) at 17.9% — relevant context if benchmarking against markets like India where UPI/EMI patterns differ.

7. Seller base grew nearly 10x over the observed window (low single digits to 383 peak active sellers), showing healthy marketplace supply-side expansion.

8. Top 10 sellers account for 13.1% of total GMV — a moderate, not extreme, concentration risk, but worth monitoring as the marketplace scales.

9. Overall SLA adherence sits at 93.2%, with a -3.08 point YoY decline — worth flagging as a trend to watch even though the absolute number is still strong.

## Data Modeling Notes
- Star schema with a dedicated Date dimension table, marked and related via 
  active/inactive relationships (order purchase, delivery, and due dates)
  
- Handled known dataset quirks: role-playing date dimensions, split-payment 
  transactions (multiple rows per order_id by design), category name 
  translation via merge, geolocation many-to-many resolved via grouping

  # Screenshot of how KPI Dashboard Looks:
  https://github.com/aman-avirani/Olist-Business-Intelligence-Report-E--Commerce-Sales-/blob/ab-0017/Olist_BI_Report.png
