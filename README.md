# Multi-Armed Bandit Algorithms: Epsilon-Greedy, UCB, and Thompson Sampling

## Overview

This repository contains implementations of three popular multi-armed bandit algorithms:

- **Epsilon-Greedy**
- **Upper Confidence Bound (UCB)**
- **Thompson Sampling**

Each algorithm is tested on a stochastic multi-armed bandit problem where each arm provides rewards based on a Bernoulli distribution. The results are analyzed in terms of **total reward, exploration efficiency, and convergence speed**.

## Implemented Algorithms

### 1. Epsilon-Greedy

Epsilon-Greedy balances exploration and exploitation using a probability **ε** to explore random arms. The remaining probability **1 - ε** is used to exploit the best-known arm.

#### Parameters:

- `ε` (exploration rate): {0.01, 0.1, 0.2, 0.5}
- Steps: 1000
- Number of arms: 5
- Reward distribution: Random Bernoulli probabilities

### 2. Upper Confidence Bound (UCB)

UCB selects arms based on an **upper confidence bound**, which considers the uncertainty in estimated rewards. The exploration term is controlled by **c**.

#### Parameters:

- `c` (exploration weight): {0.1, 1, 2}
- Steps: 1000
- Number of arms: 5

### 3. Thompson Sampling

Thompson Sampling selects arms based on **posterior probability sampling** using a **Beta distribution**.

#### Parameters:

- Prior distribution: Beta(1,1)
- Steps: 1000
- Number of arms: 5

## Experimental Results

### Individual Algorithm Performance

Each algorithm was run for 1000 steps, and their performance was recorded in terms of cumulative reward.

#### **Epsilon-Greedy Performance**

The plot below shows the cumulative rewards for different epsilon values.

![Epsolon](https://github.com/user-attachments/assets/93387e8f-90af-4254-90c6-7c1a4aadfb77)


- Lower **ε** (0.01) results in faster convergence but less exploration.
- Higher **ε** (0.5) explores more but converges slower.

#### **UCB Performance**

The plot below shows the cumulative rewards for different values of **c**.

![UCB](https://github.com/user-attachments/assets/ad26cf93-dd2f-42f8-98a7-6a9b90945bdf)


- Smaller **c** (0.1) leads to under-exploration.
- Larger **c** (2) improves exploration but may slow exploitation.

#### **Thompson Sampling Performance**

The plot below shows the cumulative rewards for Thompson Sampling.

![Thompson](https://github.com/user-attachments/assets/ffc0be4e-9612-4f74-a0df-0ddc5b9a9b7c)


- Converges efficiently by balancing exploration and exploitation dynamically.

### **Comparison of All Algorithms**

A final comparison of all three algorithms is shown below.

![Together](https://github.com/user-attachments/assets/0749f03f-613b-4837-b088-9cf477edcdf2)


### **Analysis & Comparison**

| Algorithm             | Total Reward | Exploration Efficiency | Convergence Speed    |
| --------------------- | ------------ | ---------------------- | -------------------- |
| **Epsilon-Greedy**    | Moderate     | Depends on ε           | Slower with high ε   |
| **UCB**               | High         | Good                   | Faster than ε-greedy |
| **Thompson Sampling** | Highest      | Excellent              | Fastest              |

- **Thompson Sampling** generally **outperforms** both Epsilon-Greedy and UCB in terms of reward and convergence speed.
- **UCB** is a solid alternative with controlled exploration but is **more sensitive to parameter tuning**.
- **Epsilon-Greedy** is the **simplest** but requires careful **ε tuning** to balance exploration and exploitation.

## How to Run the Code

1. Clone the repository:
   ```bash
   git clone https://github.com/BizuhanAbate/Multi-Armed-Bandit-Algorithms-Epsilon-Greedy-UCB-and-Thompson-Sampling.git
   cd Multi-Armed-Bandit-Algorithms-Epsilon-Greedy-UCB-and-Thompson-Sampling
   ```
2. Install dependencies:
   ```bash
   pip install numpy matplotlib
   ```
3. Run the experiment:
   ```bash
   python Multi_Armed_Bandit_Algorithms_Epsilon_Greedy,_UCB,_and_Thompson_Sampling.py
   ```
4. View results in the `images/` directory.

## Conclusion

This project demonstrates how different multi-armed bandit algorithms balance **exploration vs. exploitation**. 
Thompson Sampling consistently achieves the **best performance** due to its adaptive exploration strategy.


