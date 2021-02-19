## Hyperparameter tuning
All Neural net project has to be adjusted. In this project the following parameter were choosen:
The neural net is a 37x64x64x4 size. (Input 37, 2 hidden layer and the output is 4)


BUFFER_SIZE = int(1e5)  # replay buffer size - we can define how many experiences we would like to collect
BATCH_SIZE = 128         # minibatch size - That depends of the memory mainly. The 128 was sufficient for this project. 
GAMMA = 0.99            # discount factor - I left it as a standard
TAU = 1e-3              # for soft update of target parameters
LR = 1e-3               # learning rate - We are using Adam optimizer, and with the combination of a buffer size it had a nice speed to converge
UPDATE_EVERY = 2        # how often to update the network - I tried with 1-6 and 2 was performing the best

def dqn(n_episodes=2000, max_t=1000, eps_start=0.55, eps_end=0.01, eps_decay=0.985):
Changing the epsilon had the most effect for me. The 0.55 and the 0.985 was a good combo. I usually changed them together since we basically making it smaller and small at each iteration(episode)

I tuned the values to be fast to reach the 13 points. I would have used probably a smaller learning rate, the UPDATE_EVERY would have been bigger, and also the epsilon. - if the task would be to reach as much as we can.

The training result:

![result](https://github.com/plitkei/RL-Unity-MLAgents-Python-Pytorch-Banana.app/blob/main/result.jpg)
