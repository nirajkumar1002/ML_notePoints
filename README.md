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


# 🧠 Machine Learning Models & When to Use Them

---

## 🔢 1. Linear Regression
- **Type**: Supervised (Regression)
- **Use When**:
  - Predicting a continuous value (e.g., house price, salary).
  - Relationship between variables is roughly linear.
- **Pros**: Simple, interpretable, fast.
- **Cons**: Poor with nonlinear or complex data.

---

## 🟠 2. Logistic Regression
- **Type**: Supervised (Classification)
- **Use When**:
  - Binary classification (e.g., spam detection, churn prediction).
- **Pros**: Simple and interpretable.
- **Cons**: Struggles with complex decision boundaries.

---

## 🌳 3. Decision Trees
- **Type**: Supervised (Classification & Regression)
- **Use When**:
  - You need an interpretable model.
  - Your features are a mix of numerical and categorical.
- **Pros**: Visualizable, handles missing values well.
- **Cons**: Prone to overfitting.

---

## 🪵 4. Random Forest
- **Type**: Supervised (Ensemble)
- **Use When**:
  - You want better accuracy than a single tree.
  - High-dimensional or messy data.
- **Pros**: Robust, reduces overfitting.
- **Cons**: Slower, less interpretable.

---

## 🚀 5. Gradient Boosting (XGBoost, LightGBM, CatBoost)
- **Type**: Supervised (Ensemble)
- **Use When**:
  - Tabular data (Kaggle-style structured data).
  - Need top predictive performance.
- **Pros**: State-of-the-art accuracy on many structured datasets.
- **Cons**: Requires tuning, longer training time.

---

## 🔁 6. K-Nearest Neighbors (KNN)
- **Type**: Supervised (Classification & Regression)
- **Use When**:
  - Your data is not very large.
  - Decision boundary is nonlinear.
- **Pros**: Simple, no training.
- **Cons**: Slow prediction, poor with high dimensions.

---

## 🧩 7. Support Vector Machines (SVM)
- **Type**: Supervised (Classification & Regression)
- **Use When**:
  - Complex, high-dimensional datasets.
  - Need a strong margin-based classifier.
- **Pros**: Effective for small- to medium-sized datasets.
- **Cons**: Not scalable to very large datasets.

---

## 🧠 8. Neural Networks (Deep Learning)
- **Type**: Supervised (Classification & Regression)
- **Use When**:
  - Image, audio, or text data (unstructured data).
  - You have lots of data and compute.
- **Pros**: High capacity, flexible, powerful.
- **Cons**: Black-box, needs a lot of data.

---

## 💾 9. Naive Bayes
- **Type**: Supervised (Classification)
- **Use When**:
  - Text classification (spam detection, sentiment).
  - Features are independent (or close to).
- **Pros**: Very fast, good with high-dimensional sparse data.
- **Cons**: Assumes feature independence.

---

## 🔍 10. K-Means Clustering
- **Type**: Unsupervised (Clustering)
- **Use When**:
  - You want to group similar data points (e.g., customer segmentation).
- **Pros**: Simple and fast.
- **Cons**: Requires number of clusters in advance.

---

## 🧬 11. Principal Component Analysis (PCA)
- **Type**: Unsupervised (Dimensionality Reduction)
- **Use When**:
  - You want to reduce features (e.g., preprocessing).
  - Visualize high-dimensional data.
- **Pros**: Speeds up models, helps avoid overfitting.
- **Cons**: Hard to interpret components.

---

## 🧠 12. Transformer Models
- **Type**: Deep Learning (NLP, Vision, Multimodal)
- **Use When**:
  - Tasks like translation, summarization, image captioning.
- **Pros**: State-of-the-art on language & multimodal tasks.
- **Cons**: Heavy compute, complex.

---

## 🌫 13. Diffusion Models
- **Type**: Generative (Unsupervised)
- **Use When**:
  - High-quality image or audio generation (e.g., DALL·E, Stable Diffusion).
- **Pros**: SOTA image generation.
- **Cons**: Training is slow, inference takes time.

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
