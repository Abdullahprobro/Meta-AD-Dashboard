# Meta Ads Executive & Operational Analytics Dashboard

An end-to-end Power BI analytics solution designed to evaluate Meta (Facebook & Instagram) advertising performance across executive and operational levels. This multi-page dashboard bridges high-level financial reporting (**Page 1: Financial & Executive Overview**) with granular operational marketing intelligence (**Page 2: Operational, Creative & Placement Deep-Dive**) to optimize budget allocation, detect creative fatigue, and maximize return on ad spend (ROAS).

---

## 📸 Dual-Page Dashboard Overview

| Page 1: Financial & Executive Overview | Page 2: Creative & Placement Deep-Dive |
| :---: | :---: |
| ![Page 1 Executive Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) | ![Page 2 Deep Dive Final](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

### 📹 Video Walkthrough & Interactive Demo
* 🎥 **[Watch Full Dashboard Demo Video](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Meta%20ad%20dashboard%20(1)%20(1).mp4)**

---

## 🛠️ Tech Stack

| Technology | Role & Application |
| :--- | :--- |
| **Power BI Desktop** | Multi-page dashboard construction, dark theme UI/UX (`#0B0F19` canvas, `#1E293B` containers), and native button navigation. |
| **DAX (Data Analysis Expressions)** | Custom financial, ROI, and conversion metrics (`ROAS`, `CPA`, `CTR %`, `CPC`, `Total Spend`, `Total Revenue`). |
| **Power Query** | Data extraction, data type enforcement, dimensional modeling, and custom column generation. |
| **Python (`pandas`, `numpy`)** | Synthetic ad data generation, dataset cleaning, mock Meta Graph API data modeling, and pre-ingestion validation. |
| **Git / GitHub** | Project version control, documentation, and portfolio hosting. |

---

## 🐍 Python's Role in the Project

Python served as the core data engine for preparing, cleaning, and structuring the analytics model prior to loading into Power BI:

1. **Synthetic Data Generation & Distribution**:
   * Used Python's `pandas` and `numpy` libraries to model realistic multi-channel advertising datasets mimicking Meta Ads Manager API exports.
   * Generated proportional distributions for impressions, clicks, spend, revenue, conversions, age/gender demographics, device platforms, and placement types.
2. **Data Pipeline Cleaning & Transformation**:
   * Automated missing value resolution, date parsing, and currency alignment via Pandas workflows.
   * Built strict relationship validation scripts to prevent circular dependencies and cyclic loops across Star Schema tables.
3. **API Data Ingestion Simulation**:
   * Simulated automated data extraction pipelines (emulating Meta Graph API JSON responses) to structure raw payload outputs into relational CSV tables (`ADS_DATA`, `CAMPAIGNS`, `AD_CREATIVES`).

---

## 💾 Data Architecture & Star Schema Model

The data structure follows a **Star Schema** designed for maximum query speed and seamless DAX filter propagation.

![Star Schema Data Model](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1241).png?raw=true)

* **Fact Table (`ADS_DATA`)**: Contains core transactional ad performance records (Spend, Revenue, Clicks, Impressions, Conversions, Placements, Devices, Demographics, DateKey).
* **Dimension Tables**:
  * `CAMPAIGNS`: Campaign identifiers, strategy names, and budget allocations.
  * `AD_CREATIVES`: Asset titles, creative types (Static, Video, Carousel), and visual tags.
  * `DateTable`: Continuous date hierarchy for time-intelligence reporting.

* **ETL Pipeline**: Power Query transformation logic applied across all incoming datasets:
![Power Query Workflow](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1242).png?raw=true)

---

## 📌 Feature Highlights

### 1. Business Problem
Marketing leadership and performance marketers face two core operational bottlenecks:
* **Executives** lack instant clarity on top-line business ROI, total ad spend, and consolidated revenue generation.
* **Media Buyers** lack actionable operational visibility to pinpoint fatiguing ad creative, underperforming placements (Reels vs. Feed), and inefficient audience segments.

### 2. Goal of the Dashboard
To build a dark-themed, 2-page interactive intelligence portal enabling **high-level financial evaluation on Page 1** and **granular creative and audience optimization on Page 2**.

---

## 📖 Deep-Dive Page-by-Page Walkthrough

### 📊 Page 1: Executive & Financial Overview
Designed for executive leadership requiring real-time insights into campaign profitability and top-line marketing ROI.

![Page 1 Full Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1194).png?raw=true)

#### Key Visual Components on Page 1:
1. **Financial KPI Grid**:
   * Displays core conversion metrics: `Clicks` (4M), `Revenue` ($6.67M), `CPC` ($0.36), `Conversions` (55K), `CPA` ($28.31), and `CTR %` (1.72%).
   * ![KPI Grid Detail](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1195).png?raw=true)
2. **Campaign Ad Spend and Revenue (Clustered Bar Chart)**:
   * Ranks campaign effectiveness by placing spend side-by-side with generated revenue.
   * ![Campaign Spend vs Revenue](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1196).png?raw=true)
3. **Daily Ad Spend and Revenue Trend (Area Chart)**:
   * Continuous time-series area visualization tracking seasonal revenue spikes against ad spend over time.
   * ![Daily Spend & Revenue Trend](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1197).png?raw=true)
4. **Executive Summary Callout Cards**:
   * Dedicated high-contrast cards highlighting `Total Revenue` ($6.67M), `Overall ROAS` (4.29), and `Total Spend` ($1.56M).
   * ![Executive Summary Cards](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1198).png?raw=true)
5. **Interactive Slicer View**:
   * Full dynamic context filtering across campaigns and date ranges.
   * ![Page 1 Filtered View](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1199).png?raw=true)

---

### 🎯 Page 2: Operational, Creative & Placement Deep-Dive
Designed specifically for media buyers and marketing teams to evaluate creative performance, demographic efficiency, and placement distribution.

![Page 2 Production View](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true)

#### Key Visual Containers on Page 2:
1. **Creative Performance Breakdown (Matrix Visual)**:
   * **Fields**: `AD_CREATIVES[Ad_Name]`, `AD_CREATIVES[Creative_Type]`, `ADS_DATA[Total Spend]`, `ADS_DATA[CTR %]`, `ADS_DATA[Total Conversions]`, `ADS_DATA[ROAS]`.
   * Features in-cell conditional data bars for `ROAS` and `CTR %` to instantly spot fatigue in static image assets vs. high-performing video creatives.
   * ![Creative Matrix Breakdown](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1227).png?raw=true)
2. **Platform Breakdown (Donut Chart)**:
   * **Fields**: `ADS_DATA[Platform]`, `ADS_DATA[Total Spend]`.
   * Evaluates overall budget distribution across Facebook (45%), Instagram Reels/Stories (40%), and Audience Network (15%).
   * ![Platform Breakdown Donut](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1228).png?raw=true)
3. **Placement Performance (Horizontal Bar Chart)**:
   * **Fields**: `ADS_DATA[Placement]`, `ADS_DATA[CTR %]`.
   * Compares click-through efficiency across Facebook Feed, Instagram Reels, FB Stories, and IG Explore.
   * ![Placement CTR Bar Chart](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1229).png?raw=true)
4. **Spend by Key Demographics (Clustered Column Chart)**:
   * **Fields**: `ADS_DATA[Age]`, `ADS_DATA[Gender]`, `ADS_DATA[Total Spend]`.
   * Identifies top conversion volume and spend across age brackets (25-34, 35-44, 18-24) and gender groups.
   * ![Demographic Breakdown](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1230).png?raw=true)
5. **Geographic Revenue Distribution (Bubble Map)**:
   * **Fields**: `ADS_DATA[State/Region]`, `ADS_DATA[Total Revenue]`.
   * Bubble density visualizes top revenue-generating regional markets.
   * ![Geographic Map](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1231).png?raw=true)
6. **Audience Segment Performance (Treemap)**:
   * **Fields**: `ADS_DATA[Audience Segment]`, `ADS_DATA[Total Spend]`, `ADS_DATA[ROAS]`.
   * Evaluates retargeting lists vs. lookalike audiences.
   * ![Audience Treemap](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1232).png?raw=true)

---

## 🛠️ Technical Implementation & UI/UX Specifications

| UI / UX Feature | Screenshot Reference | Implementation & Configuration Details |
| :--- | :---: | :--- |
| **Header Navigation & Page Tabs** | ![Screenshot 1233](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1233).png?raw=true) | Native button navigation with custom dark state fills (`#1E293B` default, `#0052FF` active). |
| **Dark Theme Canvas Styling** | ![Screenshot 1234](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1234).png?raw=true) | Canvas background set to `#0B0F19`, containers to `#1E293B`, and primary text to `#FFFFFF`. |
| **Callout Formatting & Precision** | ![Screenshot 1235](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1235).png?raw=true) | Standardized decimal formatting (`$6.67M`, `4.29 ROAS`) across top KPI cards and matrix fields. |
| **Matrix Conditional Formatting** | ![Screenshot 1236](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1236).png?raw=true) | Applied conditional data bars (`#0052FF`) to matrix columns for immediate visual gradient analysis. |
| **Slicer & Campaign Filter Sync** | ![Screenshot 1237](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1237).png?raw=true) | Synchronized slicers ensuring filter selections propagate seamlessly across both Page 1 and Page 2. |
| **Matrix Tooltip Configuration** | ![Screenshot 1238](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1238).png?raw=true) | Custom hover tooltips providing detailed conversion metrics per ad asset without cluttering the main grid. |
| **Placement Axis Formatting** | ![Screenshot 1239](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1239).png?raw=true) | Sorted horizontal bar layout for placement CTR comparison with standardized percentages. |
| **Device Breakdown Formatting** | ![Screenshot 1240](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1240).png?raw=true) | Clustered column visualization isolating Mobile vs. Desktop conversion distributions. |

---

## 📈 Strategic Business Impact & Insights

* **ROAS Optimization**: Real-time identification of low-ROAS campaigns enables immediate re-allocation of ad spend to high-performing formats (e.g., Video assets in Instagram Reels).
* **Creative Fatigue Alerts**: CTR % monitoring on Page 2 flags decaying static visual assets before Customer Acquisition Costs (CPA) inflate.
* **Placement Spend Efficiency**: Pinpoints placements with high impression volumes but low click conversions (e.g., Audience Network vs. Facebook Feed), helping optimize bidding strategies.
* **Target Audience Precision**: Isolates peak converting demographic cohorts (e.g., Male 25-34), minimizing wasted ad spend on non-converting age brackets.
