# SelfDrivingCar

<p align="center">
<a href = "https://github.com/yilmazvolkan/SelfDrivingCar"><img 
<img src="https://github.com/yilmazvolkan/SelfDrivingCar/blob/master/Project/project_logo.png" width="750" height="220"></a>
</p>
<p align="center">
    <a href="https://github.com/yilmazvolkan/SelfDrivingCar/blob/master/README.md">
        <img src="https://img.shields.io/badge/DESCRIPTION-ONLINE-a95209.svg"
             alt="Description">
    </a>
    <a href="https://github.com/yilmazvolkan/SelfDrivingCar/tree/master/Project">
        <img src="https://img.shields.io/badge/Project-ONLINE-da690b.svg"
             alt="Project">
    </a>
    <a href="https://github.com/yilmazvolkan/SelfDrivingCar/issues">
        <img src="https://img.shields.io/badge/ISSUES 3-CLOSED-f58c34.svg"
             alt="Issues">
    </a>
</p>

## :flashlight: Before You Go



## :tophat: Introduction

It is a self driving car model project to test on several environments easily how to AI behave. It will learn how to drive itself. It will not be given any rules on how to operate in the environment.


In the reinforcement learning, suppose there is an environment and an agent which goes around this environment. It could be a robot with some sensors on it like a Lego Mindstorms EV3 Robot. The agent is a brain (AI) that navigates through the environment and learning from the feedbacks that we are giving to it. Agent takes actions and therefore it goes one state(cell) to another. It might be closer to goal (reaching point) or further from it and with respect to these states and actions it will get rewards. Thus, it will learn what actions lead to reward. You do not preprogram to what agent to do.


Deep Q-Learning is implemented in Self Driving Car. It is a result of combining Q-Learning and Artificial Neural Network. Q represents like quality of an action. The states of the environment are encoded by a vector by means of tensor which is passed as input into ANN. Then the ANN will try to predict which action should be runned by returning Q values of possible actions as outputs. The best action to run is chosen by taking the one that has the highest Q value(E-Greedy) and rarely a random action to prevent find itself stuck in local max since it thinks it gets good rewards.


<p align="center">
<a href = "https://github.com/yilmazvolkan/SelfDrivingCar/blob/master/Project/deep_q_learning.png"><img 
<img src="https://github.com/yilmazvolkan/SelfDrivingCar/blob/master/Project/deep_q_learning.png" width="800" height="300"></a>
</p>


The most challenging part of self driving car project is when the agent learns a specific action perfectly but does not learn others as well. For example, in a long and straight road, the agent will do some actions over and over and it will learn how to move straightly since it practices a lot. However when it encounters a turn, it does not know what to do and quickly it fails to turn. These consecutive states are somehow correlated and we do not want that interdependency to bias our neural network. The solution is called experience replay in which these states don’t put through network right away, instead they are saved into memory. Thus, we take a uniformly distributed sample from these actions pouch It passed them into network to learn. Moreover, it gives an opportunity to learn from previous experiences when your environment is limit to learn.


The car and map object is created with the help of Kivy library. Three sensors detect sand which is represented with yellow color. When the car passes over sand road, it means the agent goes off the road and in return it gets negative reward. The goal is trip from left upper corner to the right bottom corner in both ways. When it reaches these points it gets positive reward.


It quickly figures out the environment and accomplishes the goal. We can see the rewards and punishments graphic:


The fall in the beginning means the agent went over the sand road and gets negative reward and quickly learns not to do again in the second time.
To improve this project, it can be added another layer to ANN to make it more deeper. Thus, it can learn relations between actions and environment more. Furthermore, new methods can be introduced about reward and punishment system. For example, it can be used a timer for how long it takes for the agent to reach the destination. If the agent does not find the destination after some particular seconds it gets a punishment (reward -= 0.2), after some amount of time more punishment (reward -= 0.4) and so on.


## :blue_book: Readings



## :beers: Contributers


<p align="left">
<a href = "https://github.com/yilmazvolkan"><img 
<img src="https://avatars2.githubusercontent.com/u/28186366?s=400&v=4" width="120" height="120"></a>
</p>

