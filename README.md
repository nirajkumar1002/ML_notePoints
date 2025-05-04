# ML_notePoints

# 📘 Types of Machine Learning Problems

Machine learning problems are generally categorized based on the type of output you're trying to predict. The main categories are:

---

## 🔵 1. Supervised Learning

You have **input features (X)** and a known **target/output (y)**.

### ✅ Common Types:

| Problem Type     | Description                | Example                               | Output Type     |
|------------------|----------------------------|----------------------------------------|-----------------|
| **Regression**   | Predict a continuous value | Predict house price, insurance premium | Real number     |
| **Classification** | Predict a category/label | Spam detection, disease diagnosis      | Class label     |

---

## 🟡 2. Unsupervised Learning

You have **only input data** and no labeled output — the goal is to discover patterns or structure in the data.

### ✅ Common Types:

| Problem Type           | Description                        | Example                        | Output Type         |
|------------------------|------------------------------------|--------------------------------|----------------------|
| **Clustering**         | Group similar data points          | Customer segmentation          | Cluster label        |
| **Dimensionality Reduction** | Reduce data dimensions      | PCA, t-SNE for visualization   | Compressed features  |
| **Anomaly Detection**  | Detect unusual data points         | Fraud detection                | Binary flag or score |

---

## 🟢 3. Reinforcement Learning

An **agent learns by interacting with an environment** and receiving rewards or penalties.

| Problem Type           | Description                        | Example                        |
|------------------------|------------------------------------|--------------------------------|
| **Policy Optimization / Control** | Learn best actions over time | Playing games, robotics       |

---

## 🧩 Bonus: Specialized or Hybrid Tasks

| Task                         | Related Category          | Example                          |
|------------------------------|---------------------------|----------------------------------|
| **Time-Series Forecasting**  | Regression / Sequence     | Stock price prediction           |
| **Recommendation Systems**   | Hybrid                    | Netflix movie suggestions        |
| **Natural Language Processing (NLP)** | Usually Supervised | Sentiment analysis, text generation |

---

> ✅ Use this cheat-sheet to identify your problem type and pick suitable models accordingly.




# ✅ What is RMSLE?

**RMSLE** stands for:

> **Root Mean Squared Logarithmic Error**

It’s a metric that:

- 📏 Measures the difference between predicted and actual values  
- 📉 Uses a **logarithmic scale**, reducing the impact of large differences  
- 📊 Focuses more on **relative errors** (percent-style differences) rather than absolute ones  

---

## 📌 RMSLE Formula

\[
\text{RMSLE} = \sqrt{ \frac{1}{n} \sum_{i=1}^{n} \left( \log(1 + \hat{y}_i) - \log(1 + y_i) \right)^2 }
\]

Where:

- \(\hat{y}_i\) = predicted value  
- \(y_i\) = actual value  
- \(n\) = number of samples  

📎 **Note:** The `+1` inside the log is important — it prevents errors when values are zero (`log(0)` is undefined).

---

## 🔍 Why Use RMSLE Instead of RMSE?

| Aspect               | RMSE                                  | RMSLE                                          |
|----------------------|----------------------------------------|------------------------------------------------|
| Error Scale          | Absolute differences                   | Relative (log-transformed) differences         |
| Effect of Outliers   | High                                   | Reduced impact                                |
| Penalizes            | All errors equally                     | Underestimates more gently                     |
| Useful When          | Exact values matter                    | Relative size matters (e.g., price, sales)     |

---

## 🔄 Example

Let’s say:

- Actual: `[10, 100, 1,000]`  
- Predicted: `[12, 90, 1,200]`

With **RMSE**, the large difference on 1,000 vs 1,200 dominates the error.

With **RMSLE**:

- \(\log(1 + 1000) \approx \log(1001) \approx 6.91\)  
- \(\log(1 + 1200) \approx \log(1201) \approx 7.09\)  

So the squared difference is only \((7.09 - 6.91)^2 = 0.0324\), a **much smaller and fairer penalty** in log-space.

---

## ⚠️ Important Note

- **RMSLE only works for non-negative values**  
- If your target or predictions contain negative numbers, use a different metric like RMSE or MAE

---
