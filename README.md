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

# Getting Started

All the required libraries are there in the requirements.txt, there is an option to use the command **!pip -q install .** in the project Jupyter notebook provided by Udacity in the 
workspace to do all the required installations. 
