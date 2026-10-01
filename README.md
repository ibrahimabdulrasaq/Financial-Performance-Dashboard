# 📊 Financial Performance Dashboard - Power BI

## Project Overview

The **Financial Performance Dashboard** is an interactive Business Intelligence solution developed in **Microsoft Power BI** to analyze financial performance across revenue, expenses, profit, regions, departments, and quarters.

The dashboard transforms a 1,000-row financial dataset into an interactive reporting solution that enables users to monitor financial performance, identify trends, analyze variances, and explore business performance at different levels of detail.

The project combines **data cleaning, data transformation, data modeling, DAX, time intelligence, dynamic metric selection, visualization, UI/UX design, and dashboard development**.

---

## Project Objectives

The main objectives of this project are to:

- Analyze total Revenue, Expenses, and Profit.
- Calculate Profit Margin.
- Analyze financial performance across quarters.
- Compare Revenue, Expenses, and Profit across regions.
- Compare financial performance across departments.
- Identify changes and variances in financial performance.
- Build a Waterfall Chart for variance analysis.
- Provide dynamic metric selection using Power BI Field Parameters.
- Develop an interactive and user-friendly dashboard.
- Apply a Star Schema data model.
- Create a dedicated Date table for time intelligence.
- Design dashboard wireframes before implementation.
- Provide actionable business insights from the financial data.

---

# Dataset Description

The project uses a financial dataset containing **1,000 rows** of financial records.

The dataset contains information relating to:

| Field | Description |
|---|---|
| Date | Transaction/reporting date |
| Year | Year of the transaction |
| Quarter | Financial quarter |
| Month | Month of the transaction |
| Region | Business/geographical region |
| Department | Department responsible for the transaction |
| Revenue | Revenue generated |
| Expenses | Expenses incurred |
| Profit | Profit generated |

The dataset was prepared and transformed in Power BI before being used for dashboard development.

---

# Tools & Technologies

The following tools and technologies were used:

- **Microsoft Power BI Desktop**
- **Power Query**
- **DAX (Data Analysis Expressions)**
- **Figma**
- **Data Modeling**
- **Star Schema**
- **Time Intelligence**
- **Field Parameters**
- **Power BI Bookmarks**
- **Power BI Navigation Buttons**

---

# Data Cleaning and Transformation

The raw financial dataset was cleaned and transformed using **Power Query** before being used in the analytical model.

The data preparation process included:

- Reviewing the dataset structure.
- Checking data types.
- Cleaning and transforming fields.
- Preparing financial fields for analysis.
- Ensuring date fields could be used for time-based analysis.
- Preparing dimensions required for the semantic model.
- Creating an additional **Departments_Dim** table.
- Creating a dedicated **Date table** for time intelligence.

<img width="1366" height="583" alt="Fact_Table" src="https://github.com/user-attachments/assets/121e7951-1881-400e-b972-c2e05043affc" />
<img width="1366" height="580" alt="Department_Dim" src="https://github.com/user-attachments/assets/048e9aa2-fd25-4b14-8aac-0b552bd45cef" />
<img width="1366" height="581" alt="Date_Dim" src="https://github.com/user-attachments/assets/018c0ac6-a99c-4f9e-9ae4-66a82fefedee" />

The cleaned and transformed data was then loaded into the Power BI data model.

<img width="1366" height="556" alt="FactTable" src="https://github.com/user-attachments/assets/98580b7f-4aaa-4e4b-8b70-abe70554edd1" />
<img width="1366" height="556" alt="DepartmentDim" src="https://github.com/user-attachments/assets/2a469749-fa65-424b-a26d-541db30ed8b8" />
<img width="1366" height="558" alt="DateDim" src="https://github.com/user-attachments/assets/26404a92-05e8-46f2-a87b-a4ab83478e36" />

---

# Data Modeling

A **Star Schema** approach was used to structure the Power BI semantic model.

The model consists of a central financial/fact table supported by dimension tables.

### Main Components

- Financial/Fact table
- Department_Dim
- Date dimension

The purpose of the model is to create a structured analytical environment where financial measures can be analyzed across different dimensions.

### Simplified Model Structure

<img width="539" height="417" alt="Data Model" src="https://github.com/user-attachments/assets/9d1213cb-6ea8-4e18-909b-effdad55ba3b" />

The Star Schema structure improves organization and supports efficient filtering and analysis within the dashboard.

---

# Department_Dim Table

An additional **Department_Dim** table was created as part of the data modeling process.

The purpose of this dimension table was to support a more structured semantic model and contribute to the Star Schema design.

---

# Date Dimension

A dedicated Date table was created to support time-based analysis and Power BI time intelligence.

The Date table contains fields such as:

* Date
* Year
* Quarter
* Month
* Month Number

The Date table enables financial performance to be analyzed consistently across different periods.

---

# Time Intelligence

Time intelligence was incorporated into the dashboard using the dedicated Date table.

This enables analysis across:

* Year
* Quarter
* Month
* Date

The Date table provides a structured foundation for analyzing financial performance over time.

---

# DAX Measures

The dashboard uses DAX measures to calculate the major financial KPIs.

### Total Revenue

```DAX
Total Revenue =
SUM(Financial_Data[Revenue])
```

### Total Expenses

```DAX
Total Expenses =
SUM(Financial_Data[Expenses])
```

### Total Profit

```DAX
Total Profit =
SUM(Financial_Data[Profit])
```

### Profit Margin

```DAX
Profit Margin =
DIVIDE([Total Profit], [Total Revenue])
```

> **Note:** The table and column names should be adapted if the names in the Power BI model are different.

---

# Dynamic Metric Selection Using Field Parameters

One of the key interactive features of the dashboard is the **dynamic metric selection**.

Power BI's:

**New Parameter → Fields**

functionality was used to create a **Field Parameter**.

The parameter contains the main financial metrics:

* Profit
* Total Revenue
* Total Expenses

The Field Parameter was then used in a slicer to allow users to dynamically select the metric they want to analyze.

### Dynamic Metric Selector

Users can switch between:

```text
Profit
Total Revenue
Total Expenses
```

This allows the dashboard visuals to respond dynamically to the selected financial metric.

---

# Waterfall Chart and Variance Analysis

The Waterfall Chart was used to analyze financial performance and show how values are distributed across quarters and departments.

The Waterfall configuration uses:

| Power BI Field  | Configuration                         |
| --------------- | ------------------------------------- |
| Category        | Quarter                               |
| Breakdown       | Department                            |
| Y-axis          | Field Parameter                       |
| Field Parameter | Profit, Total Revenue, Total Expenses |

The Field Parameter placed on the Y-axis allows the Waterfall Chart to dynamically switch between:

* Profit
* Revenue
* Expenses

The **Department** field is used as the breakdown, allowing the user to see departmental contributions within each quarter.

The **Quarter** field provides the period-based structure of the analysis.

This implementation makes the Waterfall Chart interactive and allows users to analyze different financial measures without creating separate Waterfall Charts for each metric.

---

# What the Waterfall Chart Shows

The Waterfall Chart provides a visual representation of financial values across quarters.

Depending on the selected metric, users can analyze:

### Profit

The Waterfall Chart can be used to examine how profit is distributed across quarters and departments.

### Revenue

The chart can be used to analyze revenue contributions across quarters and departments.

### Expenses

The chart can be used to analyze expense contributions across quarters and departments.

The Department breakdown provides additional granularity within the quarterly analysis.

---

# Dashboard Visualizations

The dashboard contains multiple visualizations designed to provide both high-level and detailed financial analysis.

The main visual components include:

* KPI Cards
* Revenue and Expenses Trend
* Waterfall Chart
* Regional Analysis
* Departmental Analysis
* Detailed Financial Table
* Variance Analysis

---

# KPI Cards

The dashboard contains KPI cards that provide a high-level summary of financial performance.

The major KPIs include:

* Total Revenue
* Total Expenses
* Total Profit
* Profit Margin

The KPI section allows users to quickly understand the overall financial position before exploring detailed visualizations.

---

# Revenue and Expenses Trend

A time-based visualization was created to analyze the movement of:

* Revenue
* Expenses

over time.

This visualization helps users understand financial trends and identify periods where revenue or expenses change.

---

# Quarter and Department Breakdown

Financial performance can be analyzed by:

* Quarter
* Department

This allows users to investigate how different departments contribute to financial performance across different periods.

The combination of Quarter and Department provides more granular analysis than viewing total financial values alone.

---

# Regional Financial Analysis

The dashboard includes regional analysis to compare financial performance across different regions.

Users can analyze:

* Revenue by Region
* Expenses by Region
* Profit by Region

This helps identify differences in financial performance between regions.

---

# Departmental Analysis

Department-level analysis is included to understand the financial contribution of different departments.

The dashboard enables users to investigate:

* Department Revenue
* Department Expenses
* Department Profit

This provides a more detailed view of how different parts of the organization contribute to overall financial performance.

---

# Executive Summary Table

A detailed table was incorporated into the **Executive Summary** page.

The table provides information such as:

* Department
* Region
* Revenue
* Expenses
* Profit
* Quarter

Conditional formatting was applied to improve readability and make important financial values easier to identify.

---

# Dashboard Interactivity

The dashboard was designed to provide an interactive analytical experience.

Users can filter and explore the financial data using multiple controls.

---

# Slicers

The dashboard includes slicers for:

* Year
* Region
* Department

The slicers allow users to narrow the analysis according to their selected requirements.

---

# Dynamic Metric Slicer

The Metric slicer is powered by the **Field Parameter**.

Users can select:

```text
Profit
Revenue
Expenses
```

The selected metric dynamically changes the relevant visual analysis.

This reduces the need to create multiple versions of the same visual and improves dashboard usability.

---

# Navigation Buttons

Navigation buttons were incorporated into the dashboard to improve movement between dashboard pages.

The buttons provide a smoother navigation experience and make it easier for users to move between different analytical sections.

---

# Custom Bookmarks

Custom Power BI bookmarks were used to support the dashboard's user experience.

Bookmarks were incorporated as part of the dashboard interaction and navigation design.

They help create a more controlled and user-friendly reporting experience.

---

# UI/UX Design

UI/UX was considered throughout the dashboard development process.

The design focused on:

* Clear visual hierarchy
* Easy navigation
* Logical placement of KPIs
* Accessible filtering
* Consistent dashboard structure
* User-friendly interactions
* Smooth movement between dashboard pages

The dashboard was designed not only as a reporting tool but also as an interactive analytical interface.

---

# Figma Wireframing

Before developing the final Power BI dashboard, **two wireframes were created using Figma**.

The wireframes were used to plan:

* Dashboard layout
* KPI placement
* Visual hierarchy
* Navigation
* Filtering structure
* Page organization
* User flow
* Overall UI/UX

The wireframing stage helped establish the intended dashboard structure before implementation in Power BI.

---

# Dashboard Pages

The dashboard contains two primary pages:

## 1. Performance Overview

The **Performance Overview** page provides a high-level view of financial performance.

It focuses on:

* Revenue
* Expenses
* Profit
* Profit Margin
* Trends
* Quarter performance
* Regional performance
* Departmental performance
* Variance analysis

---

## 2. Executive Summary

The **Executive Summary** page provides a more detailed view of financial performance.

It includes a detailed table containing fields such as:

* Department
* Region
* Revenue
* Expenses
* Profit
* Quarter

Conditional formatting was applied to improve the interpretation of the detailed financial data.

---

# Dashboard KPI Results

The completed dashboard produced the following overall KPI values:

| KPI            |           Result |
| -------------- | ---------------: |
| Total Revenue  |            7.50M |
| Total Expenses |            6.21M |
| Total Profit   | Approximately 1M |
| Profit Margin  |           17.19% |

These values provide a high-level summary of the financial dataset represented in the completed dashboard.

---

# Key Findings

The dashboard analysis provides several observations about the financial data.

### 1. Expenses Have a Significant Impact on Profit

The relationship between Revenue, Expenses, and Profit shows that expenses represent a substantial portion of revenue.

This makes expense monitoring an important part of profitability analysis.

### 2. Financial Performance Changes Across Quarters

The quarter-based analysis shows that financial performance varies across different periods.

The Waterfall Chart provides a way to examine these changes while also breaking the results down by department.

### 3. Regional Performance Varies

The regional analysis demonstrates differences in financial performance between regions.

Revenue, expenses, and profit should therefore be considered together rather than relying on revenue alone.

### 4. Departmental Contributions Differ

Different departments contribute differently to the organization's financial results.

The departmental breakdown allows users to investigate these differences at a more granular level.

### 5. Granular Records Can Reveal Negative Profit

Detailed financial records can contain situations where expenses exceed revenue, resulting in negative profit.

These records require further investigation to understand the underlying causes.

---

# Business Insights

The dashboard provides several areas that management can investigate:

* The relationship between revenue and expenses.
* Quarterly changes in financial performance.
* Regional profitability.
* Departmental profitability.
* Areas with high expenses.
* Areas with low or negative profit.
* Differences between revenue growth and profit growth.
* Financial performance at both summary and granular levels.

The dashboard therefore supports both high-level monitoring and detailed financial investigation.

---

# Recommendations

Based on the analysis provided by the dashboard, the following actions can be considered:

### 1. Monitor Expenses

Regularly monitor expense levels and identify areas where costs can be controlled without negatively affecting business operations.

### 2. Investigate Loss-Making Areas

Records or combinations of region, department, and quarter showing negative profit should be investigated to understand the underlying causes.

### 3. Monitor Regional Profitability

Regional performance should be evaluated using Revenue, Expenses, and Profit together rather than Revenue alone.

### 4. Conduct Quarterly Performance Reviews

Quarterly financial reviews can help identify changes in performance and allow management to investigate significant movements.

### 5. Review Departmental Cost Efficiency

Departments with high expenses relative to revenue should be reviewed to understand their cost structures and operational performance.

### 6. Use the Dashboard Continuously

The dashboard can be used as an ongoing analytical tool rather than only as a one-time report.

The interactive slicers and Field Parameters allow users to explore different financial perspectives as business questions change.

---

# Learning Outcomes

This project provided practical experience in:

* Power BI dashboard development
* Power Query data transformation
* Data cleaning
* Data modeling
* Star Schema design
* DAX measure creation
* Time intelligence
* Financial analysis
* Variance analysis
* Waterfall Chart development
* Field Parameters
* Dynamic metric selection
* Interactive slicers
* Power BI bookmarks
* Navigation buttons
* Dashboard UI/UX
* Figma wireframing
* Business intelligence storytelling

---

# GitHub Repository Structure

```text
Financial-Performance-Dashboard/
│
├── README.md
│
├── dataset/
│   └── financial_dataset_1000_rows.csv
│
├── dashboard/
│   └── Financial_Performance_Dashboard.pbix
│
├── wireframes/
│   ├── wireframe_01.png
│   └── wireframe_02.png
│
├── screenshots/
│   ├── performance_overview.png
│   └── executive_summary.png
│
└── documentation/
    └── project_documentation.pdf
```

> The filenames above are suggested repository organization. Replace them with the actual filenames used in the project.

---

# Dashboard Preview

Add screenshots of the completed Power BI dashboard to this section.

### Performance Overview

<img width="912" height="518" alt="Page1" src="https://github.com/user-attachments/assets/c347fe82-6ea4-42a5-8e47-148edc790dd1" />

### Executive Summary

<img width="917" height="523" alt="Page2" src="https://github.com/user-attachments/assets/1fad9753-d961-4df4-a45b-1ce161b6c9e8" />

---

# Wireframe Preview

The project includes two Figma wireframes created during the planning stage.

### Wireframe 01


<img width="1920" height="1080" alt="Financial Performance Dashboard" src="https://github.com/user-attachments/assets/0ca4999e-2cd3-404f-9ffe-7752cd45e62f" />


### Wireframe 02

<img width="1920" height="1080" alt="Financial Performance Dashboard (1)" src="https://github.com/user-attachments/assets/751ea00b-e85c-4335-9ad1-73cf491e1ba2" />

---

# Project Workflow

The project followed the following workflow:

```text
Raw Financial Dataset
        │
        ▼
Data Cleaning
        │
        ▼
Power Query Transformation
        │
        ▼
Department_Dim Creation
        │
        ▼
Date Table Creation
        │
        ▼
Star Schema Data Model
        │
        ▼
DAX Measures
        │
        ▼
Figma Wireframing
        │
        ▼
Power BI Dashboard Development
        │
        ▼
Field Parameter / Dynamic Metrics
        │
        ▼
Waterfall & Variance Analysis
        │
        ▼
Navigation & Bookmarks
        │
        ▼
Final Interactive Dashboard
```

---

# ❓ Analytical Questions Addressed

The dashboard was designed to answer the following analytical questions:

### Revenue

* What is the total revenue?
* How does revenue change over time?
* How does revenue differ across regions?
* How does revenue differ across departments?

### Expenses

* What are the total expenses?
* How do expenses change over time?
* Which regions generate higher expenses?
* How do expenses differ between departments?

### Profit

* What is the total profit?
* What is the overall profit margin?
* How does profit change across quarters?
* How does profitability differ across regions?
* How does profitability differ across departments?

### Variance

* How does financial performance change across quarters?
* What departmental contributions make up the quarterly values?
* How does the selected financial metric change when switching between Profit, Revenue, and Expenses?
* Which areas require further investigation?

---

# Executive Summary

The **Financial Performance Dashboard** provides an interactive view of the organization's financial performance using Revenue, Expenses, Profit, and Profit Margin.

The project demonstrates the complete Business Intelligence workflow, beginning with data cleaning and transformation and continuing through data modeling, DAX development, wireframing, visualization, interactivity, and dashboard deployment.

A **Star Schema** was implemented using a central financial dataset supported by dimension tables, including the **Products_Dim** and dedicated **Date table**.

The dashboard uses **Field Parameters** to allow users to dynamically switch between Profit, Revenue, and Expenses.

The **Waterfall Chart** combines Quarter as the category, Department as the breakdown, and the Field Parameter as the Y-axis, enabling interactive analysis of different financial metrics.

The dashboard also incorporates:

* KPI cards
* Trend analysis
* Regional analysis
* Departmental analysis
* Variance analysis
* Slicers
* Dynamic metric selection
* Navigation buttons
* Custom bookmarks
* Conditional formatting
* Figma-based wireframes

The final result is an interactive Power BI financial reporting solution designed to support financial monitoring, analysis, and business decision-making.

---

# Project Highlights

* Built an interactive Power BI financial dashboard.
* Cleaned and transformed a 1,000-row financial dataset.
* Implemented a Star Schema semantic model.
* Created a dedicated Date dimension.
* Applied time intelligence concepts.
* Created financial DAX measures.
* Implemented Field Parameters for dynamic metric selection.
* Built a Waterfall Chart for variance analysis.
* Analyzed regional financial performance.
* Analyzed departmental financial performance.
* Added interactive slicers.
* Added navigation buttons.
* Implemented custom bookmarks.
* Designed two Figma wireframes.
* Created an Executive Summary table with conditional formatting.
* Developed financial trend analysis.
* Generated business insights and recommendations.

---

# Skills Demonstrated

### Data Analytics

* Data Cleaning
* Data Transformation
* Financial Analysis
* Variance Analysis
* Trend Analysis
* Business Intelligence

### Power BI

* Dashboard Development
* Data Modeling
* Star Schema
* DAX
* Power Query
* Time Intelligence
* Field Parameters
* Waterfall Charts
* KPI Cards
* Slicers
* Bookmarks
* Navigation Buttons
* Conditional Formatting

### UI/UX

* Dashboard Wireframing
* Figma
* Visual Hierarchy
* User Navigation
* Interactive Dashboard Design

---

# Author

**Ibrahim Abdulrasaq**

Data Analyst | Business Intelligence Analyst

---

# Conclusion

The Financial Performance Dashboard demonstrates how Power BI can be used to transform financial data into an interactive Business Intelligence solution.

The project combines **data preparation, semantic modeling, DAX, time intelligence, dynamic metric selection, variance analysis, visualization, and UI/UX design** into one complete analytical workflow.

The use of **Field Parameters** provides flexible metric selection, while the **Waterfall Chart** enables quarterly and departmental analysis of Profit, Revenue, and Expenses.

The combination of interactive filters, KPI cards, trend analysis, regional and departmental analysis, navigation buttons, bookmarks, and detailed reporting provides users with multiple ways to explore financial performance.

Overall, the project demonstrates practical skills in developing an end-to-end Power BI financial analytics solution.

```
```
