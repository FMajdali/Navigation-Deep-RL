# Navigation Project 

This is a solution for the Navigation Project which is part of Deep RL Udacity Nanodegree, many parts of this README.md and the repository are copied or originated from the Deep RL Udacity Nanodegree materials.

# Disclaimer by Udacity

This is an amended version of the `python/` folder from the [ML-Agents repository](https://github.com/Unity-Technologies/ml-agents).  It has been edited to include a few additional pip packages needed for the Deep Reinforcement Learning Nanodegree program.

# Navigation Project Details
## Environment
The project aims to solve one of the environments built by Unity, where the agent navigates and collects bananas in a large, square world.
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. 
Thus, the goal of the agent is to collect as many yellow bananas as possible while avoiding blue bananas.
## State
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction.
Given this information, the agent has to learn how to best select actions.
## Actions
Four discrete actions are available to the agent, corresponding to:
-  Action 0: move forward
-  Action 1: move backward
-  Action 2: turn left
-  Action 3: turn right
## Solving the environment
The environment on hand is episodic, and to **solve the project successfully, the agent must get an average score of +13 over 100 consecutive episodes.**

# Learning Algorithem
## Quick Explanation
The utilized algorithem in this project is **Deep Q Network** where a neural network is trained to become an approximator of the optimal action-value function. Reinforcement Learning is notoriously unstable when neural networks are used to represent the action-value function.

Therefore, two main techniques are used to train the network:
-  Experience Reply: a memory is used to store the experncies, then every n-runs the learning occurs on a random sample of the memory to break correlations and provide stability
-  Fixed Q-Targets: Moving the target at every multiple steps instead of changing it every step which cause oscillation, this could be done by creating another network with another set of weights, every multiple steps the target steps gets a soft update to become more similar to the first neural network

## Hyperparameters
All the below hyperparamters below could be found in the dqn_agent.py:
- Experience reply memory size: **BUFFER_SIZE = int(1e5)**
- The number of sampled experince tubles at each learning step: **BATCH_SIZE = 64**
- The discount factor applied on the action-value function of the next state: **GAMMA = 0.99**
- A learning paramter which soft update the target parametrs (1 makes the target identical to the trained model): **TAU = 1e-3**
- Learning rate alpha: **LR = 5e-4**
- The learning process will occuer at every n steps: **UPDATE_EVERY = 4**
### Epsilon:
- the epsilon hyperparameters are in the dqn class in the Navigation.ipynb:
  - The number epsilon start with: **eps_start=1.0**
  - The most minimum that epsilon could reach: **eps_end=0.01**
  - The epsilon decying rate which is applied on epsilon at the end of each episode: **eps_decay=0.995** 

## Nerual Network Architecture
The nerual network is written using pytorch, it recives the state which consist of 37 dimensions, then it process it with 4 fully connected layers of the size 64, each layer is applying a Relu activtion function on the output it passes to the next layer except the last on whcih outputs 4 outputs (crossponding to the number of actions)

# Instructions
## Getting Started

All the required libraries are there in the requirements.txt, there is an option to use the command **!pip -q install .** in the Jupyter notebook provided by Udacity in the 
project workspace to do all the required installations. 

## How to train the agent
- **model.py**: include a class named QNetwork which include the architecture of the neural network, any modification to the architecture could be done here
- **dqn_agent.py**: include two classes:
  - Agent: interacts with and learns from the environment, it has multiple methods to facilitate the learning process
  - ReplayBuffer: fixed-size buffer to store experience tuples for the Experience Reply
- **unityagents folder**: have the necessary files of the Unity environment
- **Navigation.ipynb**: the project notebook provided by Udacity, it have all the code necessary to read the enviroment and train an agent, it have a class named dqn which handles the training process

# Solving the project
The file **checkpoint.pth** has the trained model parametrs, the model have achived the desired rolling average of 13 on the **iteration**

# Solution Enhancments
- Nerual Network Architecture: it is an area to look into, as there might be an architecture that is more efficent in training with better performance then the provided
- Prioritized Experience Replay could be introduced to focus more on expernces which could provide more knowledge to the model
- Hyperparameters could be looked into using methods like Grid Search to enhance the learning process
