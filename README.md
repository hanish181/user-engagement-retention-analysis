# User Engagement & Retention Analysis for Mobile App
End-to-end analysis of user engagement, retention, and at-risk user prediction for a mobile application.
## Overview

This project analyzes mobile app user behavior to understand engagement patterns, identify drop-offs in the user journey, and build a predictive approach for detecting at-risk users.

The project follows an end-to-end data science workflow, including data exploration, user behavior analysis, funnel analysis, segmentation, retention analysis, predictive modeling, and business recommendations.

## Objective

The goal of this project is to uncover actionable insights that can improve user engagement, retention, and overall product experience.

Key objectives include:

- Understand user behavior patterns
- Analyze engagement distribution
- Identify drop-offs in the user journey
- Detect early signs of disengagement
- Build a predictive modeling approach for at-risk users
- Translate insights into product recommendations

## Dataset

The dataset contains timestamped mobile app user events.

Key fields include:

- `event_dt` — Date of the event
- `event_timestamp` — Timestamp of user activity
- `event_name` — Type of user action
- `user_id` — Unique user identifier
- `platform_type` — Device platform such as Android or iOS
- `country` — User country
- `app_version` — Application version

**Note:** The raw dataset is not included in this repository due to confidentiality.

## Project Workflow

### 1. Data Loading and Inspection

Loaded the event-level dataset and inspected its structure, columns, timestamps, and key attributes.

### 2. Event Distribution Analysis

Analyzed the frequency of user actions to understand what users do most frequently in the application.

Key findings:

- User engagement is primarily driven by reading-related actions such as `plan_day_read` and `highlight_verse`.
- Video interactions are present but less frequent compared to reading actions.

### 3. User Activity Analysis

Calculated the number of events performed by each user to understand engagement distribution.

Key findings:

- Most users show relatively consistent activity.
- A small subset of users demonstrates significantly higher engagement.

### 4. User Journey and Funnel Analysis

Built a sequential funnel using event transitions:

```text
app_open → video_started → video_stopped
```

Key findings:

- Only around 9.7% of users move from `app_open` to `video_started`.
- Around 29.9% of users who start videos complete them.
- The primary bottleneck appears to be content discovery rather than content quality.

### 5. User Segmentation

Segmented users into engagement groups:

- High Value
- Moderate
- Low Engagement

An engagement score was also created by normalizing activity over time.

Key findings:

- User engagement is fairly balanced across segments.
- Low-engagement users represent an opportunity for onboarding and engagement improvements.

### 6. Retention and Inactivity Analysis

Analyzed user inactivity using the most recent event timestamp.

Key findings:

- Most users have 0 days of inactivity.
- The dataset does not capture long-term churn behavior.
- Short-term inactivity can still be used as an early signal for disengagement.

### 7. At-Risk User Identification

Defined at-risk users using inactivity:

```text
at_risk = days_inactive > 1
```

Key findings:

- Only 1 user was identified as at-risk.
- This indicates extreme class imbalance and limited churn signal in the dataset.

### 8. Predictive Modeling

Built a predictive modeling approach for at-risk users using:

- Logistic Regression baseline model
- Class-weighted Random Forest
- Isolation Forest anomaly detection

Key findings:

- Logistic Regression failed to detect the minority class.
- Random Forest appeared to perform well, but the result is not reliable due to only one positive at-risk user.
- The model limitation is caused by data imbalance rather than the modeling approach.

## Key Findings

- User engagement is primarily driven by reading-related actions.
- Video engagement has a major drop-off from app entry.
- Most users show consistent activity, with a few highly active users.
- User segmentation shows a balanced distribution across engagement levels.
- The dataset has very limited churn signal.
- Only one user was identified as at-risk.
- Predictive modeling is limited due to extreme class imbalance.
- Anomaly detection provides an alternative approach when labeled churn data is limited.

## Recommendations

- Improve content discovery to increase video engagement.
- Focus on retaining high-value users through personalized experiences.
- Improve onboarding and user experience for low-engagement users.
- Use early inactivity signals to trigger proactive re-engagement strategies.
- Collect longer-term data to better capture churn behavior.
- Build a more reliable churn model after collecting sufficient inactive user examples.

## System Perspective

This project demonstrates how behavioral analytics, predictive modeling, and product thinking can be combined to build a scalable user engagement and retention system.

Although the predictive model is limited due to data imbalance, the framework can still be applied in real-world systems to detect unusual user behavior early and trigger proactive engagement strategies.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Repository Files

```text
Hanish_Kumar_User_Engagement_Case_Study.pdf
Hanish_User_Engagement_Notebook.ipynb
README.md
requirements.txt
```

## Author

**Hanish Kumar Kukkala**  
Data Science Case Study
