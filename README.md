# 🚗 Power BI Project — Used Car Market Intelligence  
**Behavioral Analytics | Forecasting | Anomaly Detection | KPI Storytelling**

## 📌 Project Overview
This project analyzes the **Used Cars Dataset (Indian Market)** using **Power BI** to demonstrate how large-scale, noisy marketplace data can be transformed into **actionable behavioral insights**.

The dashboard focuses on:
- 📈 **Price & demand forecasting**
- 🚨 **Anomaly detection in listings and pricing**
- 📊 **Executive-ready KPIs**
- 🧠 **Behavioral and social-signal inference** from seller and buyer activity

The project is intentionally framed to mirror **social analytics and marketplace intelligence problems**, aligning with **Senior Data Scientist – Social Analytics** responsibilities.

---

## 🎯 Business & Analytics Motivation
Used-car marketplaces behave like **social systems**:
- Sellers compete within **brand/model communities**
- Pricing diffuses through **peer listings**
- Outliers signal **fraud, urgency, or misinformation**
- Buyer attention concentrates around **influencers (brands/models)**

This project answers questions such as:
- How do prices evolve over time across communities?
- Which brands/models influence market pricing?
- Where do anomalous listings appear — and why?
- How can insights be translated into **decision-ready narratives**?

---

## 📂 Dataset Description
**Used Cars Dataset — Indian Market (Up to Nov 2024)**  
- **9,582 listings**
- **11 attributes**

### Features
| Column | Description |
|------|------------|
| Brand | Manufacturer (Maruti, Honda, Tata, VW, etc.) |
| Model | Specific car model |
| Year | Manufacturing year |
| Age | Vehicle age (years) |
| kmDriven | Total kilometers driven |
| Transmission | Manual / Automatic |
| Owner | First / Second owner |
| FuelType | Petrol / Diesel / Hybrid / CNG |
| PostedDate | Listing post date |
| AdditionalInfo | Free-text seller description |
| AskPrice | Listed price (₹ INR) |

---

## 🧮 Core KPIs
| Category | KPI |
|------|----|
| Pricing | Avg Ask Price, Median Price |
| Market Health | Price Volatility Index |
| Demand Proxy | Listing Frequency |
| Depreciation | Price vs Age |
| Behavior | Owner Type Distribution |
| Efficiency | Price per km Driven |

---

## 🔮 Forecasting
**Objective:** Predict future price and listing trends.

**Techniques:**
- Power BI time-series forecasting
- Seasonal trend extraction
- Confidence interval analysis

**Forecasted Metrics:**
- Average listing price by brand
- Monthly listing volume
- Depreciation curves

**Business Use:**
- Seller pricing guidance
- Inventory planning
- Market timing insights

---

## 🚨 Anomaly Detection
**Objective:** Detect abnormal pricing and behavior.

**Detected Patterns:**
- Under-priced high-value listings
- Over-priced aging vehicles
- Unusual km vs price combinations
- Sudden posting spikes by brand/model

**Why This Matters:**
- Fraud detection
- Mispricing identification
- Supply-demand shocks
- Trust & marketplace integrity

---

## 🧠 Behavioral & Social Analytics Framing
Although transactional, this dataset reflects **social dynamics**:

### Community Structure
- Brands & models act as **communities**
- Pricing norms emerge within communities
- Deviations signal behavioral anomalies

### Influence Signals
- Certain models drive market price anchors
- High-frequency listings influence pricing diffusion

### Narrative Translation
Findings are translated into:
- Clear executive summaries
- Visual storytelling
- Business-ready recommendations

---

## 📊 Dashboard Pages
1. **Executive Overview**
   - Market KPIs
   - Pricing trends
   - Risk & opportunity signals

2. **Price Forecasting**
   - Historical vs predicted prices
   - Brand-level seasonality
   - Confidence bands

3. **Anomaly Monitoring**
   - Outlier listings
   - Root-cause explanations
   - Drill-downs by brand/model

4. **Behavioral Insights**
   - Owner behavior patterns
   - Price diffusion across brands
   - Market segmentation

---

## 🛠 Tools & Technologies
- **Power BI Desktop**
- **Power Query (M)** for data cleaning
- **DAX** for KPI logic
- **AI visuals** (Forecasting & Anomaly Detection)

---

## 📐 Data Modeling
- Star schema
- Fact table: Listings
- Dimension tables:
  - Date
  - Brand
  - Model
  - Fuel Type
  - Transmission

Optimized for:
- Scalability
- Drill-through analysis
- Executive responsiveness

---

## 📊 Sample DAX Measures
```DAX
Average Ask Price =
AVERAGE(UsedCars[AskPrice])

Price per KM =
DIVIDE(
    AVERAGE(UsedCars[AskPrice]),
    AVERAGE(UsedCars[kmDriven])
)

Listings MOM Growth % =
DIVIDE(
    COUNT(UsedCars[AskPrice]) -
    CALCULATE(COUNT(UsedCars[AskPrice]), DATEADD('Date'[Date], -1, MONTH)),
    CALCULATE(COUNT(UsedCars[AskPrice]), DATEADD('Date'[Date], -1, MONTH))
)
