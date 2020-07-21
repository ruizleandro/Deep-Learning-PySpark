# About Deep Learning Using PySpark
Notes about using Deep Learning models with Apache Spark.

# Deep Learning Fundamentals
Neural networks are made up of artificial neurons, that consist mainly of two parts: one is summation, and the other is activation. Summation refers to adding all the input signals, and activation refers to whether the neuron will trigger, based on the threshold value.

Let's say we have two binary inputs (X1, X2) and weights of their respective connections (W1, W2). The weights can be considered similar to coefficients of input variables in traditiona; machine learning. These weights indicate how important the particular input feature in the model is. The summation function calculates the total sum of the input.

The activation function then uses this total summated value and gives a certain output. Activation is sort of a decision-making function. Based on the type of activation function used, it gives an output accordingly. There are different types of activation functions that can be used in a neural network layer.

## Activation Functions

Activation functions play a critical role in neural networks, as the output varies, based on the type of activation function used. There are typically three main activation functions that are widely used: sigmoid, hyperbolic tangent, and rectified linear unit.

### Sigmoid

This activation function ensures that the output is always between 0 and 1, irrespective of the input. That's why it is also used in logistic regression, to predict the probability of an event.

$f(x)=\frac{1}{1+e^{-x}}$

### Hyperbolic Tangent

hyperbolic tangent activation (tanh) ensures that the output value remains between -1 to 1, regardless of the input. Following is the tanh formula:

$f(x) = \frac{e^2x - 1}{e^2x + 1}$

### Rectified Linear Unit

Rectified linear units (ReLUs) have been increasingly popular over the last few years and have become the default activation function. A ReLU is very powerful, as it produces values between 0 and infinite. If the input is 0 or less than 0, the output is always going to be 0, but for anything more than 0, the output is similar to the input. The formula for a ReLU is

$f(x) = max(0, x)$
