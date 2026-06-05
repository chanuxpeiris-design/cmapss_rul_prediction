# Turbofan Engine Predictive Maintenance (CMAPSS)

## Project overview
This project was developed independently to build a robust predictive maintenance pipeline using the Pandas framework. It analyzes the NASA CMAPSS (FD001) dataset to predict the Remaining Useful Life (RUL) of turbofan engines based on thermodynamic sensor telemetry.

## Key engineering tasks
* **Data Ingestion:** Handled raw, space-separated sensor logs and mapped 21 anonymous columns to physical thermodynamic sensors.
* **Feature Engineering:** Calculated a Piecewise Linear RUL (capped at 128 cycles) to reflect the physical reality of healthy engine states.
* **Dimensionality Reduction:** Identified and dropped "dead" sensors with zero variance at sea-level operating conditions.
* **Baseline Modeling:** Trained a Random Forest Regressor to establish an interpretable baseline for sensor-based degradation prediction.

## Limitations and future scope
While the baseline snapshot model successfully tracks degradation, it highlights the need for temporal context. My next iteration roadmap includes:
1. Implementing a 30-cycle sliding window to capture degradation velocity.
2. Applying rolling averages to smooth raw sensor noise.
3. Designing an asymmetric loss function to heavily penalize over-predictions (late maintenance) in accordance with aviation safety tolerances.

## Files
* `cmapss_analysis_1.ipynb`: The complete Python/Pandas codebase.
* Data files: NASA CMAPSS FD001 training and testing logs.
