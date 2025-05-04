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
