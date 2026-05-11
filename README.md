# Uber Ride Cancellation Prediction & Operational Intelligence

## Project Overview

Every cancelled ride tells a story — a missed connection between customer demand, driver availability, time pressure, and operational efficiency.

This project analyzes nearly **150,000 Uber ride bookings** to uncover the hidden factors driving ride cancellations and operational inefficiencies across the platform. Using data analytics, visualization, and machine learning, the project explores how ride distance, waiting time, booking value, location, and customer behavior influence cancellation patterns.

The goal was not just to predict cancellations, but to transform ride-booking data into actionable operational intelligence that can help improve customer experience, reduce inefficiencies, and optimize driver allocation.

---

# Project Highlights

- Analyzed **~150K Uber ride bookings**
- Built multiple machine learning models with **Random Forest achieving 94.97% accuracy**
- Predicted ride cancellations using operational, behavioral, and geographic features
- Identified the strongest cancellation drivers using feature importance analysis
- Conducted location-based, vehicle-based, time-based, and payment-based trend analysis
- Built predictive intelligence for operational optimization and customer retention

---

# Business Problem

Ride cancellations create major operational challenges for ride-sharing platforms:
- Increased customer frustration
- Driver inefficiencies
- Revenue loss
- Longer wait times
- Poor ride allocation efficiency

This project focuses on identifying:
- Why rides get cancelled
- Which factors increase cancellation probability
- Which operational areas require optimization
- How machine learning can predict cancellations before they occur

---

# Dataset Summary

- **150,000 ride bookings**
- **21 original features**
- Multiple ride outcomes:
  - Completed
  - Cancelled by Driver
  - Cancelled by Customer
  - No Driver Found
  - Incomplete

### Target Variable Engineering
Created a binary classification feature:
- `0` → Completed rides
- `1` → Cancelled/unsuccessful rides

This transformed the project into a supervised machine learning classification problem. 

---

# Exploratory Business Analysis

## 1. Cancellation Distribution Analysis

### Key Findings
- Approximately **38% of rides** were cancelled or incomplete.
- Only **62% of rides** were successfully completed.
- Cancellation rates were high enough to represent a major operational inefficiency.

### Business Impact
- High cancellation rates reduce platform reliability.
- Operational inefficiencies increase customer churn risk.
- Improving cancellation prediction can significantly improve ride completion rates.

---

# 2. Pickup Location Intelligence Analysis

### Business Question
Which pickup locations experience the highest cancellation rates?

### Key Findings
Locations such as:
- Vinobapuri
- Akshardham
- Chhatarpur

recorded cancellation rates between **40–45%**, significantly above the platform average. 

### Trends Identified
- High-demand urban areas showed stronger cancellation concentration.
- Certain pickup zones consistently experienced operational inefficiencies.
- Geographic location became one of the strongest predictive features.

### Business Impact
- Uber can optimize driver allocation in high-risk cancellation zones.
- Dynamic driver incentives can reduce cancellation frequency.
- Geographic intelligence improves operational efficiency and matching quality.

---

# 3. Vehicle Type Market Analysis

### Ride Volume Trends
The most frequently booked ride categories were:
- Auto
- Go Mini
- Go Sedan

Lower-demand categories included:
- Uber XL
- eBike

### Key Findings
- Affordable vehicle types dominated ride demand.
- Go Sedan showed slightly higher cancellation rates than other vehicle categories.
- Vehicle type alone was not a major cancellation driver.

### Business Impact
- Uber’s strongest demand is concentrated in affordable ride options.
- Improving driver availability for high-demand categories may improve completion rates.
- Vehicle category optimization can improve operational efficiency.

---

# 4. Time-Based Cancellation Analysis

### Key Findings
- Cancellation rates remained relatively stable throughout the day (~37–38%).
- Early morning and afternoon periods showed slightly higher cancellation activity.
- Monday and Tuesday experienced marginally higher cancellation rates.

### Trend Analysis
Time-related features had surprisingly low predictive importance compared to:
- Ride distance
- Waiting time
- Booking value

### Business Impact
- Time alone is not a strong cancellation predictor.
- Operational optimization should focus more on supply-demand balance and ride allocation efficiency.

---

# 5. Payment Behavior Analysis

### Payment Distribution
- UPI accounted for approximately **45%** of all transactions.
- Cash represented nearly **25%** of ride payments.
- Wallets and cards contributed smaller transaction shares.

### Key Findings
- Payment method had very little impact on cancellation probability.
- Digital payment users showed slightly stronger ride commitment patterns.

### Business Impact
- Cancellation reduction strategies should prioritize operational factors rather than payment systems.
- UPI dominance highlights strong digital payment adoption among users.

---

# 6. Customer & Driver Behavior Insights

### Strongest Cancellation Drivers
The analysis revealed:
- Shorter rides were more likely to be cancelled.
- Longer waiting times significantly increased customer cancellations.
- Ride distance became the most important predictive feature.

### Key Operational Trends
- Higher Avg VTAT (driver arrival delay) increased customer-side cancellations.
- CTAT and ride duration strongly influenced ride completion probability.
- Ratings were unavailable for cancelled rides, reducing their predictive value.

### Business Impact
- Faster driver matching can significantly reduce cancellation rates.
- Operational efficiency matters more than vehicle type or payment method.
- Waiting time optimization is critical for customer retention.

---

# Data Preprocessing & Feature Engineering

## Data Cleaning
- Removed columns with over **90% missing values**
- Applied median imputation for numerical features
- Applied mode imputation for categorical variables
- Converted time-related object fields into datetime features

## Feature Engineering
Engineered features included:
- Cancellation indicators
- Time-period features
- Day-of-week analysis
- Customer cancellation flags
- Driver cancellation flags
- One-hot encoded categorical variables

After preprocessing:
- Dataset contained **zero missing values**
- Prepared for machine learning classification modeling

---

# Machine Learning Model Comparison

## Models Evaluated
- Logistic Regression
- Naive Bayes
- K-Nearest Neighbors (KNN)
- Random Forest
- Gradient Boosting
- XGBoost

| Model | Accuracy |
|---|---|
| Random Forest | 94.97% |
| Gradient Boosting | ~95–96% |
| XGBoost | ~95.8% |
| KNN | ~95% |
| Logistic Regression | 81% |
| Naive Bayes | 70.4% |

---

# Best Performing Model — Random Forest

## Why Random Forest Performed Best

Random Forest achieved the strongest overall performance because it:
- Captured nonlinear relationships between operational variables
- Reduced overfitting through ensemble learning
- Handled complex ride-behavior interactions effectively

### Performance Metrics
- **94.97% testing accuracy**
- High precision for predicting ride cancellations
- Strong generalization with minimal overfitting

### Confusion Matrix Insights
- Correctly classified over **27,500 completed rides**
- Correctly identified over **15,200 cancelled rides**
- Maintained very low prediction error overall

---

# Most Important Features

## Feature Importance Analysis

| Feature | Importance |
|---|---|
| Ride Distance | 30.59% |
| Avg CTAT | 24.59% |
| Booking Value | 20.49% |
| Payment Method (UPI) | 13.11% |
| Avg VTAT | 2.95% |

### Key Insights
The top 3 features alone contributed over **75%** of the model’s predictive power.

This revealed that:
- Ride distance
- Waiting time
- Ride cost

are the dominant factors driving cancellation behavior. 

---

# Key Business Insights

### Major Operational Trends
- Short rides experience higher cancellation probability.
- Longer driver arrival times significantly increase customer cancellations.
- Geographic location strongly influences operational reliability.
- Time-of-day patterns have surprisingly low predictive impact.

### Strategic Recommendations
Uber can reduce cancellations by:
- Improving driver allocation systems
- Reducing pickup delays
- Optimizing short-distance ride matching
- Applying dynamic incentives in high-cancellation zones
- Improving operational efficiency in high-demand areas

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

# Future Work

Plan to expand this project into a real-time operational intelligence platform by:
- Building a live ride cancellation prediction dashboard
- Deploying the model using Streamlit/Flask
- Integrating real-time ride analytics
- Adding dynamic operational monitoring
- Creating live geographic cancellation heatmaps
- Developing intelligent driver allocation recommendations
