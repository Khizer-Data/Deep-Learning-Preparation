A **perceptron** is the simplest type of artificial neural network, and it's used for **binary classification** tasks. It was first introduced by **Frank Rosenblatt in 1958**.

### Basic Idea:

A perceptron takes several inputs, applies weights to them, sums them up, and passes the result through an **activation function** (usually a step function) to produce a binary output (0 or 1).

### Formula:

Given inputs $x_1, x_2, ..., x_n$ and weights $w_1, w_2, ..., w_n$, the perceptron computes:

$$
y = 
\begin{cases}
1 & \text{if } \sum_{i=1}^{n} w_i x_i + b > 0 \\
0 & \text{otherwise}
\end{cases}
$$

* $b$ is the **bias**
* $y$ is the **output**

### Key Concepts:

* **Weights** are learned during training.
* It uses the **perceptron learning rule** to adjust weights.
* Works only for **linearly separable** data.

### Limitations:

* Cannot solve problems like XOR (non-linearly separable).
![XOR Problem](Deep_Learning/Perceptron/images/Xor_problem.jpeg)
* This led to the development of **multi-layer perceptrons (MLPs)** and **deep neural networks**, which overcome these limitations.
Deep_Learning/Perceptron/images/Xor_problem.jpeg
