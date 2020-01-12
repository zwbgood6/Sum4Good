# Angela Schoellig - CORL, 2019

## Future of automation

- large prior uncertainties

- **active decision making**

- expect safe and high-performance behavior

## Two approaches for robots:

1. Control Approach

**system model**: describe the robots' bahavior through the system model -> 

**system identification**: collect the data to identify the model parameters (need data collection) ->

**controller design**: design the feedback controller (control policy) based on this model

This approach works really well in the a) **controlled environemnts** (since we can write down the possible parametrized models in these environments). b) If we can have the model and access the design process, we can **use** the **robustness** to analyze the **model error** and guarantee safety/stability by modeling errors. c) Design feedback controller to satisfy **safety constraints**.

Pros:

Control (systems): 

+model: take model and feedback into account, we can guarantee safety and consider the worst-case,

+feedback, 

+safety, 

+worst-case: for worst cases, I can consider the whole class of models and design controller for all of them,

Cons:

-learning, 

-data

If we have a good understanding about the models, then we can use the model. However, if we consider the models in the 
real-world applications (e.g. self-driving cars), the **model** would **be** really **large** since there are various road/weather/people conditions. 

Thus, **optimizing over the worst-case** (e.g considering all possible worst cases) is extremely **conservative** 
even that is possible. The performance of the next generation of robots is limited by the model understanding. If we cannot
have an accurate model (or even we have a good model but it is very conservative), the performance of robots will be heavily limited. 

This **motivates** us that the **system should learn and adapt**. In control community, adaptation is a thing that people have not looked at, especially not collecting data during online operations.


2. Reinforcement learning approach

**no system model** here if using model-free RL. ->

**data sameples**: same as system identification in control methods, which collect the data to identify the model parameters ->

**controller optimization**: optimize contoller

Pros:

collecting **relevant data** for the task (**in controlled robot environment**)

work well for game-like environment (e.g. GO, atari games)

simulation (e.g. Gym environments)

Cons:

performance typically in **expectation** (since we maximize the expectation of the reward). Thus, it cannot guarantee safety.

data inefficiency: need to collect a lot of data to consider all the cases.

3. Comparison
```
------------------------------------------------------------------------------------------
|    Control (systems)    |    Machine Learning (data)   |          Combination          |
|-------------------------|------------------------------|-------------------------------|
| + Models                | + Data collection            | - Combine Models and data.    |
|-------------------------|------------------------------|                               |
| + Feedback              | + Learning                   | - System must learn and adapt.|
|-------------------------|------------------------------|                               |
| + Safety                | + Explore/exploit            | - Safety, data efficiency.    |
|-------------------------|------------------------------|                               |
| + Worst-case            | + Average case               |                               |
|-------------------------|------------------------------|                               |
| - Learning              | - Worst-case                 |                               |
|-------------------------|------------------------------|                               |
| - Data                  | - Safety                     |                               |
|-------------------------|------------------------------|                               |
| Performance limited     | Safety limited by lack of    |                               |
| by system understanding | system understanding         |                               |
------------------------------------------------------------------------------------------
```

