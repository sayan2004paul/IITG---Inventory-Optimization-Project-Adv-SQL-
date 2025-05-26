                                                # Low Inventory Detection & Reorder Point Estimation - Insights & Recommendations


### **1\. Executive Summary**

This analysis was conducted to assess the current state of inventory across stores, detect low-inventory risks, and establish a data-driven framework for replenishment. Using a series of targeted SQL queries on the final\_fact table, key metrics were extracted such as current inventory levels, reorder points, average daily demand, and demand variability. The findings uncover critical inefficiencies in stock allocation and suggest corrective actions rooted in retail inventory best practices.

### **2\. Problem Statement**

Retail and supply chain operations are increasingly vulnerable to inventory mismanagement due to static replenishment models and reactive planning. The objective here is to proactively identify SKUs at risk of stockout, quantify demand patterns, and dynamically calculate reorder points and safety stock buffers. The analysis is tailored to support real-time inventory optimization for a multi-store retail network, leveraging historical demand data and variability to inform replenishment strategies.

### **3\. Current Inventory Health by Store**

An initial evaluation of the most recent inventory snapshot was conducted to understand how inventory is distributed across stores. Each store revealed an uneven allocation of SKUs, with some products overstocked while others are critically understocked:

*   **Store 1:** Highest – p0002, Lowest – p0018
    
*   **Store 2:** Highest – p0015, Lowest – p0004
    
*   **Store 3:** Highest – p0013, Lowest – p0008
    
*   **Store 4:** Highest – p0010, Lowest – p0009
    
*   **Store 5:** Highest – p0006, Lowest – p0007
    

These disparities highlight the need for dynamic stock balancing and store-specific demand forecasting to prevent missed sales opportunities due to uneven availability.

### **4\. Static Reorder Threshold Detection**

To flag SKUs with dangerously low stock, a static threshold model was applied where products with inventory levels below 30% of a baseline average (set at 256 units) were identified. SKU p0007, with an inventory level of 59 units, emerged as a key concern. While this approach provides a quick diagnostic tool, it does not adapt to demand fluctuations and may trigger premature or delayed reorder actions.

### **5\. Dynamic Reorder Point Calculation**

To improve accuracy, reorder points were dynamically calculated using the formula:

Reorder Point=Average Daily Demand×Lead Time (7 days)\\text{Reorder Point} = \\text{Average Daily Demand} \\times \\text{Lead Time (7 days)}

This method uses rolling 30-day sales data to compute SKU-specific average daily demand, enabling more precise reorder planning. Key findings include:

*   **SKU p0009** has the highest average daily demand and consequently the highest reorder point.
    
*   **SKU p0012** shows the lowest demand and reorder requirement.
    
*   **SKU p0007**, with the second-highest demand, has critically low inventory, indicating immediate replenishment need.
    

This logic aligns with industry best practices where reorder levels are sensitive to demand volume and supply timelines.

### **6\. Inventory vs. Dynamic Reorder Points**

Next, a comparison between current inventory levels and the dynamically calculated reorder points was performed. Alarmingly, **all SKUs** were found to have inventory levels below their reorder thresholds. This signifies a systemic issue in inventory planning—either due to delayed replenishment cycles, inaccurate demand forecasting, or rigid inventory policies.

Left unaddressed, this could result in widespread stockouts, missed sales, and diminished customer satisfaction. It indicates a pressing need to integrate demand-driven logic into the inventory control process.

### **7\. Demand Variability and Safety Stock**

To account for demand uncertainty, standard deviation of daily demand per SKU was calculated over the same 30-day window. This variability metric is essential for determining the **safety stock**, which acts as a buffer during demand surges or supplier delays.

*   **SKU p0010** displayed the highest variability, implying high demand unpredictability. Recommended safety stock: **1408 units**.
    
*   **SKU p0004** had the lowest variability, suggesting stable demand patterns. Recommended safety stock: **781 units**.
    

These findings are crucial for adjusting reorder points upward to avoid frequent stockouts for high-volatility SKUs.

### **8\. Risk Zones and Prioritization**

A key risk zone was identified around **SKU p0007**, which has one of the highest average daily demands but the lowest current inventory. Combined with high demand frequency, this SKU represents a critical bottleneck in the supply chain. Similarly, p0009, while having the highest reorder point, also faces shortfall risks.

These SKUs should be prioritized for immediate restocking, and suppliers should be alerted to increase replenishment frequency or expedite lead times.

### **9\. Implications for Multi-Store Inventory Planning**

The inconsistencies in SKU distribution across stores (e.g., overstocked products in some stores while understocked in others) suggest a lack of synchronized inventory control. Inter-store transfers or redistribution strategies can be leveraged to balance stock without incurring new procurement costs.

Moreover, demand patterns likely vary across locations. Store-specific forecasting models should be developed to ensure inventory is aligned with actual consumption trends.

### **10\. Recommendations**

Based on the findings, the following actions are recommended:

*   **Adopt dynamic reorder point models** based on moving average demand and SKU-level lead time.
    
*   **Integrate safety stock buffers** using standard deviation-based calculations.
    
*   **Automate stock risk detection** through real-time dashboards with alerts for low-stock SKUs.
    
*   **Enable SKU-level and store-level forecasting** using granular sales and seasonality data.
    
*   **Balance inventory** across stores through transfer strategies before initiating new purchase orders.
    
*   **Monitor supplier lead time variability** to adjust reorder logic accordingly.
    

### **11\. KPI Framework for Ongoing Monitoring**

To track and optimize inventory operations, the following KPIs should be integrated into ongoing reporting:

KPIPurposeInventory Turnover RatioMeasures stock utilization efficiencyDays of Inventory on HandEstimates how long current inventory lastsStockout Rate per SKUIndicates service level and riskForecast Accuracy (MAPE)Validates demand prediction modelsLead Time ReliabilityEvaluates supplier performance

