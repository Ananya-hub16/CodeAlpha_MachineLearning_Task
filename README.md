<div align="center">

# 🤖 Machine Learning Projects Portfolio

[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)

> **A curated collection of Machine Learning & Deep Learning projects** covering image recognition, medical diagnosis, and financial credit scoring — from classical ML to neural networks.

</div>

---

## 📁 Projects Overview

| # | Project | Type | Algorithm | Accuracy |
|---|---------|------|-----------|----------|
| 1 | 🔢 MNIST Digit Recognition | Deep Learning | Neural Network (Dense) | ~98%+ |
| 2 | 🔤 EMNIST Letter Recognition | Deep Learning | Neural Network (Dense) | High |
| 3 | 🎗️ Breast Cancer Detection | Classical ML | SVM, RF, LR & more | **98.2%** |
| 4 | 💳 Credit Score Classification | Classical ML + Boosting | XGBoost, Random Forest | High |

---

## 🔢 Project 1 — MNIST Handwritten Digit Recognition

> Classify handwritten digits (0–9) using a fully connected neural network trained on the iconic MNIST dataset.

### 🏗️ Architecture
```
Input (28×28) → Flatten → Dense(128, ReLU) → Dense(10, Softmax)
```

### ⚙️ Key Details
- **Dataset:** 60,000 training / 10,000 test grayscale images (28×28 pixels)
- **Normalization:** Pixel values scaled to [0, 1]
- **Labels:** One-hot encoded for 10 digit classes
- **Optimizer:** Adam | **Loss:** Categorical Crossentropy
- **Training:** 5 epochs, batch size 32

### 📦 Dependencies
```bash
pip install tensorflow matplotlib
```

---

## 🔤 Project 2 — EMNIST Handwritten Letter Recognition

> Extended version of MNIST — classifies handwritten **English letters** (A–Z) using the EMNIST Letters dataset.

### 🏗️ Architecture
```
Input (28×28) → Flatten → Dense Layers → Softmax (26 classes)
```

### ⚙️ Key Details
- **Dataset:** EMNIST Letters CSV (`emnist-letters-train.csv` / `emnist-letters-test.csv`)
- **Train/Val Split:** 80/20 using `train_test_split`
- **Callbacks:** EarlyStopping · ReduceLROnPlateau · ModelCheckpoint
- **Classes:** 26 letter categories

### 📦 Dependencies
```bash
pip install tensorflow pandas numpy matplotlib
```

---

## 🎗️ Project 3 — Breast Cancer Detection

> Predict whether a tumor is **Malignant** or **Benign** using 30 clinical features. Benchmarks **7 classical ML models** side by side.

### 📊 Dataset
- **Source:** `sklearn.datasets.load_breast_cancer` (built-in)
- **Samples:** 569 patients | **Features:** 30 (radius, texture, perimeter, area, etc.)
- **Target:** `0 = Malignant (212)` · `1 = Benign (357)`
- **Split:** 80% Train / 20% Test | Scaled with `StandardScaler`

### 🏆 Model Comparison Results

| Model | Accuracy |
|-------|----------|
| 🥇 **SVM** | **98.2%** |
| 🥈 Logistic Regression | 97.4% |
| 🥉 Random Forest | 96.5% |
| Naive Bayes | 96.5% |
| Gradient Boosting | 95.6% |
| KNN | 94.7% |
| Decision Tree | 94.7% |

### 📦 Dependencies
```bash
pip install scikit-learn pandas numpy
```

---

## 💳 Project 4 — Credit Score Classification

> Predict a customer's credit score (**Good / Standard / Poor**) from financial history, payment behaviour, and engineered features.

### 📊 Dataset
- **Source:** `train.csv` / `test.csv` (Kaggle-style dataset)
- **Preprocessing Pipeline:**
  - Dropped irrelevant columns: `ID`, `Customer_ID`, `Name`, `SSN`, `Month`
  - Imputed missing values: Median (numerical) · Mode (categorical)
  - Cleaned dirty numeric strings (regex)
  - Capped outliers using 1st–99th percentile IQR method
  - Encoded categoricals with `LabelEncoder`
  - Scaled features with `RobustScaler`

### 🔧 Feature Engineering
| New Feature | Formula | Insight |
|---|---|---|
| `Debt_to_Income` | Outstanding Debt / Annual Income | Financial stress ratio |
| `EMI_to_Salary` | Total EMI / Monthly Salary | Loan burden |
| `Savings_Ratio` | Amount Invested / Monthly Salary | Savings behaviour |
| `High_Utilization` | Credit Utilization > 30% (0/1) | Over-leveraged flag |
| `Has_Delayed` | Delayed Payments > 0 (0/1) | Payment reliability |

### 🏆 Models Benchmarked
- Logistic Regression · Decision Tree · **Random Forest** · Extra Trees · Gradient Boosting · **XGBoost**
- Best model auto-selected, predictions saved to `predictions.csv`

### 📦 Dependencies
```bash
pip install scikit-learn xgboost pandas numpy matplotlib seaborn
```

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ml-projects-portfolio.git
cd ml-projects-portfolio
```

### 2. Install All Dependencies
```bash
pip install tensorflow scikit-learn xgboost pandas numpy matplotlib seaborn
```

### 3. Launch Jupyter
```bash
jupyter notebook
```

### 4. Open Any Notebook
| Notebook | Description |
|----------|-------------|
| `MNIST.ipynb` | Digit recognition with neural networks |
| `EMNIST.ipynb` | Letter recognition with deep learning |
| `Brest_cancer.ipynb` | Medical diagnosis with classical ML |
| `credit_score.ipynb` | Financial scoring with ensemble models |

---

## 🛠️ Tech Stack

<div align="center">

| Category | Tools |
|---|---|
| **Language** | Python 3.12 |
| **Deep Learning** | TensorFlow / Keras |
| **Classical ML** | Scikit-Learn, XGBoost |
| **Data** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Environment** | Jupyter Notebook |

</div>

---

## 📂 Project Structure

```
📦 ml-projects-portfolio/
├── 📓 MNIST.ipynb              # Digit recognition (Deep Learning)
├── 📓 EMNIST.ipynb             # Letter recognition (Deep Learning)
├── 📓 Brest_cancer.ipynb       # Cancer detection (Classical ML)
├── 📓 credit_score.ipynb       # Credit scoring (Ensemble ML)
├── 📄 README.md                # You are here!
└── 📁 data/
    ├── emnist-letters-train.csv
    ├── emnist-letters-test.csv
    ├── train.csv                # Credit score training data
    └── test.csv                 # Credit score test data
```

---

## 🌟 Highlights

- ✅ **Beginner-friendly** — clean, well-commented code in every notebook
- ✅ **End-to-end pipelines** — data loading → preprocessing → training → evaluation
- ✅ **Multi-model benchmarking** — compare multiple algorithms on the same dataset
- ✅ **Real-world datasets** — medical imaging, financial data, and handwriting recognition
- ✅ **Feature engineering** — domain-driven features crafted for the credit score project

---

<div align="center">

Made with ❤️ and lots of ☕

⭐ **Star this repo if you found it helpful!** ⭐

</div>
