<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=30&pause=1000&color=7C6DFA&center=true&vCenter=true&width=500&lines=🤖+ML+Projects+Portfolio;Deep+Learning+%26+Classical+ML;From+Pixels+to+Predictions" alt="Typing SVG" />

<br/>

![Python](https://img.shields.io/badge/Python-3.12-4ec9fb?style=for-the-badge&logo=python&logoColor=white&labelColor=0a0a0f)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-ff8c42?style=for-the-badge&logo=tensorflow&logoColor=white&labelColor=0a0a0f)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-f7931e?style=for-the-badge&logo=scikit-learn&logoColor=white&labelColor=0a0a0f)
![XGBoost](https://img.shields.io/badge/XGBoost-Enabled-00cc6a?style=for-the-badge&logo=xgboost&logoColor=white&labelColor=0a0a0f)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-f37626?style=for-the-badge&logo=jupyter&logoColor=white&labelColor=0a0a0f)

<br/>

> **A curated collection of Machine Learning & Deep Learning projects**  
> covering image recognition, medical diagnosis, and financial credit scoring.

</div>

---

## 📁 Projects at a Glance

<div align="center">

| # | 📓 Notebook | 🏷️ Task | ⚙️ Method | 🎯 Best Score |
|:---:|---|---|---|:---:|
| 01 | `MNIST.ipynb` | Digit Recognition | Neural Network (Dense) | `~98%+` |
| 02 | `EMNIST.ipynb` | Letter Recognition (A–Z) | Deep Learning + Callbacks | `High` |
| 03 | `Brest_cancer.ipynb` | Tumor Diagnosis | 7 Classical ML Models | `98.2%` ⭐ |
| 04 | `credit_score.ipynb` | Credit Scoring | XGBoost + Ensemble | `High` |

</div>

---

## 🔢 Project 01 — MNIST Digit Recognition

Classify handwritten digits **0–9** using a fully connected neural network.

```
Input (28×28) ──▶ Flatten ──▶ Dense(128, ReLU) ──▶ Dense(10, Softmax) ──▶ Prediction
```

**Dataset** · 60,000 train / 10,000 test · Normalized to `[0, 1]` · One-hot encoded labels  
**Training** · Adam optimizer · Categorical Crossentropy loss · 5 epochs · Batch size 32

```bash
pip install tensorflow matplotlib
```

---

## 🔤 Project 02 — EMNIST Letter Recognition

Extends MNIST to classify **26 handwritten English letters** from the EMNIST dataset.

**Highlights:**
- CSV-based EMNIST Letters dataset (train + test)
- 80/20 train-validation split via `train_test_split`
- Advanced callbacks: `EarlyStopping` · `ReduceLROnPlateau` · `ModelCheckpoint`

```bash
pip install tensorflow pandas numpy matplotlib
```

---

## 🎗️ Project 03 — Breast Cancer Detection

Predicts **Malignant vs Benign** tumors using 30 clinical features. Benchmarks **7 models** side-by-side.

**Dataset** · `sklearn.datasets.load_breast_cancer` · 569 samples · 30 features · 80/20 split + `StandardScaler`

### 🏆 Model Leaderboard

```
┌─────────────────────────┬──────────────────────────────────────┬──────────┐
│ Rank  Model             │ ██████████████████████████████████████│ Accuracy │
├─────────────────────────┼──────────────────────────────────────┼──────────┤
│  🥇   SVM               │ ████████████████████████████████████ │  98.2%   │
│  🥈   Logistic Reg.     │ ███████████████████████████████████  │  97.4%   │
│  🥉   Random Forest     │ ██████████████████████████████████   │  96.5%   │
│  4    Naive Bayes       │ ██████████████████████████████████   │  96.5%   │
│  5    Gradient Boosting │ █████████████████████████████████    │  95.6%   │
│  6    KNN               │ ████████████████████████████████     │  94.7%   │
│  7    Decision Tree     │ ████████████████████████████████     │  94.7%   │
└─────────────────────────┴──────────────────────────────────────┴──────────┘
```

```bash
pip install scikit-learn pandas numpy
```

---

## 💳 Project 04 — Credit Score Classification

Predicts **Good / Standard / Poor** credit score from financial history and behavioral features.

**Full preprocessing pipeline:**

```
Raw CSV ──▶ Drop IDs ──▶ Impute (Median/Mode) ──▶ Clean Dirty Strings
        ──▶ Cap Outliers (IQR) ──▶ Feature Engineering ──▶ LabelEncode
        ──▶ RobustScaler ──▶ Train/Val Split ──▶ Benchmark Models
```

**Engineered Features:**

| Feature | Formula | Captures |
|---|---|---|
| `Debt_to_Income` | Outstanding Debt ÷ Annual Income | Financial stress |
| `EMI_to_Salary` | Total EMI ÷ Monthly Salary | Loan burden |
| `Savings_Ratio` | Amount Invested ÷ Monthly Salary | Saving behaviour |
| `High_Utilization` | Credit Utilization > 30% → 1/0 | Over-leverage flag |
| `Has_Delayed` | Delayed Payments > 0 → 1/0 | Payment reliability |

**Models compared:** Logistic Regression · Decision Tree · **Random Forest** · Extra Trees · Gradient Boosting · **XGBoost** ← best model auto-selected

```bash
pip install scikit-learn xgboost pandas numpy matplotlib seaborn
```

---

## 🚀 Getting Started

```bash
# 1 — Clone
git clone https://github.com/your-username/ml-portfolio.git
cd ml-portfolio

# 2 — Install dependencies
pip install tensorflow scikit-learn xgboost pandas numpy matplotlib seaborn

# 3 — Launch
jupyter notebook
```

---

## 🛠️ Tech Stack

<div align="center">

| | Tool | Role |
|---|---|---|
| 🐍 | Python 3.12 | Core language |
| ⚡ | TensorFlow / Keras | Deep learning |
| 🔬 | Scikit-Learn | Classical ML |
| 🌲 | XGBoost | Gradient boosting |
| 🐼 | Pandas · NumPy | Data manipulation |
| 📊 | Matplotlib · Seaborn | Visualization |
| 📓 | Jupyter Notebook | Development environment |

</div>

---

## 📂 Repo Structure

```
📦 ml-portfolio/
├── 📓 MNIST.ipynb              ← Digit recognition (Deep Learning)
├── 📓 EMNIST.ipynb             ← Letter recognition (Deep Learning)
├── 📓 Brest_cancer.ipynb       ← Cancer detection (Classical ML)
├── 📓 credit_score.ipynb       ← Credit scoring (Ensemble ML)
├── 📄 README.md
└── 📁 data/
    ├── emnist-letters-train.csv
    ├── emnist-letters-test.csv
    ├── train.csv
    └── test.csv
```

---

## ✨ What Makes This Portfolio Stand Out

- ✅ **End-to-end pipelines** — data loading → preprocessing → training → evaluation in one notebook
- ✅ **Multi-model benchmarking** — 6–7 algorithms compared on the same dataset
- ✅ **Smart feature engineering** — 5 domain-driven features for credit scoring
- ✅ **Real-world datasets** — medical imaging, financial data, handwriting recognition
- ✅ **Clean, commented code** — readable notebooks anyone can follow
- ✅ **Production-ready preprocessing** — IQR outlier capping, RobustScaler, LabelEncoder

---

<div align="center">

Made with ❤️ and lots of ☕

**⭐ Star this repo if it helped you! ⭐**

</div>
