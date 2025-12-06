# Supplier Reliability & Cost Analysis

This project is a Power BI portfolio dashboard that analyzes how supplier
delivery performance impacts operational efficiency and financial results.

The report simulates a real-world supply chain scenario with 20 suppliers,
600+ purchase orders and multiple delay reasons (documentation, transport,
weather, production, capacity, customs).

---

## Objectives

The goal of the project is to answer four key business questions:

1. Which suppliers deliver reliably and how fast?
2. Which delays cost us the most money?
3. Why do delays happen (root causes)?
4. What should we fix first to get the biggest impact?

The dashboard is designed to support data-driven decision making for
procurement and logistics teams.

---

## Dashboard Pages

### 1. Supplier Performance (Page 3)

**Focus:** On-time delivery (OTD%) and average lead time by supplier.

Key elements:
- KPI cards: OTD %, Delay %, Avg Lead Time (days)
- Supplier ranking by OTD%
- Supplier comparison by average lead time

**Use:** Identify top and bottom performing suppliers and track overall
delivery reliability.

---

### 2. Financial Impact Analysis (Page 4)

**Focus:** How much money delays cost and who creates the biggest losses.

Key elements:
- Total delay cost (€)
- Average cost per delayed order (€)
- Bar chart: Total delay cost by supplier
- Line chart: Delay cost trend by month
- Bar chart: Delay cost by reason (documentation, transport, etc.)

**Use:** Find suppliers and root causes that drive the highest financial
impact and prioritize where to save costs.

---

### 3. Root Cause Analysis (Page 5)

**Focus:** Why delays happen and what to fix first.

Key elements:
- Heatmap: Delay cost by Supplier × Reason
- Supplier Risk Tier segmentation (Low Risk, High Frequency, High Cost, Critical)
- Recommended actions and Risk Summary text

**Use:** Connect operational issues to financial impact and define concrete
improvement actions.

---

## Data & Model

- **Data volume:** ~600 purchase orders
- **Tables:**
  - `FactOrders` – facts: order dates, promised vs actual delivery, delay flags, delay reasons, cost
  - `DimSuppliers` – supplier attributes and risk tier
  - `DimDelayReasons` – types of delay reasons
  - `DimCalendar` – date dimension

- **Model:** Star schema with `FactOrders` in the center and dimension tables
  connected via surrogate keys.

---

## Metrics (DAX)

Core measures are located in the `dax/measures.txt` file and include:

- On-time Delivery % (OTD %)
- Delay %
- Average Lead Time (days)
- Total Delay Cost (€)
- Average Cost per Delayed Order (€)
- Delay Count
- Worst Supplier (by delay cost)
- Top Cost Reason
- Top Frequency Reason
- Supplier Risk Tier (segmentation by cost & frequency)

These measures are used across cards, charts and the heatmap to create a
coherent analytical story.

---

## Tools & Tech

- **Power BI Desktop** – data model, DAX and dashboard
- **DAX** – KPI calculations and risk segmentation
- **Excel / CSV** – source data and validation
- **(Optional) Python** – synthetic data generation for the fact table

---

## Key Insights

Some of the key findings from the analysis:

- A small number of suppliers (e.g. Alpha-M Co. and Delta Components)
  generate a disproportionate share of delay cost.
- Documentation Errors are the most expensive delay cause.
- Transport Issues are the most frequent and should be monitored closely.
- Most suppliers are Low Risk, but several show recurring delays and should
  be tracked via scorecards.

These insights can guide discussions with suppliers and internal process
owners and help to prioritize improvement actions.

---

## How to Use

1. Open the `.pbix` file (if available) or review `Supplier_Reliability_Report.pdf`.
2. Use slicers (e.g. Country) to filter suppliers and see how KPIs and
   visuals react.
3. Review each page:
   - Page 3: performance
   - Page 4: financial impact
   - Page 5: root cause & risk

---

## Author

**Vladimir Luhovy**

- Data & Reporting professional with logistics and ERP background  
- Skills: Power BI, DAX, SQL, Python (data analysis)  
- Open to Data Analyst / Reporting / Data Operations roles 
