# 🔍 Fraud Analysis in American Retail - 2023

![Static Badge](https://img.shields.io/badge/SQL-blue?color=blue)
![Static Badge](https://img.shields.io/badge/Python-green)
![Static Badge](https://img.shields.io/badge/Analytic%20Skills-gray)
![Static Badge](https://img.shields.io/badge/Exploratory%20Data%20Analysis-yellow)
![Static Badge](https://img.shields.io/badge/ML-purple)
![Static Badge](https://img.shields.io/badge/Soft%20Skill%20-orange)






## 📋 Project Overview

**End-to-end fraud detection project** simulating a real-world scenario for an American wholesale retailer. Using **synthetic data based on actual patterns from a major US retailer**, I identified, quantified, and proposed solutions for operational and financial risks related to missing items in delivered orders.

> 💡 **Note**: This is a **portfolio project** using synthetic data that replicates real fraud patterns observed in the retail industry. All entities (drivers, customers, regions) are fictional but the analytical approach and methodologies are production-ready.

### Key Achievement
Developed a **predictive ML model (AUC-ROC: 0.91)** that detects fraud patterns with 78% recall, uncovering systematic fraud involving drivers, customers, and geographic regions, with potential to reduce losses by **60-75%** ($149K+ annually in this simulation).

## 🎓 Learning Outcomes & Challenges

### What I Learned
- **Complex Data Relationships**: Successfully merged and reconciled 5 interconnected datasets with different granularities
- **Imbalanced Classification**: Handled fraud detection where positive cases are rare (15% failure rate)
- **Feature Engineering**: Created temporal, behavioral, and interaction features that improved model performance
- **Model Interpretability**: Used SHAP values to explain predictions and build stakeholder trust
- **Business Translation**: Converted statistical findings into actionable recommendations with clear ROI

### Challenges Overcome
1. **Data Quality**: Dealt with missing values, inconsistent formatting, and outliers
2. **Fraud Detection Paradox**: Balanced precision vs. recall for rare event detection
3. **Multi-dimensional Analysis**: Identified patterns across 4+ dimensions (driver, customer, region, time)
4. **Stakeholder Communication**: Simplified complex ML concepts for non-technical audience
5. **Scalability**: Designed solution architecture that could handle production-scale data

### Next Steps for Improvement
- [ ] Implement real-time scoring API with FastAPI
- [ ] Add model monitoring and drift detection
- [ ] Expand feature set with text analysis (delivery notes)
- [ ] Test ensemble methods (stacking multiple models)
- [ ] Create automated reporting pipeline

---

## 🗂️ About the Data

### Data Source
The dataset is **synthetically generated** based on real fraud patterns documented in the American retail industry. The synthetic data maintains:
- ✅ Realistic distribution of order volumes and values
- ✅ Authentic fraud patterns (temporal, geographic, behavioral)
- ✅ Industry-standard failure rates and anomalies
- ✅ Privacy compliance (no real customer or employee data)

### Data Generation Process
The synthetic dataset was created by:
1. Studying published fraud cases from major US retailers
2. Analyzing industry benchmarks for delivery failure rates (2-4% normal, 15%+ anomalous)
3. Implementing realistic correlations between variables (driver behavior, customer patterns, regional clusters)
4. Introducing controlled fraud scenarios (driver-customer collusion, geographic hotspots, temporal patterns)

### Why Synthetic Data?
- **Learning**: Demonstrates my ability to work with complex, multi-table datasets
- **Realism**: Reflects actual challenges data analysts face in fraud detection
- **Ethics**: No privacy concerns or NDA violations
- **Reproducibility**: Allows others to validate my methodology

---

## 🎯 Objectives

This portfolio project demonstrates my ability to:

- ✅ Conduct **end-to-end data analysis** from raw data to actionable insights
- ✅ Build **production-ready ML models** for fraud detection
- ✅ Transform complex findings into **clear business recommendations**
- ✅ Create **interactive dashboards** for stakeholder communication
- ✅ Apply **statistical methods** to detect anomalous patterns
- ✅ Understand and solve **real business problems** with data

### Business Problem
Assess operational and financial risks related to missing items in delivered orders, identify fraud patterns, and provide a roadmap to reduce losses.

---

## 📊 Key Findings

### Executive Summary

| Metric | Value |
|--------|-------|
| **Total Orders** | 10,000 |
| **Orders with Missing Items** | 1,502 (15.02%) |
| **Total Missing Items** | 1,662 |
| **Total Financial Loss** | $149,372.61 |
| **Average Loss per Failed Order** | $99.40 |
| **Failure Rate** | 1 in every 6.6 orders |

> ⚠️ **Alert**: The 15.02% failure rate is **3-4x higher** than the 2-4% benchmark for digital retail.

### Critical Insights

#### 🚚 Driver Risk
- Drivers with **>900 deliveries** show higher failure rates
- Top 5 worst-performing drivers account for **9.4% of total losses**
- Some drivers have recurrence rates **above 30%**
- Evidence of **coordinated fraud** between delivery personnel and customers

#### 👥 Customer Risk
- **214 customers** (17.3%) had at least 1 failure
- **12 critical customers** (0.96%) generated **10.3% of total losses**
- High-risk customers show failure rates of **40-46%** vs. 15% average
- Average loss per failure is **2.5-4x higher** than normal

#### 📍 Geographic Risk
- **Top 5 regions** account for **75% of total losses**:
  - Orlando (18.3%)
  - Altamonte Springs (15.7%)
  - Winter Park (15.6%)
  - Kissimmee (12.8%)
  - Apopka (12.8%)

#### ⏰ Temporal Patterns
- **41% of failures** occur between midnight and 7 AM (only 22% of volume)
- Critical time windows: 12 AM-3 AM (23%) and 5 AM-7 AM (18%)
- Weekend deliveries show elevated risk

#### 📦 Product Categories
- **Frozen** (21%), **Pantry** (19%), **Produce** (16%)
- **Electronics** (14%), **Health & Beauty** (12%)
- High-value, small items frequently targeted

---

## 🔬 Methodology

### Data Sources
- `orders.csv` - Complete order history
- `missing_items.csv` - Records of items not delivered
- `products.csv` - Product catalog with pricing
- `customers.csv` - Customer profiles and history
- `drivers.csv` - Driver information and performance

### Analysis Pipeline

```
1. Data Reconciliation → Merge orders with missing items
2. Dimensional Audit → Analyze by driver, customer, region, time
3. Pattern Detection → Identify unusual concentrations and behaviors
4. Loss Projection → Calculate financial impact
5. Executive Reporting → Build comprehensive storytelling
```

---

## 🤖 Predictive Model

### Model Architecture
- **Algorithm**: LightGBM Classifier
- **Training/Test Split**: 70/30
- **Features**: Driver recurrence, customer history, delivery time, region, order value

### Model Performance

| Metric | Value | Interpretation |
|--------|-------|----------------|
| **AUC-ROC** | 0.91 | Excellent discrimination between fraud/normal |
| **Accuracy** | 84% | Overall correct predictions |
| **Recall** | 78% | Detects 78% of actual fraud cases |
| **Precision** | 41% | Normal for rare events in retail |
| **F1-Score** | 0.53 | Balanced performance |

### Feature Importance (SHAP Values)

| Feature | Impact | Key Finding |
|---------|--------|-------------|
| Driver Recurrence | 27% | Repeat offenders increase risk by **3.4x** |
| Historical Failure % | 19% | Past behavior predicts future fraud |
| Delivery Time | 14% | Night/early morning increases risk by **22%** |
| Customer Recurrence | 12% | Repeat customers show elevated risk |
| Order Value | 10% | High-value orders **34% more likely** to involve fraud |

---

## 💡 Recommendations

### Immediate Actions (0-30 days)
1. **Continuous Auditing**: Focus on the 10% highest-risk drivers
2. **Digital Proof of Delivery**: Require photo + geolocation for orders >$80
3. **Real-Time Alerts**: Implement predictive scoring (threshold >0.65)
4. **Temporary Blocking**: Suspend repeat offenders pending investigation

### Short-Term (1-3 months)
5. **Enhanced Supervision**: Increase oversight during 6 PM-10 PM window
6. **Geographic Focus**: Deploy targeted audits in top 5 loss regions
7. **A/B Testing**: Compare supervised vs. free routes
8. **Progressive Shutdown**: Systematic removal of proven fraudsters

### Long-Term (3-6 months)
9. **Risk Score System**: Implement comprehensive scoring (Driver + Customer + Region + Time)
10. **Process Automation**: Automate fraud detection and response workflows
11. **Driver Training**: Enhanced onboarding and ethics programs
12. **Customer Verification**: Strengthen identity validation for high-risk profiles

### Expected Impact
- **Projected Loss Reduction**: 60-75%
- **ROI**: High (focused actions on areas representing 75% of losses)
- **Recidivism Reduction**: 40-50% through automated blocking

---

## 📈 Dashboard & Visualizations

The project includes an interactive Power BI/Tableau dashboard featuring:

- **Driver Risk Scores**: Real-time ranking by risk level
- **Customer Metrics**: Distribution of failure rates and loss values
- **Geographic Heatmap**: Failure rate by region
- **Temporal Analysis**: Failure patterns by hour, day, and week
- **Category Performance**: Loss distribution by product type
- **Predictive Insights**: ML model outputs and alerts

---

## 🛠️ Tech Stack

- **Python 3.8+**: Core analysis
- **Pandas**: Data manipulation and transformation
- **NumPy**: Numerical computations
- **LightGBM**: Machine learning model
- **SHAP**: Model interpretability
- **Matplotlib/Seaborn**: Data visualization
- **Scikit-learn**: Model evaluation and preprocessing
- **Power BI/Tableau**: Interactive dashboards

---

## 📁 Project Structure

```
fraud-analysis-retail/
│
├── data/
│   ├── raw/                    # Original datasets
│   ├── processed/              # Cleaned and transformed data
│   └── outputs/                # Analysis results
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_pattern_analysis.ipynb
│   ├── 03_predictive_modeling.ipynb
│   └── 04_recommendations.ipynb
│
├── src/
│   ├── data_processing.py      # Data cleaning functions
│   ├── fraud_detection.py      # Pattern detection algorithms
│   ├── ml_model.py             # Predictive model
│   └── visualization.py        # Plotting functions
│
├── dashboards/
│   └── fraud_dashboard.pbix    # Power BI dashboard
│
├── reports/
│   └── Fraud_Analysis_Report_2023.pdf
│
├── requirements.txt
└── README.md
```

---

## 📖 Usage

### Data Preparation
```python
from src.data_processing import load_and_merge_data

# Load all datasets
df = load_and_merge_data(
    orders_path='data/raw/orders.csv',
    missing_items_path='data/raw/missing_items.csv',
    products_path='data/raw/products.csv',
    customers_path='data/raw/customers.csv',
    drivers_path='data/raw/drivers.csv'
)
```

### Fraud Detection
```python
from src.fraud_detection import detect_patterns

# Identify high-risk entities
risk_analysis = detect_patterns(df)
print(risk_analysis['high_risk_drivers'])
print(risk_analysis['high_risk_customers'])
```

### Predictive Modeling
```python
from src.ml_model import train_fraud_model

# Train and evaluate model
model, metrics = train_fraud_model(df)
print(f"AUC-ROC: {metrics['auc']}")
print(f"Recall: {metrics['recall']}")
```

---

## 📊 Results Summary

### Business Impact
- **Identified fraud patterns** involving specific driver-customer combinations
- **Quantified $149K+ in losses** with detailed attribution
- **Developed predictive model** with 91% AUC-ROC for real-time detection
- **Provided actionable roadmap** expected to reduce losses by 60-75%

### Technical Achievements
- Integrated 5 data sources with complex relationships
- Detected multi-dimensional fraud patterns (temporal, geographic, behavioral)
- Built production-ready ML model with explainable predictions
- Created interactive dashboard for ongoing monitoring

---

## 🧠 Skills Demonstrated

This project showcases a comprehensive data analytics skillset:

### Technical Skills
- **Python**: Pandas, NumPy, Scikit-learn, LightGBM
- **Machine Learning**: Classification, feature engineering, model evaluation, SHAP explainability
- **Statistics**: Hypothesis testing, anomaly detection, distribution analysis
- **Data Visualization**: Matplotlib, Seaborn, interactive dashboards (Power BI/Tableau)
- **SQL**: Complex joins, aggregations, window functions (data merging logic)

### Business Skills
- **Problem Framing**: Translated business pain points into analytical questions
- **Stakeholder Communication**: Created executive-level presentation and technical documentation
- **ROI Analysis**: Quantified financial impact and projected savings
- **Recommendation Design**: Developed actionable, prioritized implementation roadmap

### Analytical Approach
- **Exploratory Data Analysis**: Uncovered hidden patterns through multi-dimensional analysis
- **Root Cause Analysis**: Identified driver-customer-region fraud triangulation
- **Predictive Modeling**: Built and validated ML model with strong performance metrics
- **Data Storytelling**: Structured findings into compelling narrative for decision-makers


---

**⭐ If you found this project useful, please consider giving it a star!**
