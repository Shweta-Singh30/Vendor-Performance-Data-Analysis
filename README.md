# Vendor Performance Analysis & Inventory Optimization

## 📊 Project Overview
A comprehensive data analysis project that evaluates vendor performance, inventory turnover, and profitability metrics to provide actionable insights for retail and wholesale operations optimization.

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- SQLite3
- Git

### Installation & Setup

1. **Clone the Repository**
```bash
git clone https://github.com/Shweta-Singh30/Vendor-Performance-Data-Analysis.git
cd Vendor-Performance-Data-Analysis
```

2. **Create Virtual Environment**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. **Install Dependencies**
```bash
pip install pandas sqlalchemy
```

4. **Prepare Directory Structure**
```bash
mkdir -p data logs
```

5. **Add Your CSV Files**
Place these files in the `data/` directory:
- `purchases.csv`
- `sales.csv` 
- `vendor_invoice.csv`
- `purchase_prices.csv`

6. **Run the Analysis Pipeline**
```bash
# Step 1: Ingest data into database
python ingestion_db.py

# Step 2: Generate vendor summary
python get_vendor_summary.py
```

## 📋 Requirements

### Python Packages
- pandas>=1.4.0
- sqlalchemy>=1.4.0
- sqlite3 (built-in)

### System Requirements
- RAM: 4GB minimum
- Storage: 100MB free space
- OS: Windows, macOS, or Linux

## 📁 Project Structure
```
vendor-performance-analysis/
├── data/                    # Raw CSV files
├── logs/                    # Application logs
├── ingestion_db.py          # Data ingestion script
├── get_vendor_summary.py    # Analysis script
├── inventory.db             # Generated database
└── README.md
```

## 🔧 Scripts Overview

### ingestion_db.py
**Purpose**: Automatically ingests all CSV files into SQLite database.

**Features**:
- Detects all CSV files in data directory
- Creates tables with filename as table name
- Comprehensive logging
- Performance timing

**Usage**:
```bash
python ingestion_db.py
```

### get_vendor_summary.py
**Purpose**: Creates comprehensive vendor performance summary.

**Key Functions**:
- Merges purchase, sales, and freight data
- Calculates business metrics:
  - Gross Profit
  - Profit Margin (%)
  - Stock Turnover Ratio
  - Sales to Purchase Ratio
- Data cleaning and transformation
- Saves results to database

**Usage**:
```bash
python get_vendor_summary.py
```

## 📊 Key Business Insights

### 1. Vendor Dependency
- **Top 10 vendors** contribute 65.69% of total purchases
- **Risk**: High dependency on few suppliers
- **Solution**: Diversify vendor partnerships

### 2. Bulk Purchasing Benefits
- **72% lower unit costs** for bulk orders
- Bulk price: $10.78 vs Small order: $39.06 per unit
- **Recommendation**: Leverage bulk purchasing strategies

### 3. Inventory Optimization
- **$2.71M** tied up in unsold inventory
- Identified slow-moving vendors (StockTurnover: 0.61-0.82)
- **Action**: Adjust purchase quantities and launch clearance sales

### 4. Profit Margin Analysis
- **Top vendors**: 31.17% mean profit margin
- **Low-performing vendors**: 41.55% mean profit margin
- **Statistical validation**: Significant difference confirmed
- **Strategy**: High-margin vendors focus on pricing, top sellers focus on cost efficiency

### 5. Brand Performance
- **198 brands** with high margins but low sales
- Profit margins: 60-90%
- **Opportunity**: Targeted marketing and pricing adjustments

## 🗃️ Database Output

### Generated Tables
- `purchases` - Purchase transactions
- `sales` - Sales transactions
- `vendor_invoice` - Vendor invoices
- `purchase_prices` - Product pricing
- `vendor_sales_summary` - Comprehensive performance metrics

### vendor_sales_summary Columns
- VendorNumber, VendorName, Brand, Description
- PurchasePrice, ActualPrice, Volume
- TotalPurchaseQuantity, TotalPurchaseDollars
- TotalSalesQuantity, TotalSalesDollars
- GrossProfit, ProfitMargin, StockTurnover, SalesToPurchaseRatio

## 📈 Usage Examples

### Query High-Margin Brands
```python
import sqlite3
import pandas as pd

conn = sqlite3.connect('inventory.db')
query = """
SELECT VendorName, Brand, ProfitMargin, TotalSalesDollars
FROM vendor_sales_summary 
WHERE ProfitMargin > 50 
ORDER BY ProfitMargin DESC
"""
df = pd.read_sql_query(query, conn)
print(df)
```

### Analyze Slow-Moving Inventory
```python
query = """
SELECT VendorName, StockTurnover, TotalPurchaseDollars
FROM vendor_sales_summary 
WHERE StockTurnover < 0.8
ORDER BY StockTurnover ASC
"""
slow_moving = pd.read_sql_query(query, conn)
print(slow_moving)
```

## 🛠️ Troubleshooting

### Common Issues

1. **Missing CSV Files**
   - Ensure all required CSV files are in `data/` directory
   - Check file names match expected names

2. **Database Errors**
   - Delete `inventory.db` and rerun scripts
   - Check file permissions

3. **Import Errors**
   - Ensure virtual environment is activated
   - Run `pip install pandas sqlalchemy`

### Log Files
Check for detailed error information:
- `logs/ingestion_db.log` - Data ingestion process
- `logs/get_vendor_summary.log` - Analysis process

## 🎯 Business Recommendations

### Immediate Actions
- Implement promotions for 198 high-margin, low-sales brands
- Diversify vendor base to reduce dependency
- Optimize bulk purchasing strategies

### Strategic Initiatives
- Develop clearance strategies for $2.71M slow-moving inventory
- Enhance marketing for low-performing vendors
- Re-evaluate pricing strategies

### Operational Improvements
- Monitor stock turnover metrics regularly
- Implement inventory management protocols
- Optimize freight and logistics costs

## 📝 Final Results
After running both scripts, you'll have:
- Complete SQLite database with all processed data
- Comprehensive vendor performance metrics
- Log files for debugging and monitoring
- Ready-to-use data for business intelligence and reporting

## 🤝 Support
For issues or questions:
1. Check the log files in `logs/` directory
2. Ensure all CSV files are properly formatted
3. Verify Python and package versions

---

**Success Message**: After running both scripts successfully, you should see "Ingestion Complete" and "Completed" messages in the logs, with the `vendor_sales_summary` table ready for analysis in `inventory.db`.
