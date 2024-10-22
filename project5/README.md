# INFO536 Project 5: Policy Gradient for CartPole

**Due Date: Nov 5th, 2024**

## Overview

In this project, you will implement a simple reinforcement learning algorithm --- **REINFORCE** to solve the classic **CartPole** problem using **PyTorch**.

CartPole is a popular problem in reinforcement learning. The objective is to keep a pole balanced upright on a moving cart. The agent controls the cart by either pushing it left or right, and must learn to maximize the time the pole stays upright.

![CartPole](./cart_pole.gif)

## CartPole Environment Description

The **CartPole** environment consists of:
- **State**: A 4-dimensional vector representing:
  1. Cart position
  2. Cart velocity
  3. Pole angle
  4. Pole velocity at the tip
- **Action space**: The agent can take two actions:
  - Move the cart to the left (0)
  - Move the cart to the right (1)
- **Goal**: The agent's task is to keep the pole balanced for as long as possible. If the pole angle exceeds a certain threshold or the cart moves out of bounds, the episode ends.

- More details here: https://www.gymlibrary.dev/environments/classic_control/cart_pole/ 

## Requirements

You are required to implement a **Policy Gradient** algorithm, specifically using the **REINFORCE** algorithm (one simple variant of **Policy Gradient**), to solve the CartPole environment. We will use **PyTorch** to build the neural network model that represents the policy, which will output a probability distribution over the actions.

## Deliverables

1. **Report**: Include a brief report explaining your implementation, including any challenges faced, and show the performance of your agent (e.g., plot a graph of scores over time).
2. **Code Submission**: Provide a fully-commented Python script that can be run to train the agent in the CartPole environment.

## Step-by-Step Instructions

### Step 1: Install Dependencies

You will need the following Python packages:

```bash
pip install gym torch numpy matplotlib
```

### Step 2: Define the Policy Network

Create a simple neural network.

### Step 3: Implement the REINFORCE Algorithm

You will implement the REINFORCE algorithm to optimize the policy. The key steps are:

1. **Sample actions**: Use the policy network to sample actions based on the current state.
2. **Store rewards**: After each action, store the corresponding rewards.
3. **Update policy**: After the episode ends, calculate the total reward and update the policy using gradient ascent.

More details about **REINFORCE** algorithm: https://dilithjay.com/blog/reinforce-a-quick-introduction-with-code 

### Step 4: Training the Agent

The training process will run for multiple episodes. At the end of each episode, you should:

- Compute the discounted rewards.
- Normalize the rewards to stabilize training.
- Use the policy gradient to update the policy network weights.

### Step 5: Plot the Results

Once the training is complete, plot a graph showing the **average reward** per episode over time to show how the agent improves.


