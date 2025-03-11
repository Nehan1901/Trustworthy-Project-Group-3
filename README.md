
# AI Driven Mid Air Collsion Avoidance System



## Table of Contents

 - [Introduction](#introduction) 
 - [Contributions](#contributions)
 - [Key Features](#key-features)
 - [Technologies Used](#technologies-used) 
 - [Project Structure](#project-structure)
 - [Installation](#installation)
 - [References](#references)
 - [Imprtant Notes](#important-notes)

## Introduction
As the skies become increasingly crowded, ensuring the safety of aircraft is more important than ever. Traditional collision avoidance systems do their job, but they often rely on rigid rules and lack the ability to adapt to fast-changing scenarios.

This project—AI-Driven Mid-Air Collision Avoidance System—introduces an intelligent, adaptive solution powered by Reinforcement Learning . Our system predicts and prevents potential mid-air collisions by making real-time decisions.To make the system more transparent, we integrated LLM-powered explanations using , allowing human operators to understand the reasoning behind each decision.

While live flight data APIs have their limitations, we ensured smooth and reliable performance by incorporating realistic simulated data for testing and demonstrations. The result is a robust, AI-powered safety system designed to meet the future demands of air traffic management.

## Contributions

Nehan – Data Pipeline & Feature Engineering
Nehan handled the data side of things—cleaning, processing, and preparing flight data for the models. He created key features like Time-to-Collision (TTC) and Altitude Differences, making sure our models had accurate, meaningful inputs. His work was essential for building a reliable system from the ground up.

Sai Krishna – Model Development & Training
Sai Krishna focused on building and training our core AI models DQN and PPO for collision avoidance. He fine-tuned them for better performance and tested their ability to predict risks and recommend safe actions. His models form the brain of our system.

Radha – System Integration & LLM Explanations
Radha made sure everything worked smoothly together. She connected the data pipeline, AI models, and outputs into one streamlined system. She also integrated the LLM, which turns model decisions into clear, human-friendly explanations that pilots and air traffic controllers can easily understand.
## Key Features

 - Live Flight Data Processing: Integration with the OpenSky Network API for real-time data fetching, with intelligent fallback to simulated data for consistency and reliability.
 - Custom Reinforcement Learning Environment: Tailored observation and reward structures, enabling the PPO and DQN agents to learn from complex, dynamic scenarios.
- Explainable AI with LLMs: Gemini 1.5 Pro provides human-readable explanations of AI actions, enhancing trust and interpretability in decision-making processes.
- 	Hyperparameter Tuning and Model Comparison: Systematic evaluation and optimization of PPO and DQN models ensure robust performance under various conditions.
## Technologies Used
- Reinforcement Learning: PPO, DQN (Stable-Baselines3)
- Custom Environment: OpenAI Gym / Gymnasium
- Data Processing: Pandas, NumPy
- Visualization: Matplotlib
- LLM Explainability: Google Gemini 1.5 Pro API
- Training Environment: Google Colab & Local Python    Environment
## Project Structure
```
AI_MidAir_Collision_Avoidance
├── models                              
   ├── ppo_collision_avoidance_final.zip
   ├── ppo_balanced_actions_model.zip
├── data                                    
   ├── sample_flight_data.csv
   ├── model_evaluation_log.csv
├── environment.py                           # Custom gym environment definition
├── train_ppo.py                             # PPO model training script
├── train_dqn.py                             # DQN model training script
├── evaluation.py                            # Evaluation and hyperparameter tuning
├── llm_explanation.py                       # LLM (Gemini) explanation integration
├── README.md                                # Project documentation
└── requirements.txt                         # Python dependencies
```
## Installation

1.Clone the Repository

```bash
git clone https://github.com/yourusername/AI_MidAir_Collision_Avoidance.git
cd AI_MidAir_Collision_Avoidance
```

2..Create and Activate Virtual Environment

```bash
python -m venv venv
source venv/bin/activate       # Linux / MacOS
venv\Scripts\activate          # Windows
```
3.Install Dependencies

```bash
pip install -r requirements.txt
```
or install them manually

```bash
!pip install stable-baselines3 gymnasium numpy pandas matplotlib shimmy torch torchvision torchaudio google-generativeai

```
4.Configure Google Gemini API for LLM Explainability

•	Get the API key from the Gemini platform: Gemini API

•	Replace YOUR_GEMINI_API_KEY in llm_explanation.py:
```bash
import google.generativeai as genai
genai.configure(api_key="YOUR_GEMINI_API_KEY")
```

## References
"Optimizing the Next Generation Collision Avoidance System for Safe, Suitable, and Acceptable Operational Performance"
Authors: M. A. Vivona, R. J. Moss, and J. Kuchar

PPO Algorithm: Schulman et al. “Proximal Policy Optimization Algorithms” (2017)

DQN Algorithm: Mnih et al. “Playing Atari with Deep Reinforcement Learning” (2015)

#### Code Sources
This project was fully developed by our team, including custom data pipelines, collision avoidance environments, reward functions, and integration of PPO/DQN models using Stable-Baselines3. We also implemented an LLM-based explanation system using Google Gemini 1.5 Pro and built a user interface with Flask. While we relied on open-source libraries such as Stable-Baselines3, Gymnasium, Optuna, and the OpenSky Network API, All implementations followed official documentation and were customized for our unique use case.
## Important Notes
Relying exclusively on live data during the demonstration phase would compromise the integrity and reliability of the system.
By falling back to simulated data.We:
- Preserved the core purpose of showcasing how AI-driven reinforcement learning can optimize mid-air collision avoidance.
- Delivered a consistent, professional demonstration highlighting the power of AI and LLM explainability in aviation safety
  
#### LLM Explainability:
- Integrated Gemini AI to explain reinforcement learning actions, aiding in AI transparency and trustworthiness.
