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






# Inventory Optimization Recommendations & Implementation Plan

## 1. Forecasting & Procurement Improvements
**a) Implement Tiered Forecasting Approach:**
- **Stable products (P0014 Toys):** Use traditional time-series forecasting (ARIMA/ETS)
- **Volatile products (P0011 Electronics):** Deploy ML models with external signals (social trends, weather)
- **Perishables (P0016 Groceries):** Short-term probabilistic forecasting (Monte Carlo simulations)

**Expected Impact:** Reduce overstock by 25-30% and understock by 40% within 6 months

**b) Dynamic Safety Stock Adjustment:**
- Formula: `Safety Stock = Z-score × √(Lead Time × Demand Variability)`
- Apply higher Z-scores for volatile categories (Clothing: 2.5 vs Furniture: 1.5)

## **2. Operational Execution**
**a) Category-Specific Replenishment Rules:**
| Category | Strategy | Order Frequency | Target Service Level |
|----------|----------|-----------------|----------------------|
| Furniture | Reduce order size by 25% | Bi-monthly | 92% |
| Electronics | Real-time demand tracking | Weekly | 95% |
| Groceries | JIT with VMI | Daily | 90% |

**b) Automated Replenishment Triggers:**
- When stock < (Lead Time Demand + Safety Stock) × 1.2 → Auto-PO
- Exception: Perishables use (Lead Time Demand × 0.8) to prevent spoilage

## **3. Performance Monitoring**
**a) KPIs to Track Monthly:**
1. Overstock Ratio = (Excess Inventory/Total Inventory) → Target <15%
2. Stockout Rate = (Unfulfilled Orders/Total Demand) → Target <5%
3. Inventory Turnover → Improve by 1.5x current

**b) Alert Mechanism:**
- Red flag when:
  - Overstock >30% for 2 consecutive weeks
  - Stockout rate >8% for any top-20 SKU

## **4. Organizational Alignment**
**a) Cross-Functional Workflow:**
1. **Planning:** Provides 13-week demand forecast
2. **Procurement:** Confirms supplier capacity
3. **Finance:** Approves working capital allocation
4. **Stores:** Provides sell-through feedback

**b) Incentive Structure:**
- Reward buyers for hitting both:
  - Inventory turnover targets (60% weight)
  - Service level goals (40% weight)

## **Implementation Roadmap**
| Quarter | Initiative | Success Metric |
|---------|------------|----------------|
| Q1 | Pilot ML forecasting for Electronics | 20% reduction in stockouts |
| Q2 | Roll out dynamic safety stock rules | 15% decrease in overstock |
| Q3 | Full VMI implementation for Groceries | 30% less waste |
| Q4 | Enterprise dashboard deployment | 100% adoption by planners |

**Expected Business Outcomes:**
- 18-22% reduction in carrying costs
- 12-15% improvement in full-price sell-through
- 5-8% increase in GMROI (Gross Margin Return on Inventory)

