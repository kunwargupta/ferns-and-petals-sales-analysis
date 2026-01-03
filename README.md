# Ferns & Petals Sales Analysis – Excel Project

## Project Overview

This project provides a **comprehensive end-to-end sales analysis** of Ferns & Petals using **MS Excel + Power Query + Power Pivot**. It demonstrates the complete data analytics workflow from raw data cleaning to interactive dashboard visualization, enabling deep insights into customer behavior, product performance, and occasion-wise revenue patterns.

**Technologies Used:** Excel, Power Query, Power Pivot, DAX, Pivot Tables, Interactive Dashboards

---

## Project Objectives

- **Clean & Transform:** Validate and prepare raw data from multiple sources (Customers, Orders, Products)
- **Model Data:** Design a proper star-schema data model using Power Pivot
- **Calculate Metrics:** Create calculated columns using DAX (Revenue, Day Names, Delivery Performance)
- **Analyze Trends:** Extract actionable insights from orders, revenue, and delivery metrics
- **Visualize:** Build an interactive dashboard for stakeholder reporting

---

## Dataset Structure

The project includes three main data tables:

### 1. Customers Table
- Customer ID (Primary Key)
- Customer Name
- Contact Number (converted to Text format)
- Age, Gender
- City, Location

### 2. Orders Table (Fact Table)
- Order ID (Primary Key)
- Customer ID (Foreign Key)
- Order Date & Time
- Delivery Date & Time
- Product ID (Foreign Key)
- Quantity
- Occasion (Anniversary, Birthday, Diwali, Holi, Raksha Bandhan, Valentine's Day, etc.)

### 3. Products Table
- Product ID (Primary Key)
- Product Name
- Price (Currency Format)
- Category

---

## Part 1: Data Cleaning & Transformation (Power Query)

### 1.1 Column Profiling & Quality Checks
- Used **Power Query Column Profiling** to identify:
  - Data distribution (distinct & unique values)
  - Null/blank values
  - Potential data quality issues
  - Inconsistent formatting

### 1.2 Data Type Corrections
- **Contact Number** column in Customers table:
  - Converted from **Number** to **Text** format
  - Preserves leading digits and prevents scientific notation

### 1.3 Feature Engineering – Orders Table
Using **Add Column** in Power Query Editor:

**Temporal Features:**
- **Month Name** extracted from `Order Date`
  - Enables month-level trend analysis (Jan, Feb, Mar, etc.)
  - Used in pivot tables for seasonal patterns

- **Order Hour** extracted from `Order Time`
  - Captures time-of-day ordering patterns
  - Useful for peak order analysis

- **Delivery Hour** extracted from `Delivery Time`
  - Analyzes delivery scheduling patterns

**Delivery Performance:**
- **Delivery Difference (Days)**:
  - Custom column: `Delivery Date – Order Date` (returns duration)
  - Converted duration to **Number of Days**
  - Measures delivery speed (~5.53 days average)
  - Analyzed by order quantity and city

### 1.4 Merging Tables
- **Products → Orders** (Left Outer Join)
  - Join key: `Product ID`
  - Brought **Price** column into Orders table
  - Formatted Price as **Currency** for calculations

---

## Part 2: Data Modeling with Power Pivot

### 2.1 Enabling Power Pivot
**Steps to Enable:**
1. Go to **File > Options > Customize Ribbon**
2. Check **Developer** tab
3. Click **Developer > COM Add-ins**
4. Select **Microsoft Power Pivot for Excel**

### 2.2 Star Schema Design

Built a **star schema** architecture connecting:
- **Customers (1) ↔ Orders (Many)** on `Customer_ID`
  - Links customer demographics to their purchases

- **Products (1) ↔ Orders (Many)** on `Product_ID`
  - Connects product info (name, price) to order transactions

**Benefits of Star Schema:**
- Enables accurate aggregation across dimension tables
- Supports complex pivot table calculations
- Improves query performance
- Maintains data integrity through relationships

### 2.3 DAX Calculated Columns

**Revenue Calculation:**
- `Revenue = [Price] * [Quantity]`
- Line-level sales value
- Aggregated for occasion-wise, city-wise, and product-wise analysis

**Day Name Extraction:**
- `Day Name = FORMAT([Order Date], "DDDD")`
- Converts dates to full day names (Monday, Tuesday, etc.)
- Enables day-of-week analysis

---

## Part 3: Analysis & Key Insights

### 3.1 Order Analysis
- **Total Orders** aggregated by customer, occasion, and geography
- **Top Cities**: Imphal, Dhanbad, Kavali and other key cities identified
- City-level performance comparison

### 3.2 Delivery Performance
- **Average Delivery Time:** ~5.53 days
- **Delivery by Order Quantity:** 1-5 units
- Delivery time increases with larger order quantities
- Identify bottlenecks in fulfillment

### 3.3 Revenue Analysis
- **Top Occasions:** Anniversary, Raksha Bandhan
- **Other Occasions:** Holi, Birthday, Valentine's Day, Diwali, etc.
- Seasonal revenue trends
- **Top Products:** Magnam Set, Quia Gift, Dolores Gift
- Product mix analysis

### 3.4 Time-Based Trends
- Month-wise patterns: Identify peak seasons
- Day-of-week patterns: Which days drive most sales?
- Hour-of-day patterns: Peak ordering hours
- Seasonal effects: Occasion-driven spikes

---

## Part 4: Interactive Dashboard

### 4.1 Key Performance Indicators (KPIs)
The main dashboard displays:
1. **Total Revenue** – Overall sales performance
2. **Total Orders** – Transaction volume
3. **Average Delivery Time (Days)** – Service efficiency
4. **Top Cities Count** – Geographic distribution
5. **Top Occasions Revenue** – Revenue concentration

### 4.2 Visual Components
1. **Top 10 Cities by Order Count** (Bar Chart)
   - Shows geographic concentration of orders
   - Identifies key markets for expansion

2. **Revenue by Occasion** (Pie/Donut Chart)
   - Visualizes occasion-wise revenue contribution
   - Highlights top revenue generators

3. **Best-Selling Products by Revenue** (Bar Chart)
   - Product performance ranking
   - Helps inventory and marketing decisions

4. **Order Quantity vs. Delivery Days** (Scatter/Line Chart)
   - Shows correlation between order size and delivery time
   - Identifies service bottlenecks

### 4.3 Interactive Filtering
Dashboard includes slicers/filters for:
- **Occasion** (Anniversary, Birthday, Diwali, etc.)
- **City** (drill-down capability)
- **Product** (category or individual)
- **Month** (seasonal analysis)
- **Customer Segment** (optional)

**Users can dynamically filter the dashboard to explore specific scenarios and trends.**

---

## Key Insights & Findings

1. **Occasion-Driven Business:** Anniversary and Raksha Bandhan are primary revenue drivers
2. **Geographic Concentration:** Top 5 cities account for significant order volume
3. **Product Performance:** A small number of SKUs dominate sales
4. **Delivery Consistency:** Average 5.53-day delivery time; increases with larger orders
5. **Seasonal Patterns:** Clear seasonal peaks for specific occasions
6. **Peak Hours:** Most orders placed during evening hours

---

## Technical Skills Demonstrated

### Excel & Power Query
- Column profiling and data quality assessment
- Data type conversions (Number → Text)
- Custom column creation (calculations, string extraction)
- Merging/joining tables (Left Outer Join)
- Date/time transformations (FORMAT, extraction)

### Data Modeling (Power Pivot)
- Star schema design principles
- One-to-many relationships
- Diagram view visualization
- Data view management

### DAX (Data Analysis Expressions)
- Calculated columns (Revenue, Day Name)
- Formula syntax and functions
- Aggregation patterns

### Pivot Tables & Visualization
- Multi-dimensional pivot tables
- Pivot charts (bar, pie, scatter)
- Interactive dashboard design
- Slicers and filters
- KPI cards and conditional formatting

### Business Analytics
- Descriptive analytics
- Trend analysis
- Segmentation (by occasion, city, product)
- Performance metrics and KPIs
- Actionable insights extraction

---

## Project Deliverables

1. **Cleaned & Transformed Data** – Ready for analysis
2. **Power Pivot Data Model** – Properly structured with relationships
3. **Calculated Columns** – Revenue, Day Name, etc.
4. **Pivot Tables** – Multi-dimensional analyses
5. **Interactive Dashboard** – Executive summary with filters
6. **Documentation** – This README with complete methodology

---

## How to Use This Project

### For Learning:
1. Follow the data cleaning steps in Power Query to understand ETL workflows
2. Study the star schema design for data modeling best practices
3. Review DAX formulas to learn calculated column creation
4. Examine the dashboard for visualization techniques

### For Implementation:
1. Replace the sample data with your own Customers, Orders, Products tables
2. Recreate the relationships in Power Pivot
3. Adjust filters and KPIs as per your business requirements
4. Customize the dashboard colors and layout

---

## Prerequisites

- **Microsoft Excel 2016 or later** (Power Pivot support)
- **Power Query** add-in (built-in for Excel 2016+)
- Basic understanding of:
  - Excel functions and pivot tables
  - Database concepts (primary keys, relationships)
  - Data analysis fundamentals

---

## Learning Outcomes

After completing this project, you will understand:

- How to clean and validate raw business data
- Data type conversions and why they matter
- Designing normalized data models (star schema)
- Creating relationships in Power Pivot
- Writing DAX formulas for calculated columns
- Building pivot tables from related tables
- Designing interactive dashboards
- Extracting business insights from data
- End-to-end analytics workflow

---

## Contributing

If you have improvements or extensions to this project:
1. Fork the repository
2. Create a branch for your feature
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

## Contact & Support

For questions or feedback about this project:
- **GitHub:** [@kunwargupta](https://github.com/kunwargupta)
- **Topics:** Data Analysis, Excel, Power Pivot, Data Modeling, Business Intelligence

---

## License

This project is open source and available under the MIT License.

---

## References & Resources

- **Microsoft Excel Documentation:** Power Query Guide
- **DAX Formula Reference:** Microsoft DAX Documentation
- **Star Schema Design:** Data Warehouse Design Best Practices
- **Data Cleaning Best Practices:** Tidy Data Principles

---

**Last Updated:** January 2026
**Project Status:** Complete
