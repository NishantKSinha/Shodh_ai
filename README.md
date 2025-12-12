# Policy Optimization for Financial Decision-Making

**Shodh AI ML Engineer Take-Home Assessment**  

This repository contains my submission for the Shodh AI Machine Learning take-home assessment. The project involves an end-to-end analysis of a loan approval problem, comparing a standard deep learning (DL) classifier against an offline reinforcement learning (RL) agent.

---

## Project Overview & Business Context

This project simulates the role of a Research Scientist at a fintech company tasked with improving the loan approval process.  
The objective is to develop an intelligent system that can approve or deny loan applications, maximizing **financial return** rather than just classification accuracy.

Two modeling paradigms are implemented and compared using the LendingClub Loan Data:

1. **Predictive DL Model**  
   - A PyTorch-based Multi-Layer Perceptron (MLP) trained to predict the probability of loan default.
   
2. **Offline RL Agent**  
   - A Discrete Conservative Q-Learning (CQL) agent trained to learn an optimal decision policy (Approve/Deny) that maximizes expected financial return.

---

## Key Findings & Analysis

The analysis revealed a significant divergence between the two models, highlighting a classic problem in offline RL.

| Metric | Model 1: DL Classifier (F1-Optimized) | Model 2: RL Agent (CQL) |
|--------|--------------------------------------|--------------------------|
| **Primary Goal** | Maximize F1-Score | Maximize Financial Return |
| **Key Metric** | F1-Score: 0.4265 (AUC: 0.7081) | Estimated Policy Value: $1890.34 |
| **Learned Policy** | Approve if prob_default < 0.2442 | 100% Approval |
| **Approval Rate** | 65.4% | 100.0% |
| **Simulated Avg. Return** | -$1054.00 / loan | -$1610.33 / loan |

