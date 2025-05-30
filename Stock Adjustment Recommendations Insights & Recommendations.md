# Stock Adjustment Insights: Key Findings :


## 1. Overstocking Risks 

Pattern: Top products (e.g., P0018 Clothing, P0014 Toys) show >50% excess inventory, indicating poor demand forecasting or overly conservative sales projections.

Hidden Issue: Furniture appears twice in top overstocked items, suggesting category-wide procurement misalignment.

Impact: Capital tied up in unsold stock increases holding costs and forces margin-eroding markdowns.

Solution:

Recalibrate safety stock levels using probabilistic forecasting (e.g., Monte Carlo simulations).
Implement dynamic replenishment triggers for high-overstock categories (e.g., reduce order sizes for Furniture by 20–30%).


## 2. Understocking Risks :

Pattern: Products like P0011 (Electronics) and P0016 (Groceries) show >40% demand-supply gaps, reflecting under-ordering due to risk-averse planning.

Hidden Issue: Clothing dominates understocked items, likely due to unaccounted trend volatility or seasonal spikes.

Impact: Lost sales (~43% unmet demand) and customer attrition, especially in high-margin categories (e.g., Electronics).

Solution:

Adopt AI-driven demand sensing (e.g., NLP for trend analysis in Clothing).
For perishables (Groceries), use short-cycle ordering with vendor-managed inventory (VMI).


## 3. Systemic Mismatches 

Root Cause: Binary procurement behavior—over-ordering for stable categories (Furniture), under-ordering for volatile ones (Clothing, Electronics).

Data Signal: No products had orders "significantly higher" than sales in 6 months, implying asymmetric risk aversion (prioritizing overstock prevention over revenue capture).

Unified Fix:

Classify SKUs into 4 quadrants (Stable/Volatile + High/Low Margin) and apply tailored strategies:

Stable + High Margin (e.g., P0014 Toys): Optimize EOQ (Economic Order Quantity).

Volatile + High Margin (e.g., P0011 Electronics): Safety stock + real-time demand tracking.

Perishables (e.g., P0016 Groceries): Just-in-time (JIT) ordering.
