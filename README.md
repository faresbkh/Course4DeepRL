[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/42135622-e55fb586-7d12-11e8-8a54-3c31da15a90a.gif "Soccer"


# Project 3: Collaboration and Competition

### Introduction

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained Agent][image1]

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux_NoVis.zip) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)


2. Place the file in the course GitHub repository, in the base folder, and unzip (or decompress) the file. In the `Tennis.ipynb` change the cell 
    ```python
   env = UnityEnvironment(file_name="Tennis_Windows_x86_64\Tennis.exe")
   ```
   with the file name and folder corresponding to your operating system

### Description

*   The complete code is inside the `Tennis.ipynb` or `Tennis_1.ipynb` running the cells in order will 
    *   Create the environment ( do not close unity window if it stays loading for too long as you need to run the other cells while it's open )
    *   Define the Actor and Critic
    *   Define the Agent an initialise it
    *   Define ddpg algoritm
    *   Train the agents
    *   Explore the result
    *   Test the model in inference mode
    *   Close the environment ( this will close the unity window )
*   The base implementation is based on `deep-reinforcement-learning` [implementation](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum) of ddpg 
*   This repo contains these files :
    - `checkpoint_actor.pth`: saved model weights for the Actor model
    - `checkpoint_critic.pth`: saved model weights for the Critic model
    - `Tennis.ipynb`: notebook containing the solution
    - `scores_plot.png`: score evolution during training of the model
    - `Tennis_1.ipynb`: notebook containing the solution but with required average score of 1 instead of 0.5
    - `checkpoint_actor_1.pth`: saved model weights for the Actor model of score 1
    - `checkpoint_critic_1.pth`: saved model weights for the Critic model of score 1
    - `scores_plot_1_score.png`: score evolution during training of the model to reach score of 1
*   To run the project the dependencies required are in the `requirements.txt` file with instructions how to create conda environment, One major difference is the Torch version as the oldest available version of torch in python 3.6 currently is 1.7.0 which is different from the recommended version. Also torch gpu version is installed.