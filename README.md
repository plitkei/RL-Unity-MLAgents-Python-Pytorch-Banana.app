# Reinforcement_Learning
RL algorithms

[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Introduction

In this project we are going to train an Agent to play a modified version of the "banana" environment from Unity. The original one can be still found at the MLAgent Github page. Just make sure to choose the right release like release 0.5.0.

![Trained Agent][image1]

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Getting Started 

The environment I have used:

    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

You just need to unzip it and reference it from the project.

# Build your own Unity environment

I would recommend to choose a fresh environmnet from the current ML-Agent github repo. 
It is a bit more work at the begining, since you have to compile it for your system and you also need to install Unity. 
The problem with the very old versions like this. It is almost immpossible to collect the right (old) versions of the python/pytorch/ML-Agents circle -just to name a few.

If you have the curtesy to use a newer app. In the navigation.ipynb 
do not use the:  *from unityagents import UnityEnvironment*
Use the **from mlagents_envs.environment import UnityEnvironment**
The unityagents are in a different folder in the newer version. So you **Do not** need to pip install unityagents. there is package called like this and that is a very old version of the ML-Agents.

This is how u can set up a new environment:
https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Installation.md


*Basically, there is a Unity application what we will call from python with the ML-Agents help. That will be the connection between the unity app and the pytorch code in order to train the Agent.*


We have our model in the **model.py** file.
And the DQN algorithm that uses the model in the **dqn_agent.py** file.
The connection between unity and the model is in the **navigation.ipynb**

# We are going to use DQN - Deep Q-Learning to solve this task.

In the **dqn_agent.py** there is a standard implementation of a DQN algorithm using Experience replay and Fix Q Target. A very similiar modell was used at deepmind to learn all the Atari game. [click here to read more about it](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf)
The **model.py** is a "standard" MLP which we use to determine the best action for a current state. These two files are used in the **navigation.ipynb**

The beauty of these algorithms that you can apply it for other games/problems as well. You just have to adjust the MLP input and output size to adapt to your project.

Normally the weights can be quite big. I decided to upload it because it has a relative small size. Usi it to compare if you want to. **checkpoint.pth**






