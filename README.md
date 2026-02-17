📊 Sales Performance Dashboard - Power BI Project

https://github.com/punith7915-prog/Project/blob/main/Screenshot%202026-02-17%20095303.png

## 🎯 Project Overview
An interactive Power BI dashboard providing comprehensive sales analytics and business intelligence insights for Q1 2024 order management data. This project demonstrates end-to-end data visualization capabilities, from raw data processing to actionable business insights.

## 📊 Key Metrics at a Glance
- **Total Revenue**: ₹15,298
- **Total Orders**: 31
- **Average Revenue per Order**: ₹493
- **Order Completion Rate**: 64.52%
- **Top Region**: North (42.62% of revenue)
- **Best Salesperson**: Sarah Johnson (₹7.2K)

## 📁 Repository Structure
```
sales-performance-dashboard/
├── data/
│   └── Sales_Data.xlsx              # Source dataset (31 orders)
├── screenshots/
│   ├── dashboard_final.png          # Final dashboard view
│   ├── data_preview.png             # Excel data preview
│   └── dashboard_evolution/         # Development stages
├── Dashboard.pbix                   # Power BI dashboard file
└── README.md                        # This file
```

## 🚀 Features

### 📈 Visual Components

#### 1. **Key Performance Indicators (KPIs)**
- Large, prominent cards displaying critical metrics
- Real-time calculation of totals and averages
- Color-coded for quick recognition

#### 2. **Monthly Revenue Trend**
- Clean bar chart visualization
- Shows Q1 2024 performance (Jan-Mar)
- Highlights: January peak at ₹3.7K

#### 3. **Regional Performance Analysis**
- Donut chart with percentage breakdowns
- Geographic distribution insights
- **Breakdown**: North 42.62% | South 27.29% | West 15.16% | East 14.93%

#### 4. **TOP 5 Products by Revenue**
| Rank | Product | Revenue |
|------|---------|---------|
| 1 | Laptop | ₹3,600 |
| 2 | Office Chair | ₹2,400 |
| 3 | Conference Table | ₹1,200 |
| 4 | Meeting Table | ₹899 |
| 5 | Storage Cabinet | ₹800 |

#### 5. **TOP 5 Customers by Revenue**
| Rank | Customer | Total Spent |
|------|----------|-------------|
| 1 | John Smith | ₹3,730 |
| 2 | Quinn Lopez | ₹1,500 |
| 3 | Jack Thomas | ₹1,200 |
| 4 | Bob Williams | ₹900 |
| 5 | Victor Walker | ₹899 |

#### 6. **Sales Representative Performance**
- Horizontal bar chart comparing team contributions
- **Team Breakdown**:
  - Sarah Johnson: ₹7.2K (47% of total)
  - Mike Davis: ₹4.2K (27%)
  - Tom Wilson: ₹2.6K (17%)
  - Lisa Chen: ₹1.3K (9%)

#### 7. **Order Status Distribution**
- Pie chart showing fulfillment pipeline
- **Status Breakdown**:
  - ✅ Completed: 64.52%
  - 📦 Pending: 16.13%
  - 🚚 Shipped: 12.90%
  - ❌ Cancelled: 6.45%

### 🎛️ Interactive Filters
- **Region**: East, North, South, West, NA
- **Status**: Completed, Pending, Shipped, Cancelled
- Cross-filtering enabled across all visuals

## 📊 Dataset Details

### Source Data Specifications
- **File**: Sales_Data.xlsx
- **Records**: 31 sales orders
- **Time Period**: January 1, 2024 - March 30, 2024
- **Currency**: Indian Rupees (₹)

### Data Schema
| Column | Type | Description |
|--------|------|-------------|
| Order ID | Integer | Unique order identifier (1001-1031) |
| Customer Name | Text | Customer full name |
| Product Category | Text | Electronics, Furniture, Office Supplies |
| Product Name | Text | Specific product ordered |
| Order Date | Date | Date of order placement |
| Quantity | Integer | Number of units ordered |
| Unit Price | Currency | Price per unit in ₹ |
| Total Amount | Currency | Quantity × Unit Price |
| Region | Text | Geographic region (North/South/East/West/NA) |
| Sales Rep | Text | Assigned sales representative |
| Status | Text | Order status (Completed/Pending/Shipped/Cancelled) |

## 🛠️ Technical Implementation

### Power BI Features Used
- ✅ Data modeling and relationships
- ✅ DAX measures for calculated fields
- ✅ Custom visual formatting and themes
- ✅ Visual-level and page-level filters
- ✅ Conditional formatting
- ✅ Interactive cross-filtering
- ✅ Responsive layout design
- ✅ Bookmarks for navigation

### Sample DAX Measures
```DAX
// Total Revenue
Total Revenue = SUM(Sales[Total Amount])

// Total Orders
Total Orders = COUNTROWS(Sales)

// Average Revenue per Order
Average Revenue = DIVIDE([Total Revenue], [Total Orders], 0)

// Completion Rate
Completion Rate = 
DIVIDE(
    CALCULATE(COUNTROWS(Sales), Sales[Status] = "Completed"),
    COUNTROWS(Sales),
    0
)

// Month-over-Month Growth
MoM Growth = 
VAR CurrentMonth = [Total Revenue]
VAR PreviousMonth = 
    CALCULATE(
        [Total Revenue],
        DATEADD(Sales[Order Date], -1, MONTH)
    )
RETURN
    DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth, 0)
```

## 📈 Key Business Insights

### 🔍 Analysis Findings

1. **Revenue Trend Analysis**
   - January showed strong performance (₹3.7K)
   - Sharp decline in February (₹1.2K) - 68% drop
   - Slight recovery in March (₹1.5K) - 25% increase
   - **Action**: Investigate February factors (seasonality, market conditions, sales activities)

2. **Geographic Performance**
   - North region dominates with 42.62% market share
   - South region second at 27.29%
   - East and West underperforming (combined 30%)
   - **Action**: Develop growth strategies for East and West regions

3. **Product Mix**
   - Electronics (Laptop) drives highest revenue
   - Furniture category shows strong performance (Office Chair, Conference Table)
   - Office Supplies contribute smaller amounts
   - **Action**: Focus marketing on high-value electronics and furniture

4. **Customer Concentration**
   - Top 5 customers represent 53.8% of revenue (₹8,229)
   - High customer concentration risk
   - John Smith alone contributes 24.4% of revenue
   - **Action**: Implement customer retention program and diversify customer base

5. **Sales Team Performance**
   - Sarah Johnson significantly outperforms (47% of sales)
   - Large performance gap between top and bottom performers
   - **Action**: Study Sarah's best practices and implement team training

6. **Order Fulfillment**
   - 64.52% completion rate needs improvement
   - 16.13% orders still pending (potential revenue at risk)
   - 6.45% cancellation rate within acceptable range
   - **Action**: Streamline fulfillment process and address pending orders
