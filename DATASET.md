#  DATASET.md



## 1. Dataset Overview
This repository includes **processed** flight data used to train, evaluate, and test our collision avoidance AI models. The dataset is derived from the **OpenSky Network** API responses and **simulated data** designed to replicate real-world flight conditions for effective model training and testing.



## 2. Data Sources

- **Primary Source**: [OpenSky Network API](https://opensky-network.org/)  
- **Simulated Data**: Custom-generated data used for consistent model testing, especially during live API downtime or data insufficiencies.



## 3. Why We Use Processed Data

While our system is designed to work with **live flight data**, several factors led us to provide a **processed dataset** instead for training and demonstration:
 
- **Incomplete / Noisy Data**: Live data often contains missing or inaccurate entries that require extensive cleaning.  
- **Reproducibility**: Processed data allows for consistent results, essential for model evaluation and peer replication.  
- **Efficient Demonstration**: Guarantees seamless workflow for testing PPO/DQN models and LLM explanations without relying on live data availability.



## 4. Dataset Structure & Features

| Feature             | Description                                           |
|---------------------|-------------------------------------------------------|
| `distance`          | Euclidean distance between aircraft                  |
| `altitude`          | Aircraft altitude in feet                            |
| `velocity`          | Speed in knots                                        |
| `heading`           | Aircraft heading in degrees                          |
| `latitude`          | Latitude coordinate                                   |
| `longitude`         | Longitude coordinate                                  |
| `vertical_rate`     | Rate of climb/descent in feet per minute              |
| `baro_altitude`     | Barometric altitude in feet                          |
| `time_to_collision` | Estimated time to potential collision (in seconds)    |



## 5. Processing Steps

1. **Raw Data Collection**  
   - Fetched from the OpenSky Network API  
   - Stored in JSON and CSV formats

2. **Cleaning & Preprocessing**  
   - Removed missing or NaN values  
   - Converted data types to numeric (float32)  
   - Eliminated outliers and normalized important fields

3. **Feature Engineering**  
   - Calculated Distance, Altitude Difference, Velocity Difference  
   - Derived Time-to-Collision (TTC) metrics  
   - Scaled features as necessary for PPO/DQN models

4. **Final Processed Dataset**  
   - Saved as `processed_flight_data.csv`  
   - Ready for immediate use in model training and evaluation pipelines



## 6. Usage

- **Environment**: Input for `ImprovedCollisionAvoidanceEnv` and `CollisionAvoidanceEnv`  
- **Reinforcement Learning**: PPO and DQN agents are trained using this dataset  
- **Explainability**: LLM model generates natural language explanations for recommended collision avoidance maneuvers  
- **Model Evaluation**: Supports continuous evaluation of PPO/DQN strategies in both training and simulation modes





## 7. Licenses & Attribution

- **OpenSky Network API**: Licensed under the [OpenSky License](https://opensky-network.org/about/licensing)  
- **Usage Disclaimer**:  
  This dataset is intended **strictly for academic research and demonstration purposes**.  
  No sensitive, personal, or military data is included.  
  The dataset does not infringe upon privacy or security protocols.


