# Ferns & Petals Sales Analysis

## What I Did

Built a complete sales analysis project for Ferns & Petals using Excel, analyzing 3 interconnected data tables (Customers, Orders, Products) with 1000+ transactions. Performed data cleaning, created data models, built interactive dashboards, and extracted actionable business insights.

---

## Data I Worked With

**Three main tables:**
- **Customers:** Demographics (ID, Name, Contact, City, Age, Gender)
- **Orders:** Transaction data (Order ID, Date, Time, Delivery Date, Quantity, Occasion)
- **Products:** Product details (Product ID, Name, Price, Category)

**Analyzed:** Revenue by occasion, delivery performance, top cities, product popularity, temporal trends

---

## What I Learned & Tools Used

### 1. Data Cleaning & Transformation (Power Query)

**What I did:**
- Column profiling to detect data quality issues (blanks, inconsistent formatting, data distribution)
- Converted Contact Number from Number to Text format (preserves leading zeros)
- Extracted temporal features:
  - Month Name from Order Date
  - Hour from Order Time & Delivery Time
  - Delivery duration (Delivery Date - Order Date)
- Merged Products table into Orders (Left Outer Join on Product ID)
- Formatted Price column as currency

**Skills gained:**
- Data quality validation & error detection
- Data type conversions and their impact
- Date/time extraction & transformation
- Table joins & data consolidation

### 2. Data Modeling with Power Pivot

**What I did:**
- Built star schema data model
- Created relationships:
  - Customers (Dimension) 1:Many -> Orders (Fact)
  - Products (Dimension) 1:Many -> Orders (Fact)
- Enabled cross-table aggregation using relationships

**Skills gained:**
- Database design principles (star schema)
- Primary/foreign key relationships
- Fact vs dimension table concepts
- How relationships enable multi-table analysis

### 3. Calculated Columns & DAX

**What I did:**
- Revenue column: `[Price] * [Quantity]`
- Day Name column: `FORMAT([Order Date], "DDDD")`

**Skills gained:**
- DAX formula writing
- Mathematical calculations in data models
- Date formatting functions

### 4. Analysis & Key Insights Discovered

- **Top revenue drivers:** Anniversary (highest), followed by Raksha Bandhan
- **Delivery performance:** Average 5.53 days delivery time
- **Geographic trends:** Imphal, Dhanbad, Kavali are top cities
- **Product performance:** Magnam Set, Quia Gift dominate sales
- **Delivery scaling:** Larger orders take longer (1-5 units)
- **Seasonal patterns:** Clear spikes for occasion-based gifting

**Skills gained:**
- Business intelligence & insight extraction
- Trend identification & analysis
- Data-driven decision making
- KPI definition & measurement

### 5. Interactive Dashboard Creation

**Built:**
- KPI cards: Total Revenue, Total Orders, Avg Delivery Time
- Top 10 Cities bar chart
- Revenue by Occasion pie chart
- Best-selling Products ranking
- Order Quantity vs Delivery Days correlation
- Dynamic slicers: Occasion, City, Month, Product

**Skills gained:**
- Dashboard design for business users
- Chart selection & visualization best practices
- Interactive filtering & slicing
- User-friendly reporting

---

## Technical Stack

**Excel Tools Used:**
- Power Query (ETL, data transformation, feature engineering)
- Power Pivot (data modeling, relationships, DAX)
- Pivot Tables (multi-dimensional analysis)
- Pivot Charts (visualization)
- Interactive Dashboards (KPI reporting)

---

## Key Accomplishments

✓ Cleaned & validated raw data from multiple sources
✓ Designed & implemented star schema database model
✓ Extracted & engineered 5+ new features from raw dates/times
✓ Created calculated metrics using DAX formulas
✓ Built interactive dashboard with 5+ visualizations
✓ Discovered 6+ actionable business insights
✓ Enabled dynamic multi-level filtering for analysis

---

## Why This Matters

**Demonstrates:**
- End-to-end analytics pipeline (raw data → insights)
- Database design & data modeling concepts
- Problem-solving with real business data
- Technical proficiency in Excel BI tools
- Ability to communicate data through dashboards
