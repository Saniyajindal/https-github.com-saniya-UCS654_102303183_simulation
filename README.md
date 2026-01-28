
# Data Generation using Modeling and Simulation for Machine Learning

## Introduction
This project focuses on generating synthetic data using simulation techniques and applying Machine Learning models to analyze system performance. Instead of using real-world data, a simulated environment was created to produce training data.

## Simulation Tool Used
The simulation was implemented using **SimPy**, a Python-based discrete-event simulation library used to model real-world systems such as queues and service systems.

## System Modeled
A **Bank Queue System** was simulated where customers arrive randomly and are served by limited counters. The waiting time of customers depends on arrival rate, service time, and number of counters.

## Parameters and Bounds

| Parameter | Lower Bound | Upper Bound |
|-----------|-------------|-------------|
| Arrival Rate | 1 | 10 |
| Service Time | 2 | 15 |
| Number of Counters | 1 | 5 |
| Simulation Time | 200 | 500 |

## Data Generation
1000 simulations were performed by randomly selecting parameter values within the defined bounds. Each simulation produced the average waiting time, forming a synthetic dataset.

## Machine Learning Models Used
- Linear Regression  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- KNN  
- Support Vector Regression (SVR)

## Evaluation Metrics
The models were evaluated using:
- **R² Score**
- **Mean Absolute Error (MAE)**

## Results
A comparison table of models was generated, and performance graphs were plotted to visualize the results.

## Best Model
Ensemble models such as **Random Forest** and **Gradient Boosting** showed the best performance with the highest R² score.

## Conclusion
This project demonstrates how simulation-based data generation can be used when real datasets are unavailable, and how ML models can learn patterns from simulated environments.
