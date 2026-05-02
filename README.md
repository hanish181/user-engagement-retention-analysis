# 📊 User Engagement & Retention Analysis (Bible App Case Study)

## 📌 Overview
This project analyzes user behavior data from a mobile application to understand engagement patterns, identify key drop-offs in the user journey, and develop data-driven strategies to improve user retention and overall product experience.

The analysis follows a structured approach covering:
- User behavior analysis
- Funnel and session-level journey analysis
- User segmentation and retention insights
- Predictive modeling for at-risk users
- Video completion prediction
- Anomaly detection

## 🎯 Business Problem
The product team is experiencing strong growth but lacks clarity on:
- Whether users are engaging meaningfully
- Where users drop off in the journey
- How to identify at-risk users early
- How to improve video engagement and completion

## 📂 Dataset
- ~150,000 events
- ~1,000 users
- Timeframe: Jan 1 – Dec 31, 2024

### Features:
- event_timestamp – Timestamp of event
- event_name – Type of user action
- user_id – Unique identifier
- platform_type – Device OS
- app_version – App version
- country – User location

## 🔍 Analysis Workflow

### 1. Event Distribution
- Reading-related events dominate
- Video interactions are low

### 2. User Activity
- Average events/user ≈ 151
- Small group of highly active users

### 3. User Journey (Funnel + Sessions)
- App → Video: ~9.7%
- Video → Next Event: ~29.9%
- Completed sessions: 144
- Incomplete sessions: 27K+

👉 Major drop at discovery + low session engagement

### 4. User Segmentation
- High: 355
- Moderate: 330
- Low: 315

### 5. Retention
- Near-zero inactivity
- Limited churn signal

👉 Retention appears artificially strong due to short observation window

### 6. At-Risk Detection
- Only 1 at-risk user
- Extreme imbalance (999 vs 1)

### 7. Predictive Modeling
- Logistic Regression + Random Forest
- Results misleading due to imbalance

👉 Problem = data, not model

### 8. Anomaly Detection
- Isolation Forest used
- Most users normal

### 9. Risk Score
- Near-zero for most users

### 10. Video Completion Model
- Session-based features (event_count, duration)
- Very low completion prediction

👉 Engagement drops within sessions

## 📊 Key Insights
- Reading dominates engagement
- Video discovery is weak (~9.7%)
- Session completion is extremely low
- Growth driven by activity volume, not depth

## 💡 Recommendations
1. Improve content discovery
2. Increase video engagement
3. Target low-engagement users
4. Retain high-value users
5. Improve data collection

## 🧠 Final Conclusions
- Engagement is narrow (reading-heavy)
- Video underutilized
- Retention misleading due to data
- Main bottleneck = discovery + session engagement

## 🚀 Final Takeaway
Focus on content discovery + in-session engagement to improve growth and retention.

## ⚙️ Tech Stack
Python, Pandas, NumPy, Matplotlib, Scikit-learn

## 👤 Author
Hanish Kumar Kukkala
