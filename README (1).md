# Policy Optimization for Financial Decision-Making
### Shodh AI ML Engineer Take-Home Assessment

This repository contains my submission for the Shodh AI Machine Learning take-home assessment. The project involves a start-to-finish analysis of a loan approval problem, comparing a standard deep learning (DL) classification model against an offline reinforcement learning (RL) agent.


---

## Project Overview & Business Context

This project simulates the role of a Research Scientist at a fintech company tasked with improving the loan approval process. The goal is to develop an intelligent system that can decide whether to approve or deny new loan applications, with the objective of maximizing financial return rather than just optimizing for classification accuracy.

To achieve this, I implemented and compared two distinct modeling paradigms using the LendingClub Loan Data:

1.  **Model 1 (Predictive DL Model):** A PyTorch-based Multi-Layer Perceptron (MLP) trained to predict the probability of loan default.
2.  **Model 2 (Offline RL Agent):** A Discrete Conservative Q-Learning (CQL) agent trained to learn an optimal decision *policy* (Approve/Deny) that maximizes expected financial return.

## Key Findings & Analysis

This is the most critical part of the project. The analysis revealed a significant divergence between the two models, driven by a classic problem in offline RL.

| Metric | Model 1: DL Classifier (F1-Optimized) | Model 2: RL Agent (CQL) |
| :--- | :--- | :--- |
| **Primary Goal** | Maximize F1-Score | Maximize Financial Return |
| **Key Metric** | **F1-Score: 0.4265** (AUC: 0.7081) | **Estimated Policy Value: $1890.34** |
| **Learned Policy** | Approve if `prob_default < 0.2442` | 100% Approval |
| **Approval Rate** | 65.4% | 100.0% |
| **Simulated Avg. Return** | **-$1054.00 / loan** | **-$1610.33 / loan** |


## Setup & Installation

To reproduce this project, please follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/](https://github.com/)[your-username]/[your-repo-name].git](https://github.com/AnoushkaDuggal/ShodhAI_Task.git
    cd ShodhAI_Task
    ```

2.  **Install Dependencies:**
    All required packages are listed in `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download the Data:**
    * The dataset (`accepted_2007_to_2018Q4.csv.gz`) is not included in this repository due to its large size.
    * Please download it from the official Kaggle competition: [LendingClub Loan Data](https://www.kaggle.com/datasets/wordsforthewise/lending-club)
    
