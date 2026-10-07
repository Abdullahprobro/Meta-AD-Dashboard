# Meta Ads Executive & Operational Analytics Dashboard

An end-to-end Power BI analytics solution designed to evaluate Meta (Facebook & Instagram) advertising performance. This dashboard bridges high-level financial reporting (Page 1: Financial & Executive Overview) with operational marketing intelligence (Page 2: Creative & Placement Deep-Dive) to maximize return on ad spend (ROAS) and optimize campaign performance.

---

## 📸 Dashboard Preview

| Page 1: Financial & Executive View | Page 2: Operational & Creative Deep-Dive |
| :---: | :---: |
| ![Executive Overview Page 1](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1193).png?raw=true) | ![Creative Deep Dive Page 2](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1225).png?raw=true) |

### 📹 Video Walkthrough & Demo
* **[Click Here to Watch the Full Dashboard Demo Video](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Meta%20ad%20dashboard%20(1)%20(1).mp4)**

---

## 🛠️ Tech Stack

| Technology | Role & Application |
| :--- | :--- |
| **Power BI Desktop** | Dashboard development, visual design, custom UI/UX dark theme (`#0B0F19`), and interactive navigation. |
| **DAX (Data Analysis Expressions)** | Custom financial and operational metrics (`ROAS`, `CPA`, `CTR %`, `CPC`, `Total Spend`, `Total Revenue`). |
| **Power Query** | Data transformation, data type enforcement, dimensional modeling, and custom column creation. |
| **Python (`pandas`, `numpy`)** | Synthetic ad data generation, dataset cleaning/wrangling, mock Meta Graph API data ingestion, and data validation. |
| **Git / GitHub** | Project version control, documentation, and portfolio hosting. |

---

## 🐍 Python's Role in the Project

Python served as the core data engine for preparing and structuring the analytics model prior to ingestion in Power BI:

1. **Synthetic Data Generation & Simulation**:
   * Used Python's `pandas` and `numpy` libraries to model realistic multi-channel advertising datasets mimicking Meta Ads Manager exports.
   * Generated proportional distributions for impressions, clicks, spend, revenue, conversions, demographics (age, gender), device types, platforms, and placements.
2. **Data Cleansing & Transformation Pipeline**:
   * Automated missing value handling, date parsing, and currency formatting via Pandas workflows.
   * Built validation checks to prevent relationship loops and ensure strict data integrity across star-schema entity relationships.
3. **API Data Extraction Simulation**:
   * Simulated automated data ingestion pipelines (emulating Meta Graph API responses) to convert raw JSON outputs into structured CSV relational tables (`ADS_DATA`, `CAMPAIGNS`, `AD_CREATIVES`).

---

## 💾 Data Source & Model Architecture

The data architecture follows a **Star Schema** to ensure fast query performance and scale efficiency:

* **Fact Table (`ADS_DATA`)**: Contains raw transactional metrics (Spend, Revenue, Clicks, Impressions, Conversions, Placements, Devices, Demographics, DateKey).
* **Dimension Tables**:
  * `CAMPAIGNS`: Campaign names, objectives, and budget allocations.
  * `AD_CREATIVES`: Ad names, creative types (Static, Video, Carousel), and asset metadata.
  * `DateTable`: Continuous date hierarchy for time-intelligence DAX functions.

---

## 📌 Feature Highlights

### 1. Business Problem
Marketing executives and media buyers often struggle to connect top-line financial metrics (total spend, revenue, overall ROAS) with granular campaign decisions (which ad visual is fatigue-prone, or which placement is burning budget). Without a unified dashboard, budget allocation across campaigns, platforms, and demographics remains reactive and inefficient.

### 2. Goal of the Dashboard
To build a dark-themed, 2-page interactive intelligence portal that allows executives to evaluate high-level business ROI in seconds, while empowering marketing managers to perform detailed creative and audience deep-dives to reduce Acquisition Costs (CPA) and increase CTR.

---

### 3. Walkthrough of Key Visuals

#### Page 1: Executive & Financial Overview
![Page 1 Overview](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1194).png?raw=true)

* **Financial KPI Grid**: Standardized KPI cards tracking core metrics (`Clicks`, `Revenue`, `CPC`, `Conversions`, `CPA`, `CTR %`).
* **Daily/Monthly Revenue & Spend Trend**: Dual-line/area chart comparing monthly ad spend against total generated revenue to identify peak seasonal performance.
* **Top-10 Campaign Performance**: Clustered horizontal bar chart displaying top campaigns ranked by spend and revenue.
* **Executive Summary Cards**: Dedicated callouts for overall `ROAS`, `Total Spend`, and `Total Revenue` formatted for quick executive review.

#### Page 2: Operational & Creative Deep-Dive
![Page 2 Deep-Dive](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1226).png?raw=true)

* **Creative Performance Breakdown (Matrix Table)**: Itemized matrix breaking down ad performance (`Ad Name`, `Creative Type`, `Spend`, `CTR %`, `Conversions`, `ROAS`) with conditional data bars to instantly spot top-performing assets.
* **Placement & Platform Breakdown**: Donut and bar charts analyzing budget distribution across platforms (Facebook, Instagram, Audience Network) and placements (Feeds, Reels, Stories).
* **Demographic & Device Distribution**: Clustered visuals breaking down conversions and spend across target age groups, genders, and device platforms (Mobile vs. Desktop).

---

## 🖼️ Complete Visual Gallery & Component Breakdown

### Executive & Financial Views (Page 1)

| View Description | Screenshot Preview |
| :--- | :--- |
| **KPI Grid & Header Navigation** | ![Screenshot 1195](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1195).png?raw=true) |
| **Campaign Revenue vs Spend Chart** | ![Screenshot 1196](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1196).png?raw=true) |
| **Daily Spend & Revenue Trend Analysis** | ![Screenshot 1197](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1197).png?raw=true) |
| **Executive Card Metrics ($6.67M Revenue)** | ![Screenshot 1198](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1198).png?raw=true) |
| **Full Page 1 Filtered View** | ![Screenshot 1199](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1199).png?raw=true) |

---

### Creative & Placement Deep-Dive Views (Page 2)

| Visual Component | Screenshot Preview |
| :--- | :--- |
| **Creative Matrix & Format Heatmap** | ![Screenshot 1227](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1227).png?raw=true) |
| **Platform Spend Distribution (Donut Chart)** | ![Screenshot 1228](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1228).png?raw=true) |
| **Placement Performance (CTR % Bar Chart)** | ![Screenshot 1229](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1229).png?raw=true) |
| **Age & Gender Demographic Breakdown** | ![Screenshot 1230](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1230).png?raw=true) |
| **Geographic Revenue Distribution Map** | ![Screenshot 1231](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1231).png?raw=true) |
| **Audience Segment Performance Treemap** | ![Screenshot 1232](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1232).png?raw=true) |

---

<details>
<summary>🔍 Click to view additional design iterations & detailed visual close-ups</summary>

| Detail View | Screenshot |
| :--- | :--- |
| **Navigation & Header Setup** | ![Screenshot 1233](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1233).png?raw=true) |
| **Dark Theme Canvas Styling** | ![Screenshot 1234](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1234).png?raw=true) |
| **Card Format & Decimal Precision** | ![Screenshot 1235](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1235).png?raw=true) |
| **Data Bar Conditional Formatting** | ![Screenshot 1236](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1236).png?raw=true) |
| **Campaign Slicer Integration** | ![Screenshot 1237](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1237).png?raw=true) |
| **Matrix Tooltip Configuration** | ![Screenshot 1238](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1238).png?raw=true) |
| **Placement CTR Alignment** | ![Screenshot 1239](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1239).png?raw=true) |
| **Mobile vs Desktop Device Breakdown** | ![Screenshot 1240](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1240).png?raw=true) |
| **Star Schema Relationship View** | ![Screenshot 1241](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1241).png?raw=true) |
| **Power Query Transformation Workflow** | ![Screenshot 1242](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1242).png?raw=true) |
| **Final Published State** | ![Screenshot 1243](https://github.com/Abdullahprobro/Meta-AD-Dashboard/blob/main/Screenshot%20(1243).png?raw=true) |

</details>

---

### 4. Business Impact & Strategic Insights

* **ROAS Maximization**: Identifies underperforming campaigns and reallocates ad spend toward top-converting formats (e.g., Video assets in Instagram Reels).
* **Creative Fatigue Detection**: Enables real-time monitoring of CTR % drops across specific ad creatives to signal when new creative assets are required.
* **Placement Optimization**: Reveals cost-per-click (CPC) variances across Facebook Feed vs. Instagram Stories, allowing media buyers to optimize bidding strategies.
* **Target Audience Precision**: Highlights high-value demographic cohorts to reduce wasted ad impressions on non-converting age/gender segments.
