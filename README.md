# Data Generation using Modelling and Simulation for Machine Learning

## 1. Introduction
In many real-world scenarios, collecting large amounts of real data is costly, time-consuming, or impractical. Modelling and simulation provide an effective way to generate synthetic data that can be used for machine learning tasks.

In this project, an open-source simulation tool is used to generate data through modelling and simulation, and multiple machine learning models are trained and evaluated on the generated dataset.

---

## 2. Simulation Tool Used
**SimPy** – an open-source, Python-based discrete-event simulation library.

SimPy allows modelling of real-world systems such as queues, networks, and resource-sharing environments. It is lightweight, easy to use, and suitable for integration with machine learning workflows.

---

## 3. Problem Description
A hospital patient queue system is simulated where:

- Patients arrive at a hospital  
- A limited number of doctors are available  
- Each patient experiences a waiting time before treatment  

The goal of the simulation is to study how different system parameters affect the average patient waiting time, and then use machine learning models to predict the waiting time based on these parameters.

---

## 4. Simulation Model and Parameters

### 4.1 Simulation Model
The system is modelled as a discrete-event simulation using SimPy:

- Patient arrivals follow an exponential distribution  
- Service time also follows an exponential distribution  
- Doctors are modelled as limited resources  

### 4.2 Simulation Parameters and Bounds

| Parameter        | Description                              | Lower Bound | Upper Bound |
|------------------|------------------------------------------|-------------|-------------|
| arrival_rate     | Patient arrival rate (per unit time)     | 1           | 10          |
| service_rate     | Service rate of doctors                  | 2           | 12          |
| doctors          | Number of doctors available              | 1           | 5           |
| simulation_time  | Total simulation duration                | 100         | Fixed       |

These bounds were chosen to represent realistic and stable system behaviour.

---

## 5. Data Generation Methodology

- Random values for arrival rate, service rate, and number of doctors are generated within the defined bounds.  
- The parameters are passed to the SimPy simulation.  
- The simulation runs for a fixed duration.  
- The average waiting time of patients is recorded.  
- Steps 1–4 are repeated 1000 times to generate a synthetic dataset.  

Each simulation run produces one data sample.

---

## 6. Dataset Description

The generated dataset contains the following features:

| Feature Name   | Description                               |
|---------------|-------------------------------------------|
| arrival_rate  | Patient arrival rate                      |
| service_rate  | Doctor service rate                       |
| doctors       | Number of doctors                         |
| avg_wait_time | Average patient waiting time (target)     |

The dataset is saved as **simulation_data.csv**.

---

## 7. Data Visualization
A scatter plot is generated to visualize the relationship between arrival rate and average waiting time. This helps in understanding the system behaviour and validates the simulation results.

*(Insert visualization image here if available)*

---

## 8. Machine Learning Models Used

The following regression models were trained and evaluated:

- Linear Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- Support Vector Regressor (SVR)  
- K-Nearest Neighbors Regressor (KNN)

---

## 9. Model Evaluation Metrics

The models were evaluated using:

- Mean Squared Error (MSE)  
- R² Score  

These metrics help in comparing prediction accuracy and model performance.

---

## 10. Results and Comparison
A comparison table was generated showing the performance of all models. Tree-based ensemble models such as Random Forest and Gradient Boosting performed the best, achieving higher R² scores and lower prediction errors.

*(Insert result graph image here if available)*

---

## 11. Conclusion
This project demonstrates how modelling and simulation can be effectively used to generate synthetic data for machine learning tasks. The use of SimPy enabled realistic system simulation, and the generated data was successfully used to train and compare multiple ML models.

Simulation-based data generation is especially useful in situations where real data is scarce or difficult to obtain.

---

## 12. Files in the Repository

- simpy_hospital_simulation.ipynb – Google Colab notebook containing simulation and ML code  
- simulation_data.csv – Generated dataset  
- README.md – Project documentation  

---

## 13. How to Run

1. Open the notebook in Google Colab  
2. Install SimPy using:

   ```bash
   pip install simpy
   ```

3. Run all cells sequentially  
4. Observe simulation results, graphs, and model comparisons  
