### Basic Idea:

A perceptron takes several inputs, applies weights to them, sums them up, and passes the result through an **activation function** (usually a step function) to produce a binary output (0 or 1).
<div align="center">

<img src="https://github.com/Khizer-Data/Deep-Learning-Preparation-/raw/main/Deep_Learning/Perceptron/images/Perceptron.jpeg" alt="🌟 Perceptron 🌟" width="300" title="Perceptron">

</div>

A **perceptron** is the simplest type of artificial neural network, and it's used for **binary classification** tasks. It was first introduced by **Frank Rosenblatt in 1958**.

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

### 1. **Weights (w)** 🏋️‍♂️
- **What?** Numbers set at the start to weigh each input’s importance.
- **Initialization**: Randomly set, often in range **[-1, 1]** or **[-0.1, 0.1]** for small steps.
- **Auto-Update**: Adjusted during learning to reduce errors using the learning rule.
- **Think of it like**: Tuning how much each input “matters.”

---

### 2. **Bias (b)** ⚖️
- **What?** A constant also set at the start to shift the decision boundary.
- **Initialization**: Often set to **0** or a small random value like **[-0.1, 0.1]**.
- **Auto-Update**: Tweaked automatically with the learning rule.
- **Think of it like**: A nudge to get the prediction just right.
- **Why?** Makes the perceptron flexible to fit data better.

---

### 3. **Perceptron Learning Rule** 📚
- **What?** The recipe to automatically update weights and bias when predictions are wrong.
- **How?** If predicted output \( \hat{y} \) ≠ actual output \( y \):
    - Weight: w_i = w_i + η * (y - ŷ) * x_i
    - Bias: b = b + η * (y - ŷ)
- **Think of it like**: Fixing the recipe after a bad cake! 🥮
- **Auto?** Yes! Updates happen every time the perceptron learns.

---

### 4. **Learning Rate (η)** ⚙️
- **What?** A small number (e.g., **0.01** or **0.001**) that controls how much weights and bias change.
- **Why Small?** Small steps prevent overshooting the best solution, ensuring steady learning.
- **Think of it like**: Fine-tuning a radio dial to get the perfect signal. 🎛️
- **Why Important?** Too big (e.g., 1.0) = wild jumps, missing the target. Too small (e.g., 0.0001) = super slow learning.
- **Typical Range**: **0.001 to 0.1**, tweaked to optimize results.

---

### 5. **Activation Function** 🚀
- **What?** A function that decides whether the perceptron should output 0 or 1.
- **Common Choices**: Step function (0 or 1), Sigmoid function (0 to 1), ReLU (rectified linear unit).
- **Think of it like**: A switch that decides if the cake is good or not.
- **why?** To make the perceptron learn complex patterns.
- **Step Function** is a simple one:
  - If \( z \) is positive, output 1.
  - If \( z \) is negative or zero, output 0.
- **Example**: If \( z = 0.5 \), the step function outputs 1.

---

🖼️ How It Works

Start: Initialize random weights (e.g., between -0.1 and 0.1) and bias (e.g., 0).
Process: Multiply each input (x1, x2, ...) by its weight, sum them, and add the bias:z = (w1 * x1 + w2 * x2 + ...) + b


Predict: Pass z through an activation function (like a yes/no switch) to get the output ŷ.
Learn: If ŷ is wrong, the learning rule updates weights and bias using the learning rate to reduce errors.
Repeat: Keep predicting and learning until the perceptron is good at classifying.

---

### Advantages:

* Simple to understand and implement.
* Works well for linearly separable data.


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

## Real-Life Example: Decision to Go for a Walk

We'll use a perceptron to decide whether to go for a walk based on two factors:

* x₁: Is it sunny? (1 = Yes, 0 = No)
* x₂: Do you have free time? (1 = Yes, 0 = No)

The perceptron will predict:
* ŷ = 1 → Go for a walk
* ŷ = 0 → Don't go for a walk

## Perceptron Parameters

Our perceptron has:
* Weights: w₁ = 0.6, w₂ = 0.4
* Bias: b = -0.5
* Activation function: Step function

```
step(z) = {
    1 if z ≥ 0
    0 if z < 0
}
```

## Perceptron Formula

For any input, we calculate:

1. The weighted sum (including bias): z = w₁x₁ + w₂x₂ + b
2. Apply the activation function: ŷ = step(z)

## Example 1: Sunny but No Free Time

Input:
* x₁ = 1 (It is sunny)
* x₂ = 0 (You don't have free time)

Calculation:
1. Weighted sum:
   ```
   z = w₁x₁ + w₂x₂ + b
   z = (0.6 × 1) + (0.4 × 0) + (-0.5)
   z = 0.6 + 0 - 0.5 = 0.1
   ```

2. Apply activation function:
   ```
   ŷ = step(z) = step(0.1) = 1
   ```

Decision: Since ŷ = 1, the perceptron recommends going for a walk.

## Example 2: Not Sunny but Have Free Time

Input:
* x₁ = 0 (Not sunny)
* x₂ = 1 (You have free time)

Calculation:
1. Weighted sum:
   ```
   z = w₁x₁ + w₂x₂ + b
   z = (0.6 × 0) + (0.4 × 1) + (-0.5)
   z = 0 + 0.4 - 0.5 = -0.1
   ```

2. Apply activation function:
   ```
   ŷ = step(z) = step(-0.1) = 0
   ```

Decision: Since ŷ = 0, the perceptron recommends not going for a walk.

## Example 3: Sunny and Have Free Time

Input:
* x₁ = 1 (It is sunny)
* x₂ = 1 (You have free time)

Calculation:
1. Weighted sum:
   ```
   z = w₁x₁ + w₂x₂ + b
   z = (0.6 × 1) + (0.4 × 1) + (-0.5)
   z = 0.6 + 0.4 - 0.5 = 0.5
   ```

2. Apply activation function:
   ```
   ŷ = step(z) = step(0.5) = 1
   ```

Decision: Since ŷ = 1, the perceptron recommends going for a walk.

## Example 4: Not Sunny and No Free Time

Input:
* x₁ = 0 (Not sunny)
* x₂ = 0 (You don't have free time)

Calculation:
1. Weighted sum:
   ```
   z = w₁x₁ + w₂x₂ + b
   z = (0.6 × 0) + (0.4 × 0) + (-0.5)
   z = 0 + 0 - 0.5 = -0.5
   ```

2. Apply activation function:
   ```
   ŷ = step(z) = step(-0.5) = 0
   ```

Decision: Since ŷ = 0, the perceptron recommends not going for a walk.

## Interpretation of the Weights

- The weight for "sunny" ($w_1 = 0.6$) is higher than the weight for "free time" ($w_2 = 0.4$), indicating that good weather has more influence on the decision to go for a walk than having free time.
- The bias ($b = -0.5$) is negative, which means there's a default inclination not to go for a walk unless the positive factors are strong enough.
- For the perceptron to recommend going for a walk ($z \geq 0$), you need either:
  * Sunny weather (which contributes 0.6 to the sum), or
  * Both factors to be positive (sunny and free time)

## Complete Truth Table

| x₁ (Sunny) | x₂ (Free Time) | Weighted Sum (z) | Output (ŷ) | Decision |
|------------|----------------|------------------|------------|----------|
| 0 | 0 | 0 + 0 - 0.5 = -0.5 | 0 | Don't go |
| 0 | 1 | 0 + 0.4 - 0.5 = -0.1 | 0 | Don't go |
| 1 | 0 | 0.6 + 0 - 0.5 = 0.1 | 1 | Go for a walk |
| 1 | 1 | 0.6 + 0.4 - 0.5 = 0.5 | 1 | Go for a walk |

## Decision Boundary

The perceptron's decision boundary is the line where z = 0:

```
w₁x₁ + w₂x₂ + b = 0
0.6x₁ + 0.4x₂ - 0.5 = 0
0.6x₁ + 0.4x₂ = 0.5
```

This equation represents the line that separates the "go for a walk" region from the "don't go for a walk" region in the feature space.

## Code from Scratch in notebook

 - link: [code_from_scratch.ipynb](https://github.com/Khizer-Data/Deep-Learning-Preparation-/blob/main/Deep_Learning/Perceptron/code_from_scratch.ipynb)

 ---

 ## Code from Libraries in notebook

 - link: [code_from_libraries.ipynb](https://github.com/Khizer-Data/Deep-Learning-Preparation-/blob/main/Deep_Learning/Perceptron/code_from_libraries.ipynb)

 
### Thank you for reading! 🌟
