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
<div align="center">

<img src="https://github.com/Khizer-Data/Deep-Learning-Preparation-/raw/main/Deep_Learning/Perceptron/images/Xor_problem.jpeg" alt="🌟 XOR Problem 🌟" width="300" title="The XOR Problem Explained">

<p style="text-align: center; color: #4682b4; font-style: italic;">A fun look at the XOR problem! 🔢</p>

</div>

Great! Let’s go step-by-step:

---

### **1. XOR & Non-Linearity**

The **XOR (exclusive OR)** logic is:

| Input A | Input B | Output A XOR B |
| ------- | ------- | -------------- |
| 0       | 0       | 0              |
| 0       | 1       | 1              |
| 1       | 0       | 1              |
| 1       | 1       | 0              |

Now plot these points:

* (0, 0) → 0
* (0, 1) → 1
* (1, 0) → 1
* (1, 1) → 0

There is **no single straight line** that can separate the output classes (0 vs. 1) — this is what we mean by **non-linear**. The **basic perceptron fails** to solve this.


* This led to the development of **multi-layer perceptrons (MLPs)** and **deep neural networks**, which overcome these limitations.
Deep_Learning/Perceptron/images/Xor_problem.jpeg
