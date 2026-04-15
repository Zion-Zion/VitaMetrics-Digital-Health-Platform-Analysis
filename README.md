# VitaMetrics: Digital Health Platform Analysis

A comprehensive product and health outcomes analysis for a digital metabolic health platform serving 750+ users across three markets (Nigeria, UK, UAE).

## Project Overview

This project analyzes user behavior, platform performance, and health outcomes for VitaMetrics, a digital health platform that combines mobile app engagement, wearable device integration, and AI-generated health insights to help users improve their metabolic health.

**Analysis Period:** January - April 2024  
**Dataset Size:** 750 users, 15,000+ app events, 2,200+ health readings

## Business Questions Addressed

**Product Analytics**
- Where do users drop off during signup, and why?
- What defines an "activated" user beyond account creation?
- Which user segments retain best, and what drives retention?
- What early behaviors predict long-term engagement?

**Health Outcomes**
- Does the platform actually improve user health metrics?
- What engagement patterns differentiate successful users from others?
- How do connected device users perform compared to manual loggers?

## Key Findings

### Activation & Funnel Performance
- **58.5% signup completion rate** from 750 initiated signups
- Biggest leakage point: Verification stage (23.9% drop-off)
- Regional disparity: Nigeria shows 39.8% verification failure rate vs. UK at 17.5%
- Referral and organic search users convert best (68.3% and 67.0% respectively)

### Retention & User Segmentation
- **D30 retention: 55.6%**, indicating moderate platform stickiness
- Five distinct behavioral segments identified in first 14 days:
  - **Power Users (17.1%):** 99.2% retention, device-connected, high AI insight engagement
  - **Ghosters (75.6%):** 41.6% retention, minimal platform engagement
  - Passive Trackers, Manual Loggers, Learners (7.3% combined)

### Health Outcomes (12-Week Analysis)
- **72.0% of users lost weight** (average: 2.0kg reduction)
- **31.6% achieved clinically meaningful improvement** (≥5% weight loss OR ≥2% body fat reduction)
- Success drivers: Food logging frequency (1.5x higher) and AI insight engagement (1.4x higher)
- Body fat analysis limited to 153 device-connected users (61.2% of tracked cohort)

### Critical Insight
Users who connect devices within the first 7 days show 97.6% device adoption and near-perfect retention (99%+). Device connection is the strongest predictor of long-term success.

## Analysis Approach

**Methodology**
- Activation defined as: Signup completion + core health action (device connection, readings recorded, or weight logging) within 7 days
- Retention measured via app_open events across D1, D7, D14, D30 windows
- Behavioral segmentation based on first 14-day engagement patterns
- Health improvement threshold: ≥5% weight loss OR ≥2% body fat reduction (clinical significance)

**Data Quality Steps**
- Standardized inconsistent referral source formatting (13 variants → 5 clean categories)
- Validated BMI calculations against user profiles (100% accuracy within ±0.5 tolerance)
- Confirmed expected null patterns for body fat % in manual log entries
- Handled missing demographics (6% age, 4% gender) via exclusion from demographic-specific analyses only

**Limitations Acknowledged**
- Selection bias: Analysis includes only users who completed 12-week tracking period
- Correlation, not causation: Cannot prove app directly caused health improvements
- Limited body fat data: Device requirement reduces sample to 61.2% of users
- Short timeframe: 12 weeks insufficient for long-term weight maintenance assessment

## Tools & Technologies

- **Python 3.x:** Data manipulation and analysis
- **Libraries:** pandas, numpy, matplotlib
- **Environment:** Jupyter Notebook
- **Visualization:** matplotlib for executive summary charts

## Repository Structure
``` VitaMetrics-Analysis/
│
├── VitaMetrics_Analysis.ipynb          # Complete analysis notebook
├── Executive_Summary.pdf                # 4-slide stakeholder presentation
│
├── datasets/
│   ├── original/
│   │   ├── user_profiles.csv
│   │   ├── app_events.csv
│   │   └── health_outcomes.csv
│   │
│   ├── cleaned/
│   │   ├── user_profiles_clean.csv
│   │   ├── app_events_clean.csv
│   │   └── health_outcomes_clean.csv
│   │
│   └── Data_Dictionary.pdf
│
└── README.md
```
## Key Recommendations

1. **Drive Early Device Connection:** Implement targeted Day 1 and Day 3 push notifications for device setup to shift users into high-retention cohort

2. **Strengthen AI Insight Onboarding:** Show sample AI insight during Day 0 onboarding to demonstrate platform value before data collection

3. **Re-engage Ghosters:** Launch Day 7 email campaign targeting the 75.6% low-activity segment with success stories and feature highlights

4. **Fix Regional Verification:** Implement WhatsApp-based verification alternative for Nigerian market to address 39.8% SMS failure rate

## Running the Analysis

1. Clone this repository
2. Install dependencies: `pip install pandas numpy matplotlib jupyter`
3. Open `VitaMetrics_Analysis.ipynb` in Jupyter
4. Run all cells sequentially

All datasets are included in `/datasets/original/`. The notebook is fully reproducible.

## About This Project

This analysis was completed as a technical assessment demonstrating:
- Product analytics and funnel optimization
- User segmentation and behavioral analysis
- Health outcomes measurement and clinical interpretation
- Data quality management and assumption documentation
- Stakeholder communication via executive summary

---

**Author:** Zion Oluwasegun  
**Portfolio:** [bit.ly/ZionTheAnalyst](https://bit.ly/ZionTheAnalyst)
**LinkedIn:** [linkedin.com/in/zion-oluwasegun](https://linkedin.com/in/zion-oluwasegun)

For a detailed walkthrough of the methodology and decision-making process, see the accompanying Medium article: [Link coming soon]
