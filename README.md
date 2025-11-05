🛡️ Fraud Detection Model Monitoring & Diagnostics
This project addresses a critical performance drop in Poundbank's production fraud detection model. I established a robust monitoring pipeline to diagnose the failure, aiming to quantitatively prove that data and concept drift were the root cause.

1. Actions and Methodology
I implemented a comprehensive model observability framework using specialized monitoring techniques to track both model stability and data integrity:

Performance Tracking: I used methodologies derived from CBPE (Confidence-Based Performance Estimation) and Performance Calculators to track the model's estimated and realized accuracy monthly, identifying exactly when performance fell outside acceptable confidence bands.

Drift Analysis: I employed the Univariate Drift Calculator (using Kolmogorov-Smirnov and Chi-Square tests) and Data Quality checks to measure feature stability and unusual statistical shifts in key variables.

Visualization: I generated a Realized ROC Curve using Scikit-learn to visually confirm the model's degraded performance against a random baseline.

2. Key Findings and Business Impact
The analysis confirmed that the model was rendered obsolete due to adversarial adaptation by fraudsters, providing immediate, actionable evidence.

Sustained Failure: Accuracy alerts were triggered for three consecutive months (April, May, and June 2019), confirming a sustained model failure and establishing a critical window for intervention.

Root Cause Identified: time_since_login_min was identified as the feature most strongly correlated with the drop in accuracy, providing the data science team with the precise factor requiring enhanced engineering.

Behavioral Shift: Data quality checks revealed a major shift in transactional behavior: the monthly average transaction amount spiked to over $3,000, confirming that fraudsters consolidated their activities into fewer, larger transfers to evade detection.

By isolating the performance failure, quantifying the behavioral change, and confirming the specific drifting features, this project provided actionable evidence to immediately guide model retraining and risk mitigation strategies, effectively safeguarding bank assets against the new attack vector.
