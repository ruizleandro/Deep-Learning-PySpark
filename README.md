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

<img src="https://render.githubusercontent.com/render/math?math=f(x)=\frac{1}{1+e^{-x}}">

### Hyperbolic Tangent

Hyperbolic tangent activation (tanh) ensures that the output value remains between -1 to 1, regardless of the input. Following is the tanh formula:

<img src="https://render.githubusercontent.com/render/math?math=f(x)=\frac{e^2x-1}{e^2x+1}">

### Rectified Linear Unit

Rectified linear units (ReLUs) have been increasingly popular over the last few years and have become the default activation function. A ReLU is very powerful, as it produces values between 0 and infinite. If the input is 0 or less than 0, the output is always going to be 0, but for anything more than 0, the output is similar to the input. The formula for a ReLU is

<img src="https://render.githubusercontent.com/render/math?math=f(x)=max(0,x)">

# Neuron Computations

Now that we have a basic understanding of different activation functions, let's consider an example, to understand how the actual output is calculated inside a neuron. Let's say we have two inputs, X1 and X2, with values of 0.2 and 0.7, respectively, and the weights are 0.05 and 0.03. The summation function calculates the total sum of incoming input signals.

The summation is as follows:

<img src="https://render.githubusercontent.com/render/math?math=sum = X1 * W1 + X2 * W2">

<img src="https://render.githubusercontent.com/render/math?math=sum = 0.2 * 0.05 + 0.7 * 0.03">

<img src="https://render.githubusercontent.com/render/math?math=sum = 0.01 + 0.021">

<img src="https://render.githubusercontent.com/render/math?math=sum = 0.031">

The next step is to pass this sum through an activation function. Let's consider using a sigmoid function, which returns values between 0 and 1, irrespective of the input. The sigmoid function will calculate the value, as follows:

<img src="https://render.githubusercontent.com/render/math?math=f(x) = \frac{1}{1 + e^-x}">

<img src="https://render.githubusercontent.com/render/math?math=f(sum) = \frac{1}{1 + e^-sum}">

<img src="https://render.githubusercontent.com/render/math?math=f(0.031) = \frac{1}{1 + e^-0.031}">

<img src="https://render.githubusercontent.com/render/math?math=f(0.031) = 0.5077">

So, the output of this single neuron is equal to 0.5077. Now that we know a single neuron operates, let's quickly go over how multiple connected neurons work together to calculate the output.


# Training Process: Neural Network

When we combine multiple neurons, we end up with a neural netwrok. Most simple and basic neural networks can be built using just input and output neurons.

The challenge with using a neural network such as this is that it can only learn linear relatioships and cannot perform well in cases in which the relationship between input and output is nonlinear. As we have seen, in real-world scenarions, the relationship is hardly simple and linear. Therefore, we must introduce an additional layer of neurons between the input and output layer, in order to increase the network's capacity to learn different kinds of nonlinear relationships. This additional layer of neurons is known as a hidden layer. It is responsible for introducing nonlinearities into the learning process of the network. Neural netwroks are also known as universal approximators, because they have the ability to approximate any relationship between input and output variables, no matter how complex and nonlinear in nature. A lot depends on the number of hidden layers in the networksa nd the total number of neurons in each hidden layer. Given sufficient numbers of hidden layers, a network can perform brilliantly at mapping this relationship.

A neural netwrok is all about various connections and different weights associated with these connections. The training of neural networks primarily includes adjusting these weights in such a way that the model can make predictions with a higher degere of accuracy. To understand how neural networks are trained, let's reak down the steps of network training:

* Step 1: Take the input values and calculate the output values that are passed to hidden neurons. The weights used for the first iteration of sum calculation are generated randomly.
An additional component that is passed is the bias neuron input. This is mainly used when you want to have some non-zero output for even the zero input values.

* Step 2: The hidden layer neurons now go through the same process to calculate the output, using the inputs from the previous layer (input layer). This hidden layer output acts as an input for the final output neuron calculation.

* Step 3: Once we have the final output, it is compared with the actual output, and the error is backpropagated to the network, to adjust the weights of the connections so as to reduce the overall error on the training data. This process is known as backpropagation.

* Step 4: Weights of the connections are readjusted according to the output, to minimize the overall errors made by the network, to the point that there is no further reduction of error on the training data.

* Step 5: Now that we have the final version of the weights, a new output value is calculated, based on updated weights, by the network.
