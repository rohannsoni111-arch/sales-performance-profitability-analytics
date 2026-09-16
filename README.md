# Sales Performance & Profitability Analytics

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458.svg)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.5%2B-11557c.svg)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.12%2B-3776ab.svg)](https://seaborn.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

An end-to-end Data Analytics project analyzing global transactional sales performance, revenue distribution, operating costs, and net profitability across regions, product categories, distribution channels, and sales representatives.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Objectives](#objectives)
- [Dataset Overview](#dataset-overview)
- [Tools & Technologies](#tools--technologies)
- [Project Structure](#project-structure)
- [Analysis Performed](#analysis-performed)
- [Key Insights](#key-insights)
- [Visualizations Showcase](#visualizations-showcase)
- [How to Run](#how-to-run)
- [Results Summary](#results-summary)
- [Future Improvements](#future-improvements)
- [License](#license)

---

## 📖 Overview
Understanding sales dynamics and profitability margins is critical for commercial growth and resource allocation. This project processes a dataset of 1,000 sales transactions across 2025 to evaluate gross revenue, operating costs, net profit, and profit margins.

Through systematic data cleaning, exploratory data analysis (EDA), and multivariate visual breakdown, this repository uncovers key profitability drivers, top sales channels, high-performing product lines, and geographic market leaders.

---

## 🎯 Objectives
- **Data Hygiene & Preprocessing**: Convert currency/percentage string formatted data into clean numerical types and parse temporal features.
- **Profitability & Cost Analysis**: Compute gross revenue, cost of goods sold, net profit, and profit margins.
- **Segmented Analysis**: Evaluate performance metrics sliced by **Region**, **Country**, **Category**, **Product**, **Channel**, and **Sales Representative**.
- **Visual Analytics**: Generate publication-ready visualizations saved automatically to `outputs/figures/`.
- **Strategic Insights**: Provide executive recommendations based on empirical findings.

---

## 📊 Dataset Overview
The project uses `data/44.csv` containing 1,000 sales records from **Jan 1, 2025 to Dec 31, 2025**.

| Column | Data Type | Description |
| :--- | :--- | :--- |
| `Order Date` | Datetime | Date of order placement |
| `Region` | Category | Geographic region (North, South, East, West) |
| `Country` | String | Customer country |
| `Category` | Category | Merchandise category (Home & Kitchen, Office, Apparel, Electronics) |
| `Product` | String | Product name |
| `Sales Rep` | String | Assigned sales representative |
| `Channel` | Category | Sales channel (Online, Retail Store, Wholesale) |
| `Units Sold` | Integer | Quantity of units sold |
| `Unit Price` | Float | Price per single unit ($) |
| `Unit Cost` | Float | Cost per single unit ($) |
| `Revenue` | Float | Gross revenue ($) |
| `Cost` | Float | Total order cost ($) |
| `Profit` | Float | Net profit ($) |
| `Margin %` | Float | Profit margin percentage (%) |

---

## 🛠 Tools & Technologies
- **Python 3.10+**: Core programming language.
- **Pandas**: Data manipulation, cleaning, and aggregation.
- **NumPy**: Numerical computations.
- **Matplotlib**: Core plotting engine for custom data visualizations.
- **Seaborn**: Statistical graphics and styled visual layouts.
- **Jupyter Notebook**: Interactive execution environment.

---

## 📁 Project Structure
```
Sales-Performance-Profitability-Analytics/
│
├── data/
│   └── 44.csv                             # Raw sales dataset
│
├── notebooks/
│   └── Sales_Performance_Profitability_Analysis.ipynb   # Main Jupyter Analysis Notebook
│
├── outputs/
│   ├── figures/                           # Exported high-resolution PNG charts
│   └── reports/                           # Text and summary analytics reports
│
├── README.md                              # Comprehensive project documentation
├── requirements.txt                       # Python dependencies
├── .gitignore                             # Ignored runtime and temporary files
└── LICENSE                                # MIT Open-Source License
```

---

## 🔬 Analysis Performed
1. **Data Preprocessing**:
   - Stripped currency characters (`$`, `,`) and converted `Unit Price`, `Unit Cost`, `Revenue`, `Cost`, `Profit` to numeric float values.
   - Converted `Margin %` string formatted figures to numeric floats.
   - Cast `Order Date` into datetime and extracted `Year`, `Month`, `Month Name`, `Day`, and `Day Name`.
   - Verified 0 null values and removed any duplicate rows.
2. **Descriptive EDA**: Computed overall aggregate stats, minimums, maximums, standard deviations, and quartiles.
3. **Sales & Volume Analysis**: Evaluated total units sold (21,355 units) and order frequency.
4. **Revenue & Profit Breakdown**: Computed overall gross revenue ($1,539,751.45) and overall profit ($755,860.48).
5. **Dimensional Segmentations**: Sliced performance across Region, Product Category, Distribution Channel, and Sales Representatives.

---

## 💡 Key Insights
All metrics are calculated directly from the dataset:

- 📈 **Total Financial Overview**:
  - **Gross Revenue**: **$1,539,751.45**
  - **Total Cost**: **$783,890.97**
  - **Net Profit**: **$755,860.48**
  - **Overall Profit Margin**: **49.09%**
  - **Total Units Sold**: **21,355 units**
- 🌍 **Top Geographic Region**:
  - **South** led all regions in revenue (**$434,395.49**) and net profit (**$218,807.00**).
  - **North** followed second with **$394,483.24** in revenue and **$191,773.03** in profit.
- 📦 **Category & Product Leaders**:
  - **Home & Kitchen** generated the highest gross revenue (**$454,309.59**).
  - **Office** generated the highest net profit (**$207,714.30**).
  - **Desk Chair** was the single most profitable item (**$139,953.60** profit).
- 🛒 **Sales Channels**:
  - **Online Channel** generated **$802,328.49** (52.1% of revenue) and **$391,374.02** in profit.
  - **Retail Store** contributed **$482,622.42** (31.3% of revenue).
  - **Wholesale** contributed **$254,800.54** (16.5% of revenue).
- 👤 **Sales Representative Performance**:
  - **K. Ivanova** was the top-performing sales rep with **$243,152.03** in gross revenue.

---

## 🖼 Visualizations Showcase
The project generates 20+ analytical figures saved in `outputs/figures/`, including:
- `revenue_by_region.png` & `profit_by_region.png`
- `revenue_by_category.png` & `profit_by_category.png`
- `profit_by_product.png` (Horizontal Bar Chart)
- `daily_revenue_trend.png` (Time-Series Plot)
- `revenue_share_channel.png` (Pie Chart) & `revenue_share_category.png` (Donut Chart)
- `revenue_distribution.png` (Histogram) & `profit_distribution.png` (KDE Plot)
- `revenue_vs_profit.png` (Scatter & Regression Plots)
- `revenue_heatmap_region_category.png` (Heatmap)
- `revenue_stacked_region_category.png` (Stacked Bar Chart)

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/Sales-Performance-Profitability-Analytics.git
cd Sales-Performance-Profitability-Analytics
```

### 2. Create a Virtual Environment
```bash
# On Windows
python -m venv .venv
.venv\Scripts\activate

# On macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Start Jupyter Notebook
```bash
jupyter notebook
```

### 5. Open and Run the Notebook
1. Navigate to the `notebooks/` directory.
2. Open `Sales_Performance_Profitability_Analysis.ipynb`.
3. Select **Kernel -> Restart & Run All** to execute all analysis cells from start to finish.

---

## 📈 Results Summary
- The business exhibits healthy unit economics with a ~49.1% profit margin.
- Online distribution is the primary growth engine (52.1% revenue share).
- Regional expansion in South and North accounts for over 53% of overall corporate net profit.

---

## 🔮 Future Improvements
*Features planned for future iterations:*
- 📊 **Interactive Dashboards**: Build an interactive Power BI / Tableau dashboard for executive drill-downs.
- 🤖 **Predictive Sales Modeling**: Implement ARIMA/Prophet time-series forecasting for quarterly revenue prediction.
- ⚡ **Automated ETL Pipeline**: Build automated pipeline scripts to ingest incremental transaction batches.
- 🧪 **Statistical Hypothesis Testing**: Conduct ANOVA testing across channels and regions to assess margin variance.

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).
