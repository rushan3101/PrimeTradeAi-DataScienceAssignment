# 📊 Data Science Assignment – Web3 Trading Team
**Candidate:** Mohd Rushan  
**Project:** Relationship Between Trader Behavior and Market Sentiment (Fear vs Greed)

**Google Colab File link** : https://colab.research.google.com/drive/1K-_O0N8TgJjyZINSSm9iqs8zfOCH_m56?usp=sharing

---

## 📁 Project Structure
ds_MohdRushan/
├── notebook_1.ipynb
├── csv_files/
│   └── sentiment_summary.csv
├── outputs/
│   ├── SentimentData_1.png
│   ├── SentimentData_2.png
│   ├── TraderData_1.png
│   └── SentimentWiseAnalysis.png
├── ds_report.pdf
└── README.md
---

## 🧠 Objective
To analyze **how trading behavior (profitability, risk, volume, and leverage)** aligns or diverges from overall **market sentiment (Fear vs Greed)**.  
We aim to identify hidden trends that could guide smarter trading strategies in Web3 and crypto markets.

---

## 📊 Datasets Used

### 1. Bitcoin Market Sentiment Dataset
- **Columns:** timestamp, value, Date, classification  
- Represents the **Fear & Greed Index**, which measures market sentiment on a scale from extreme fear to extreme greed.

### 2. Historical Trader Data (Hyperliquid)
- **Columns (sample):** Account, Coin, Execution Price, Size Tokens, Size USD, Side, Timestamp, Closed PnL, Fee, Direction  
- Represents trading activity and profitability metrics of multiple traders.

---

## ⚙️ Steps Performed

### **Step 1 – Data Loading & Cleaning**
- Imported both datasets into Google Colab.  
- Checked for missing values, duplicates, and inconsistent timestamps.  
- Converted timestamps into proper datetime objects.  
- Ensured both datasets cover the same date range.

### **Step 2 – Sentiment Data EDA**
- Explored sentiment dataset using `.describe()` and `.value_counts()`.  
- Visualized the distribution of the Fear & Greed Index over time and its classification frequency.  
- Generated:
  - `SentimentData_1.jpeg` – Distribution & trend of sentiment index  
  - `SentimentData_2.jpeg` – Frequency of Fear vs Greed classifications  

### **Step 3 – Trader Data EDA**
- Basic summary of trader metrics and categorical columns.  
- Identified data structure for further analysis.  
- Generated:
  - `TraderData_1.jpeg` – Initial trader EDA visualization  

### **Step 4 – Merging and Metric Creation**
- Merged datasets on the **Date** column.  
- Created derived columns:
  - `Net_PnL = ClosedPnL - Fee`
  - `NetPnl% = (Net_PnL / SizeUSD) * 100`
  - Win/Loss flags for performance tracking.  

### **Step 5 – Sentiment-wise Analysis**
- Grouped merged data by `classification` (fear/greed).  
- Calculated:
  - Average Net PnL
  - Average Net PnL%
  - Win Rate (%)
- Visualized metrics using bar plots and boxplots.
- Generated:
  - `SentimentWiseAnalysis.jpeg` – Combined 2×2 figure summarizing all sentiment-based metrics  

---

## 🧩 Output CSV
- **`sentiment_summary.csv`** – Contains aggregated metrics for each sentiment class.

| classification | avg_net_pnl | avg_net_pnl_% | win_rate_% |
|----------------|--------------|----------------|-------------|
| fear           | ...          | ...            | ...         |
| greed          | ...          | ...            | ...         |

---

## 💡 Insights (Summary)
- **Profitability** and **win rate** tend to vary significantly between fear and greed phases.  
- The **Greed phase** often shows higher potential returns but also increased volatility.  
- **Fear periods** may present more stable or risk-averse behavior.  
- These insights can guide strategy formulation for adaptive or contrarian trading approaches.
