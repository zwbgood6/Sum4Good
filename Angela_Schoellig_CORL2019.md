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

This approach works really well in the a) **controlled environemnts** (since we can write down the possible parametrized models in
these environments). b) If we can have the model and access the design process, we can **use** the **robustness** to analyze the **model** 
error** and guarantee safety/stability by modeling errors. c) Design feedback controller to satisfy safety constraints.

(systems): +model, +feedback, +safety, +worst-case, -learning, -data

Pros:

- If we have a good understanding about the models, then we can use the model. However, if we consider the models in the 
real-world applications (e.g. self-driving cars), the model would be really large since there are various road/weather/people 
conditions. Thus, optimizing over the worst-case (e.g considering all possible worst cases) is extremely conservative 
even that is possible.

Cons:
