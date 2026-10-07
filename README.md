# Meta Ads Executive & Operational Analytics Dashboard

An end-to-end Power BI analytics solution designed to evaluate Meta (Facebook & Instagram) advertising performance across executive and operational levels. This multi-page dashboard bridges high-level financial reporting (**Page 1: Financial & Executive Overview**) with granular marketing intelligence (**Page 2: Audience, Creative & Placement Deep-Dive**) to optimize ad spend allocation, detect creative fatigue, and maximize return on ad spend (ROAS).

---

## 📸 Dual-Page Dashboard Preview

| Page 1: Financial & Executive Overview | Page 2: Audience & Creative Performance Deep-Dive |
| :---: | :---: |
| ![Page 1 Executive Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) | ![Page 2 Deep Dive Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

### 📹 Video Walkthrough & Interactive Demo
* 🎥 **[Watch Full Dashboard Demo Video](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Meta%20ad%20dashboard%20(1)%20(1).mp4)**

---

## 🛠️ Tech Stack

| Technology | Role & Application |
| :--- | :--- |
| **Power BI Desktop** | Multi-page report development, dark theme UI/UX (`#0B0F19` canvas, `#1E293B` containers), and native page button navigation. |
| **DAX (Data Analysis Expressions)** | Custom calculated measures for financial ROI and engagement performance (`ROAS`, `CPA`, `CTR %`, `CPC`, `Total Spend`, `Total Revenue`). |
| **Power Query** | Data transformation, data type enforcement, dimensional modeling, and field mappings across fact/dimension tables. |
| **Python (`pandas`, `numpy`)** | Synthetic ad performance dataset generation, Meta Graph API response modeling, missing value handling, and pre-ingestion validation. |
| **Git / GitHub** | Project version control, documentation, and portfolio hosting. |

---

## 🐍 Python's Role in the Analytics Engine

Python served as the core data engine for structuring and enriching the underlying dataset prior to loading into Power BI:

1. **Multi-Channel Data Simulation**:
   * Generated realistic, multi-dimensional advertising data mimicking raw Meta Ads Manager CSV/API exports using `pandas` and `numpy`.
   * Constructed balanced distributions across impressions, clicks, spend, revenue, conversions, demographics, platforms, and placement types.
2. **Data Pipeline Cleansing & Transformation**:
   * Programmatically resolved missing values, parsed date hierarchies, and harmonized currency formats via Pandas workflows.
   * Executed strict relationship validation checks to ensure clean primary/foreign key mappings across tables without cyclic dependencies.
3. **API Data Extraction Simulation**:
   * Simulated an automated ETL pipeline transforming raw nested JSON payloads (emulating Meta Graph API endpoints) into structured CSV relational tables (`ADS_DATA`, `CAMPAIGNS`, `AD_CREATIVES`).

---

## 💾 Data Architecture & Star Schema Model

The data architecture follows a **Star Schema** designed for maximum query speed and seamless DAX filter context flow.

![Star Schema Data Model](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1241).png?raw=true)

* **Fact Table (`ADS_DATA`)**: Stores core transactional advertising metrics (Spend, Revenue, Clicks, Impressions, Conversions, Demographics, Placement, Platform, DateKey).
* **Dimension Tables**:
  * `CAMPAIGNS`: Campaign identifiers, strategy names, and budget allocations.
  * `AD_CREATIVES`: Asset titles, creative types (Static, Video, Carousel), and visual metadata.
  * `DateTable`: Continuous calendar table supporting Time Intelligence calculations.

* **Power Query ETL Transformation Pipeline**:
![Power Query Workflow](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1242).png?raw=true)

---

## 📊 PAGE 1: Financial & Executive Overview

Designed for C-suite leadership and marketing managers requiring instant high-level financial evaluation of total spend, revenue generation, and overall campaign return on investment (ROAS).

### Key Features on Page 1:
* **Financial KPI Grid**: Standardized KPI cards tracking top-line operational metrics (`Clicks`, `Revenue`, `CPC`, `Conversions`, `CPA`, `CTR %`).
* **Campaign Spend vs. Revenue Bar Chart**: Ranks campaign performance side-by-side to isolate top-performing campaigns against budget allocations.
* **Daily Ad Spend & Revenue Area Chart**: Continuous time-series line/area chart tracking seasonal spikes, scale phases, and revenue trends over time.
* **Executive Callout Summary Cards**: Prominently highlights consolidated totals for `Total Revenue` ($6.67M), `Overall ROAS` (4.29), and `Total Spend` ($1.56M).

### 📸 Page 1 Screenshot Gallery

| Visual Component | Screenshot Preview |
| :--- | :---: |
| **Full Page 1 Executive Layout** | ![Page 1 Layout](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) |
| **Page 1 Full Overview View** | ![Page 1 Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1194).png?raw=true) |
| **Top KPI Grid Detail** | ![KPI Grid](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1195).png?raw=true) |
| **Campaign Revenue vs Spend Chart** | ![Campaign Spend vs Revenue](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1196).png?raw=true) |
| **Daily Spend & Revenue Trend Analysis** | ![Daily Trend](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1197).png?raw=true) |
| **Executive Card Metrics ($6.67M Revenue)** | ![Summary Cards](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1198).png?raw=true) |
| **Page 1 Filtered Slicer View** | ![Filtered Page 1](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1199).png?raw=true) |

---

## 🎯 PAGE 2: Operational, Audience & Creative Deep-Dive

Designed specifically for media buyers, growth marketers, and creative teams to analyze creative efficiency, demographic traction, placement distributions, and target audience segments.

### Key Features on Page 2:
* **Creative Performance Breakdown (Matrix Visual)**: Itemized matrix breaking down ad performance (`Ad Name`, `Creative Type`, `Spend`, `CTR %`, `Conversions`, `ROAS`) with conditional data bars to instantly spot top concepts and detect visual fatigue.
* **Spend by Key Demographics**: Clustered horizontal bar chart mapping advertising spend and conversion volume across age brackets (25-34, 35-44, 18-24) and gender groups.
* **Placement Performance**: Bar chart evaluating click-through efficiency (`CTR %`) across distinct ad placements (Facebook Feed, Instagram Reels, FB Stories, IG Explore).
* **Platform Breakdown**: Donut chart visualizing overall budget distribution across Facebook, Instagram, and Audience Network.
* **Geographic Revenue Distribution**: Bubble density map highlighting top revenue-generating regional markets.
* **Audience Segment Performance**: Treemap comparing spend and ROAS across retargeting website visitors vs. lookalike target audiences.

### 📸 Page 2 Screenshot Gallery

| Visual Component | Screenshot Preview |
| :--- | :---: |
| **Page 2 Deep-Dive Overview (Initial)** | ![Page 2 Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1225).png?raw=true) |
| **Full Page 2 Dashboard Layout** | ![Page 2 Full](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1226).png?raw=true) |
| **Creative Matrix Breakdown & Heatmap** | ![Creative Matrix](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1227).png?raw=true) |
| **Platform Breakdown (Donut Chart)** | ![Platform Donut](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1228).png?raw=true) |
| **Placement Performance (CTR %)** | ![Placement CTR](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1229).png?raw=true) |
| **Age & Gender Demographics Breakdown** | ![Demographics Breakdown](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1230).png?raw=true) |
| **Geographic Revenue Distribution Map** | ![Geographic Map](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1231).png?raw=true) |
| **Audience Segment Performance Treemap** | ![Audience Treemap](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1232).png?raw=true) |
| **Mobile vs Desktop Device Breakdown** | ![Device Breakdown](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1240).png?raw=true) |
| **Page 2 Final Production State** | ![Page 2 Final](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

---

## ⚙️ Technical UI/UX Specifications & Close-Ups

<details>
<summary>🔍 Click to view design close-ups, navigation logic, and conditional formatting setups</summary>

| Technical Component | Screenshot Reference | Description |
| :--- | :---: | :--- |
| **Header Navigation & Page Tabs** | ![Screenshot 1233](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1233).png?raw=true) | Native button navigation with custom dark state fills (`#1E293B` default, `#0052FF` active). |
| **Dark Theme Canvas Styling** | ![Screenshot 1234](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1234).png?raw=true) | Canvas background set to `#0B0F19`, containers to `#1E293B`, and text to `#FFFFFF`. |
| **Callout Formatting & Decimals** | ![Screenshot 1235](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1235).png?raw=true) | Standardized decimal formatting (`$6.67M`, `4.29 ROAS`) across top KPI cards and matrix values. |
| **Matrix Conditional Formatting** | ![Screenshot 1236](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1236).png?raw=true) | Applied in-line data bars (`#0052FF`) to matrix columns for immediate visual gradient analysis. |
| **Slicer & Filter Synchronization** | ![Screenshot 1237](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1237).png?raw=true) | Synchronized slicers ensuring campaign filter selections propagate across Page 1 and Page 2. |
| **Matrix Tooltip Configuration** | ![Screenshot 1238](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1238).png?raw=true) | Custom hover tooltips providing detailed conversion metrics per ad asset without cluttering grids. |
| **Placement Axis Alignment** | ![Screenshot 1239](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1239).png?raw=true) | Sorted horizontal bar layout for placement CTR comparison with standardized percentages. |

</details>

---

## 📈 Strategic Business Impact & Insights

* **ROAS Optimization**: Real-time identification of low-ROAS campaigns enables immediate re-allocation of ad spend to high-performing formats (e.g., Video assets in Instagram Reels).
* **Creative Fatigue Alerts**: CTR % monitoring on Page 2 flags decaying static visual assets before Customer Acquisition Costs (CPA) inflate.
* **Placement Spend Efficiency**: Pinpoints placements with high impression volumes but low click conversions (e.g., Audience Network vs. Facebook Feed), helping optimize bidding strategies.
* **Target Audience Precision**: Isolates peak converting demographic cohorts (e.g., Male 25-34), minimizing wasted ad spend on non-converting age brackets.
