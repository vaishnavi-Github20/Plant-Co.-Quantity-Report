# 🌿 Plant-Co. Quantity Performance Report

![Dashboard Screenshot](https://github.com/vaishnavi-Github20/Plant-Co.-Quantity-Report/blob/main/quantity-performance.png)


---

## 📚 Table of Contents

- [📊 Overview](#-overview)
- [🎯 Project Goals](#-project-goals)
- [📈 Dashboard Features](#-dashboard-features)
- [🧱 Data Model Architecture](#-data-model-architecture)
- [🛠️ Tools & Technologies Used](#️-tools--technologies-used)
- [🚀 How to Use](#-how-to-use)
- [📌 Use Cases](#-use-cases)
- [🛠️ Future Enhancements](#️-future-enhancements)
- [📸 Dashboard Preview](#-dashboard-preview)
- [📬 Contact](#-contact)
- [📄 License](#-license)

---

## 📊 Overview

The **Plant-Co. Quantity Performance Report** is a Power BI project that provides comprehensive insights into production quantity performance across various plants. The goal is to empower decision-makers by transforming raw operational data into meaningful KPIs and visual narratives.

The dashboard facilitates easy monitoring of:
- Total output across time
- Plant-wise comparisons
- Monthly trends
- Top-performing production units

This helps stakeholders quickly identify issues, discover opportunities, and plan operational improvements effectively.

---

## 🎯 Project Goals

- 🔍 Provide a centralized view of quantity-based production performance
- 📉 Highlight low-performing plants to address inefficiencies
- 📈 Empower data-driven strategies using interactive visualizations
- 📊 Track production over time for trend analysis and forecasting
- ✅ Offer an intuitive and accessible reporting interface for non-technical users

---

## 📈 Dashboard Features

This Power BI report includes a variety of performance-focused visuals:

| Visualization           | Description                                                       |
|-------------------------|-------------------------------------------------------------------|
| **KPI Cards**           | Showcase total production quantity and other core metrics         |
| **Monthly Trend Chart** | Line or clustered column chart showing production trends over time|
| **Plant-Wise Bar Chart**| Compares production output across all plants                      |
| **Pie Chart**           | Displays percentage contribution of each plant to total quantity  |
| **Slicers**             | Interactive filters for selecting date ranges and specific plants |
| **Top Performing Plants** | Dynamically ranks plants based on quantity produced             |

These elements are all interconnected, enabling deep drill-downs and quick data slicing.

---

## 🧱 Data Model Architecture

The report leverages a star schema model with calculated measures written in DAX (Data Analysis Expressions).

### 🗃️ Tables

- **FactProduction**
  - Fields: `Date`, `Plant ID`, `Quantity Produced`
- **DimPlant**
  - Fields: `Plant ID`, `Plant Name`, `Location`
- **DimDate**
  - Fields: `Date`, `Month`, `Year`, `Quarter`

### 🧮 Sample DAX Measures

```dax
Total Quantity = SUM(FactProduction[Quantity Produced])

Top Plants = 
TOPN(5, 
    SUMMARIZE(FactProduction, DimPlant[Plant Name], "TotalQty", [Total Quantity]),
    [Total Quantity], DESC
)

Monthly Trend = 
CALCULATE(
    [Total Quantity],
    ALLEXCEPT(DimDate, DimDate[Month], DimDate[Year])
)
```

## 🛠️ Tools & Technologies Used

| Tool / Technology   | Description                                             |
|---------------------|---------------------------------------------------------|
| **Power BI Desktop**| A business intelligence tool used to build interactive dashboards and reports |
| **DAX (Data Analysis Expressions)** | A formula language used in Power BI to define custom calculations and measures |
| **Power Query (M)** | A data transformation and preparation engine used to clean and shape raw data |
| **GitHub**          | Version control system for hosting and collaborating on the project |
| **Excel / CSV**     | Data sources used for importing production and plant-related data |

## 🚀 How to Use

Follow these steps to run and explore the Power BI report:

### 1. Clone this repository:

```bash
git clone https://github.com/vaishnavi-Github20/Plant-Co.-Quantity-Report.git

```
---


## 📌 Use Cases

This report can be used by multiple teams in a manufacturing business:

- **Operations Team**: Monitor real-time output trends and plant-wise efficiency.
- **Executives & Leadership**: Get high-level overviews to support strategic decisions.
- **Production Managers**: Identify and fix bottlenecks in underperforming units.
- **Data Analysts**: Use this report as a foundation for deeper exploratory analysis.

---

## 🛠️ Future Enhancements

Planned future improvements to make the dashboard even more valuable:

- ✅ **Live database connection** for real-time insights
- 📥 **Cloud sharing via Power BI Service** for collaborative access
- 🧠 **Predictive analytics** to forecast future production trends
- 🗂️ Additional report pages for **plant maintenance** and **resource allocation**
- 📱 **Mobile-optimized views** for use by field managers on the go

---

## 📬 Contact

**Vaishnavi Ganeshkar**  
👩‍💻 [GitHub Profile](https://github.com/vaishnavi-Github20)  
✉️ For questions, suggestions, or collaboration opportunities, please raise an issue or reach out via GitHub.

