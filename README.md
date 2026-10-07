# Meta Ads Executive & Operational Analytics Dashboard

An end-to-end Power BI analytics solution designed to evaluate Meta (Facebook & Instagram) advertising performance across executive and operational levels. This multi-page dashboard bridges high-level financial reporting (**Page 1: Financial & Executive Overview**) with granular marketing intelligence (**Page 2: Creative & Placement Deep-Dive**) to optimize ad spend allocation, detect creative fatigue, and maximize return on ad spend (ROAS).

---

## 📸 Dual-Page Dashboard Overview

| Page 1: Executive & Financial View | Page 2: Operational & Creative Deep-Dive |
| :---: | :---: |
| ![Executive Overview Page 1](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) | ![Creative Deep Dive Page 2](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

### 📹 Video Walkthrough & Demo
* **[Click Here to Watch the Full Multi-Page Interactive Demo Video](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Meta%20ad%20dashboard%20(1)%20(1).mp4)**

---

## 🛠️ Tech Stack

| Technology | Role & Application |
| :--- | :--- |
| **Power BI Desktop** | Multi-page report development, dark theme UI/UX (`#0B0F19` canvas, `#1E293B` containers), and native button navigation. |
| **DAX (Data Analysis Expressions)** | Calculated measures for financial ROI and engagement performance (`ROAS`, `CPA`, `CTR %`, `CPC`, `Total Spend`, `Total Revenue`). |
| **Power Query** | ETL processing, data cleansing, dimensional modeling, and field mappings across fact/dimension tables. |
| **Python (`pandas`, `numpy`)** | Synthetic ad performance dataset generation, Meta Graph API response modeling, missing value handling, and pre-ingestion validation. |
| **Git / GitHub** | Project version control, documentation, and portfolio hosting. |

---

## 🐍 Python's Role in the Analytics Engine

Python served as the core data engine for structuring and enriching the underlying dataset prior to loading into Power BI:

1. **Multi-Channel Data Simulation**:
   * Generated realistic, multi-dimensional advertising data mimicking raw Meta Ads Manager CSV/API exports.
   * Constructed balanced distributions across impressions, clicks, spend, revenue, conversions, demographics, platforms, and placement types.
2. **Data Pipeline Cleansing & Transformation**:
   * Programmatically resolved missing values, parsed date hierarchies, and harmonized currency formats via `pandas`.
   * Executed strict relationship validation checks to ensure clean primary/foreign key mappings across tables without cyclic dependencies.
3. **API Data Extraction Simulation**:
   * Simulated an automated ETL pipeline transforming raw nested JSON payloads (emulating Meta Graph API endpoints) into structured, tabular dimension and fact files.

---

## 💾 Data Architecture & Star Schema

The project utilizes a **Star Schema** to ensure optimal query execution speed and DAX filter context flow:

* **Fact Table (`ADS_DATA`)**: Stores core transactional advertising metrics (Spend, Revenue, Clicks, Impressions, Conversions, Demographics, Placement, Platform, DateKey).
* **Dimension Tables**:
  * `CAMPAIGNS`: Campaign names, objectives, and budget allocations.
  * `AD_CREATIVES`: Creative titles, ad format types (Static, Video, Carousel), and asset metadata.
  * `DateTable`: Continuous calendar table supporting Time Intelligence calculations.

---

## 📌 Feature Highlights

### 1. Business Problem
Marketing leadership and performance marketers face two key challenges:
* **Executives** lack immediate clarity on overall campaign profitability and bottom-line revenue impact.
* **Media Buyers** lack actionable operational visibility to identify which specific creatives are fatiguing, which demographics are converting, and which placements (e.g., Reels vs. Feed) offer the highest CTR.

### 2. Goal of the Dashboard
To engineer an interactive, dark-themed 2-page analytics portal that enables **instant high-level financial evaluation on Page 1** and **granular creative and audience optimization on Page 2**.

---

## 📖 Comprehensive Page-by-Page Walkthrough

### 📊 Page 1: Executive & Financial Overview
Designed for high-level stakeholders requiring real-time insights into total spend, revenue generation, and overall campaign effectiveness.

![Page 1 Overview Full](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1194).png?raw=true)

* **Top Financial KPI Grid**: 6 synchronized KPI cards displaying key metrics: `Clicks` (4M), `Revenue` ($6.67M), `CPC` ($0.36), `Conversions` (55K), `CPA` ($28.31), and `CTR %` (1.72%).
* **Campaign Spend vs. Revenue Bar Chart**: Ranks campaign performance to immediately isolate top revenue-generating campaigns against their allocated ad budgets.
* **Daily Ad Spend & Revenue Area Chart**: Continuous time-series line/area visualization tracking seasonal spikes, scale phases, and revenue trends.
* **Executive Callout Summary Cards**: Prominently highlights consolidated totals for `Total Revenue` ($6.67M), `Overall ROAS` (4.29), and `Total Spend` ($1.56M).

---

### 🎯 Page 2: Operational, Audience & Creative Deep-Dive
Designed for media buyers and creative teams to analyze creative efficiency, demographic traction, and placement distribution.

![Page 2 Deep Dive Full](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true)

* **Container 1: Ad Creative Performance Breakdown (Matrix)**
  * **Fields**: `AD_CREATIVES[Ad_Name]`, `AD_CREATIVES[Creative_Type]`, `ADS_DATA[Total Spend]`, `ADS_DATA[CTR %]`, `ADS_DATA[Total Conversions]`, `ADS_DATA[ROAS]`.
  * **Function**: Features conditional data bars on `ROAS` and `CTR %` to instantly highlight top-performing ad concepts and detect fatiguing static images or video assets.
* **Container 2: Spend by Key Demographics (Horizontal Bar Chart)**
  * **Fields**: `ADS_DATA[Age]`, `ADS_DATA[Gender]`, `ADS_DATA[Total Spend]`.
  * **Function**: Maps advertising spend and conversion volume across age brackets and gender segments to optimize target audience targeting.
* **Container 3: Placement Performance (Clustered Bar Chart)**
  * **Fields**: `ADS_DATA[Placement]` (FB Feed, IG Reels, FB Story, IG Explore), `ADS_DATA[CTR %]`.
  * **Function**: Evaluates click-through efficiency across distinct ad placements to identify low-cost conversion opportunities.
* **Container 4: Platform Distribution (Donut Chart)**
  * **Fields**: `ADS_DATA[Platform]` (Facebook, Instagram, Audience Network), `ADS_DATA[Total Spend]`.
  * **Function**: Visualizes overall budget distribution across Meta platforms to guide platform-level budget reallocations.

---

## 🖼️ Complete Visual Gallery & Detailed Screenshot Index

### Executive View (Page 1 Screenshots)

| Feature / Visual | Screenshot Preview |
| :--- | :--- |
| **Page 1 Executive Layout** | ![Screenshot 1193](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) |
| **KPI Grid & Navigation Header** | ![Screenshot 1195](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1195).png?raw=true) |
| **Campaign Revenue vs Spend** | ![Screenshot 1196](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1196).png?raw=true) |
| **Daily Spend & Revenue Trend** | ![Screenshot 1197](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1197).png?raw=true) |
| **Executive Card Metrics** | ![Screenshot 1198](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1198).png?raw=true) |

---

### Creative & Placement Deep-Dive (Page 2 Screenshots)

| Feature / Visual | Screenshot Preview |
| :--- | :--- |
| **Page 2 Production View** | ![Screenshot 1243](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |
| **Creative Matrix Breakdown** | ![Screenshot 1227](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1227).png?raw=true) |
| **Platform Breakdown (Donut)** | ![Screenshot 1228](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1228).png?raw=true) |
| **Placement CTR % Analysis** | ![Screenshot 1229](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1229).png?raw=true) |
| **Demographics Distribution** | ![Screenshot 1230](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1230).png?raw=true) |
| **Geographic Revenue Distribution** | ![Screenshot 1231](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1231).png?raw=true) |
| **Audience Segment Treemap** | ![Screenshot 1232](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1232).png?raw=true) |

---

<details>
<summary>🔍 Click to expand build details & close-up UI components</summary>

| Build Stage / Feature | Screenshot |
| :--- | :--- |
| **Navigation & Header Alignment** | ![Screenshot 1233](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1233).png?raw=true) |
| **Canvas & Theme Settings** | ![Screenshot 1234](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1234).png?raw=true) |
| **Callout Formatting & Decimals** | ![Screenshot 1235](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1235).png?raw=true) |
| **Matrix Conditional Formatting** | ![Screenshot 1236](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1236).png?raw=true) |
| **Filter & Slicer Setup** | ![Screenshot 1237](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1237).png?raw=true) |
| **Tooltip Configurations** | ![Screenshot 1238](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1238).png?raw=true) |
| **Placement Axis Formatting** | ![Screenshot 1239](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1239).png?raw=true) |
| **Device Breakdown Formatting** | ![Screenshot 1240](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1240).png?raw=true) |
| **Star Schema Data Model View** | ![Screenshot 1241](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1241).png?raw=true) |
| **Power Query Transformations** | ![Screenshot 1242](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1242).png?raw=true) |
| **Final Multi-Page Production Model** | ![Screenshot 1243](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

</details>

---

## 📈 Strategic Business Impact

* **ROAS Optimization**: Real-time identification of low-ROAS campaigns enables immediate re-allocation of budget to high-performing channels (e.g., Instagram Reels).
* **Creative Renewal Alerts**: CTR % monitoring on Page 2 flags decaying ad creatives before acquisition costs spike.
* **Placement Spend Efficiency**: Prevents wasted ad spend by identifying placements with high impressions but low conversion rates.
* **Demographic Precision**: Informs future audience targeting strategies by isolating the age and gender demographics driving the highest lifetime value.

---

## 🎨 In-Depth Audience & Creative Performance Analysis (Page 2 Operational Deep-Dive)

Page 2 serves as the primary operational workspace for growth marketers, performance media buyers, and creative strategists. Below is a detailed breakdown of the visualizations, configurations, and technical setup driving Page 2.

### 🖼️ Complete Page 2 Production View
![Page 2 Production View](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true)

---

### 1. Ad Creative Performance Breakdown & Fatigue Detection Matrix
![Creative Matrix Breakdown](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1227).png?raw=true)

* **Visual Matrix**: Evaluates ad-level creative concepts (`Ad Name`, `Creative Type`, `Spend`, `CTR %`, `Conversions`, `ROAS`).
* **Conditional Formatting Configuration**:
  ![Matrix Conditional Formatting](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1236).png?raw=true)
  * In-cell dynamic data bars (`#0052FF`) applied directly to `ROAS` and `CTR %` allow media buyers to quickly distinguish top-performing video assets from fatiguing static graphics.
* **Custom Tooltip Integration**:
  ![Tooltip Configurations](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1238).png?raw=true)
  * Hovering over any creative row displays custom secondary metrics (Impressions, CPA, Cost Per Click) without overcrowding the primary report grid.

---

### 2. Slicer & Cross-Filtering Synchronization Setup
![Filter & Slicer Setup](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1237).png?raw=true)

* **Cross-Filtering Logic**: Synchronized slicers across both pages ensure that selecting a specific campaign or date range on Page 1 updates all demographic, creative, and placement metrics on Page 2 automatically.

---

### 3. Demographic & Callout Formatting Breakdown
![Demographics Distribution](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1230).png?raw=true)

* **Audience Analytics**: Maps spend and conversions across age brackets (`18-24`, `25-34`, `35-44`, `45-54`) and gender classifications.
* **Precision Formatting**:
  ![Callout Formatting & Decimals](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1235).png?raw=true)
  * Standardized decimal formatting ensures consistent KPI card displays and clean visual alignment across all device screens.

---

### 4. Placement Axis & Efficiency Analysis
![Placement Axis Formatting](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1239).png?raw=true)

* **Placement CTR Breakdown**: Evaluates engagement efficiency across Facebook Feed, Instagram Reels, FB Stories, and IG Explore.
* **Axis & Label Standardization**: Custom-sorted horizontal bar layout with standardized percentage formatting to quickly flag low-performing placements.

---

### 5. Backend Architectural Foundation for Page 2

| Data Model Relationship (Star Schema) | Power Query Transformation Pipeline |
| :---: | :---: |
| ![Star Schema Model](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1241).png?raw=true) | ![Power Query Setup](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1242).png?raw=true) |
| Single-direction 1:N filter context propagation from `AD_CREATIVES` and `CAMPAIGNS` into `ADS_DATA`. | Data typing, column cleanup, and relational key definitions in Power Query. |
