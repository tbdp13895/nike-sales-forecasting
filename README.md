👟 Nike Sales Forecasting & Marketing Analytics
Analysis of Nike's U.S. retail sales data to uncover regional and product performance patterns, segment customers, and forecast future monthly revenue — with the goal of informing data-driven marketing and pricing strategy.

📌 Project Overview
Nike sells across five U.S. regions through multiple retail partners and sales channels (in-store, online, outlet). This project asks: which regions, products, and channels are actually driving sales — and how can that shape marketing and pricing decisions going forward?

The analysis combines exploratory data analysis, customer/region segmentation, and time-series forecasting to turn a raw transaction log into concrete, actionable recommendations.

🎯 Objectives
Identify top- and bottom-performing regions, products, states, and sales methods
Segment regions and retailers (via K-Means clustering and RFM analysis) to enable targeted marketing
Quantify how price per unit relates to sales volume and revenue
Forecast future monthly sales using Meta's Prophet model and evaluate forecast accuracy
Translate findings into concrete marketing and pricing recommendations
🗂️ Repository Structure
nike-sales-forecasting/
├── data/                     # Nike_Dataset.csv — raw sales transaction data
├── _FINAL__Nike_analysis.ipynb  # Main analysis & forecasting notebook (Jupyter)
├── other/slides/              # Summary presentation (PowerPoint)
└── README.md
📊 Dataset
Source: Nike Dataset.csv — ~9,300 retail sales transactions

Column	Description
invoice_date	Date of the sales transaction
product	Nike product category (e.g., Men's Street Footwear, Women's Apparel)
region	U.S. sales region (West, Northeast, Southeast, South, Midwest)
retailer	Retail partner (e.g., Foot Locker, Walmart, Sports Direct)
sales_method	Channel — In-store, Online, or Outlet
state	U.S. state where the sale occurred
price_per_unit	Price per unit sold
total_sales	Total revenue from the transaction
units_sold	Number of units sold
🔍 Methodology
1. Data Preparation & Cleaning Standardized column names, checked for missing values and duplicates, and converted invoice_date to a proper datetime type.

2. Exploratory Data Analysis Aggregated sales over time, by region, and by sales method to establish a baseline view of overall performance and channel mix.

3. Regional Deep-Dive For each of the five regions (West, Northeast, Southeast, South, Midwest), analyzed monthly sales trends, top/bottom products, top/bottom sales methods, and top/bottom states.

4. Customer & Region Segmentation

K-Means clustering on total sales, units sold, and average price per unit (optimal cluster count selected via silhouette score) to group regions into performance tiers.
RFM analysis (Recency, Frequency, Monetary) on retailers to classify them into segments such as Champions, Loyal, Potential, and At-Risk.
5. Pricing & Product Analysis Examined the correlation between price per unit and total sales, and ranked products into performance quartiles to flag candidates for promotion vs. discounting/phase-out.

6. Forecasting Built a monthly sales forecasting model using Prophet, holding out the last 6 months as a test set.

Metric	Result
MAE	~$101,050
RMSE	~$116,019
MAPE	~35.96%
The model captures the overall upward trend in Nike's monthly sales, with larger errors around irregular spike periods (e.g., Sep–Oct), suggesting sales are influenced by promotions and events not captured by a pure time-series model.

💡 Key Findings & Business Recommendations
Augment forecasting with business events — sales spikes correlate with promotions, product launches, and campaigns that aren't in the historical time series alone; tracking these as features would sharpen forecasts.
Build region-level forecasting models — regional performance varies enough that one model per region is likely to outperform a single national model.
Tier pricing and promotion strategy by product quartile — apply discount/bundle strategies to bottom-25% performers and prioritize marketing spend on top performers.
Prioritize retention for At-Risk retailer segments identified via RFM, while continuing to nurture Champions/Loyal accounts.
🛠️ Tech Stack
Python: pandas, numpy
Visualization: matplotlib, seaborn
Machine Learning: scikit-learn (K-Means, StandardScaler)
Forecasting: Prophet
Environment: Jupyter Notebook
🚀 Getting Started
git clone https://github.com/tbdp13895/nike-sales-forecasting.git
cd nike-sales-forecasting
pip install pandas numpy matplotlib seaborn scikit-learn prophet
jupyter notebook
📁 Deliverables
Analysis notebook (_FINAL__Nike_analysis.ipynb) — full EDA, segmentation, pricing analysis, and Prophet forecasting workflow
Presentation — executive summary of findings and recommendations (other/slides/)
📬 Contact
Questions or feedback are welcome — feel free to open an issue or reach out via GitHub.
