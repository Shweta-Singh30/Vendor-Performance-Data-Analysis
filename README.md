# Vendor Performance Analysis & Inventory Optimization

## 📊 Project Overview
This project analyzes vendor performance, inventory turnover, and profitability metrics to provide actionable insights for optimizing retail and wholesale operations. The analysis identifies underperforming brands, evaluates vendor dependencies, assesses bulk purchasing impacts, and recommends strategies for improving profitability and inventory efficiency.

## 🎯 Business Problem
Effective inventory and sales management are critical for profitability in retail and wholesale. Companies face challenges with:
- Inefficient pricing strategies
- Poor inventory turnover
- Vendor dependency risks
- Profitability variance across vendors

This analysis aims to address these challenges through data-driven insights and recommendations.

## 📁 Dataset Description
The dataset contains 10,692 records with the following key metrics:
- **Vendor Information**: VendorNumber, Brand
- **Financial Metrics**: PurchasePrice, ActualPrice, GrossProfit, ProfitMargin
- **Inventory Metrics**: Volume, TotalPurchaseQuantity, TotalSalesQuantity, StockTurnover
- **Operational Metrics**: FreightCost, TotalExciseTax

### Data Filtering Applied
To ensure reliable insights, the analysis filtered:
- Gross Profit ≤ 0 (exclude loss-making transactions)
- Profit Margin ≤ 0 (focus on profitable operations)
- Total Sales Quantity = 0 (eliminate unsold inventory)

## 🔍 Key Insights

### 1. Brand Performance Optimization
- Identified **198 brands** with low sales but high profit margins (60-90%)
- Opportunity for targeted marketing and pricing adjustments to boost volume

### 2. Vendor Dependency Analysis
- **Top 10 vendors** contribute 65.69% of total purchases
- High dependency creates supply chain risks requiring diversification

### 3. Bulk Purchasing Impact
- **72% lower unit costs** for bulk orders ($10.78 vs. $39.06 per unit)
- Strategic advantage in encouraging larger orders

### 4. Inventory Turnover Issues
- **$2.71M** tied up in unsold inventory
- Identified vendors with low stock turnover (0.61-0.82) requiring management

### 5. Profit Margin Comparison
- **Top vendors**: 31.17% mean profit margin
- **Low-performing vendors**: 41.55% mean profit margin
- Statistical testing confirms significant difference between groups

## 📈 Correlation Insights
- **Strong correlation** (0.999) between purchase and sales quantities
- **Weak correlation** between purchase price and sales revenue/profit
- **Negative correlation** between sales price and profit margin

## 🚀 Recommendations

### Immediate Actions
- Implement targeted promotions for high-margin, low-sales brands
- Diversify vendor base to reduce dependency on top 10 suppliers
- Optimize bulk purchasing strategies for cost savings

### Strategic Initiatives
- Develop clearance strategies for slow-moving inventory ($2.71M value)
- Enhance marketing and distribution for low-performing vendors
- Re-evaluate pricing strategies across vendor segments

### Operational Improvements
- Monitor stock turnover metrics regularly
- Implement inventory management protocols
- Optimize freight and logistics costs

## 📊 Technical Implementation
The analysis includes:
- Exploratory Data Analysis (EDA)
- Statistical hypothesis testing
- Correlation analysis
- Profit margin confidence intervals
- Vendor segmentation and performance benchmarking

## 📄 Files Included
- `Vendor_Performance_Report.pdf` - Complete analysis and findings
- `README.md` - Project documentation

## 🛠 Skills Demonstrated
- Data Analysis & Visualization
- Statistical Testing
- Business Intelligence
- Inventory Management
- Vendor Relationship Management
- Profitability Analysis

## 📈 Business Impact
Implementation of these recommendations can lead to:
- Improved profit margins through optimized pricing
- Reduced inventory holding costs
- Enhanced supply chain resilience
- Better cash flow management
- Sustainable profitability growth

---

**Note**: This analysis provides a foundation for data-driven decision making in retail and wholesale inventory management. Regular monitoring and adjustment of these strategies is recommended for ongoing optimization.
