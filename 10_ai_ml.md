# ARTIFICIAL INTELLIGENCE & MACHINE LEARNING (Expanded Conceptual Guide)

## 📊 MODEL LIFECYCLE SUMMARY
**Data → Preprocess → Train Model → Evaluate → Deploy → Monitor**

---

## 🧠 1. MACHINE LEARNING – BASICS
**Concept:** Systems learn from data patterns without explicit programming.

**Flow:**
```
Input Data → Model → Predictions → Feedback
```

**Types:**
- **Supervised:** labeled data  
- **Unsupervised:** unlabeled  
- **Reinforcement:** reward-based

**Example:**
```python
from sklearn.linear_model import LinearRegression
model = LinearRegression().fit(X_train, y_train)
```

**MCQs:**
1️⃣ Learns from → ✅ Data  
2️⃣ Unlabeled data → ✅ Unsupervised  
3️⃣ Reward learning → ✅ Reinforcement

---

## 📘 2. SUPERVISED LEARNING
**Concept:** Learn mapping X→Y with labeled data.
```
X (features) → Model → Y (target)
```
**Algorithms:** Linear, Logistic Regression, Decision Trees

**Example:**
```python
model.fit(X_train, y_train)
```

**MCQs:**
1️⃣ Needs labels → ✅ Yes  
2️⃣ Regression output → ✅ Continuous  
3️⃣ Classification → ✅ Category

---

## 🔍 3. UNSUPERVISED LEARNING
**Concept:** Find hidden structures in unlabeled data.
```
Input → Clustering/Dim.Reduction → Patterns
```
**Algorithms:** K-Means, PCA

**Example:**
```python
from sklearn.cluster import KMeans
KMeans(n_clusters=3).fit(X)
```

**MCQs:**
1️⃣ Works with → ✅ Unlabeled data  
2️⃣ K-Means → ✅ Clustering  
3️⃣ PCA → ✅ Dimensionality reduction

---

## 🧹 4. DATA PREPROCESSING
**Concept:** Clean and prepare raw data.
```
Missing → Encode → Scale → Split
```
**Example:**
```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

**MCQs:**
1️⃣ Missing data → ✅ Imputation  
2️⃣ Scaling → ✅ Normalization  
3️⃣ Categorical → ✅ Encoding

---

## 🧪 5. MODEL EVALUATION
**Concept:** Assess model accuracy.

| Task | Metric |
|------|---------|
| Classification | Accuracy, F1 |
| Regression | RMSE, MAE |
| Clustering | Silhouette |

**Example:**
```python
from sklearn.metrics import accuracy_score
accuracy_score(y_test, y_pred)
```

**MCQs:**
1️⃣ Accuracy → ✅ Classification  
2️⃣ RMSE → ✅ Regression  
3️⃣ Silhouette → ✅ Clustering

---

## 📈 6. LINEAR REGRESSION
**Concept:** Models linear relation.
```
y = β₀ + β₁x + ε
```
**Example:**
```python
from sklearn.linear_model import LinearRegression
LinearRegression().fit(X, y)
```

**MCQs:**
1️⃣ Type → ✅ Linear  
2️⃣ Output → ✅ Continuous  
3️⃣ Use → ✅ Prediction

---

## ⚙️ 7. LOGISTIC REGRESSION
**Concept:** Binary classification using sigmoid.
```
P(y=1)=1/(1+e^-(β₀+β₁x))
```
**Example:**
```python
from sklearn.linear_model import LogisticRegression
```

**MCQs:**
1️⃣ Output → ✅ Probability  
2️⃣ Use → ✅ Classification  
3️⃣ Function → ✅ Sigmoid

---

## 🌲 8. DECISION TREES
**Concept:** Tree structure splitting data by features.
```
Feature? → Yes → LeafA / No → LeafB
```
**Example:**
```python
from sklearn.tree import DecisionTreeClassifier
```

**MCQs:**
1️⃣ Structure → ✅ Hierarchical  
2️⃣ Overfit risk → ✅ Deep trees  
3️⃣ Handles categorical → ✅ Yes

---

## 🧭 9. CLUSTERING
**Concept:** Group similar data points.
```
Points → Distance → Clusters
```
**Example:**
```python
from sklearn.cluster import KMeans
```

**MCQs:**
1️⃣ K = → ✅ Number of clusters  
2️⃣ Type → ✅ Unsupervised  
3️⃣ Output → ✅ Cluster labels

---

## 🧱 10. FEATURE ENGINEERING
**Concept:** Create/transform features for better models.  
Steps: **Selection • Extraction • Encoding • Scaling**

**MCQs:**
1️⃣ Goal → ✅ Improve performance  
2️⃣ Categorical → ✅ One-hot  
3️⃣ Scaling part of → ✅ Feature Eng.

---

## 🐍 11. PYTHON FOR ML
**Libraries:** NumPy, Pandas, Matplotlib, Scikit-learn

**Example:**
```python
import pandas as pd
df = pd.read_csv('data.csv')
```

**MCQs:**
1️⃣ DataFrame → ✅ Pandas  
2️⃣ Arrays → ✅ NumPy  
3️⃣ Plot → ✅ Matplotlib

---

## 🔡 12. TENSORFLOW
**Concept:** Google’s deep-learning library.
```
Define → Compile → Train → Evaluate
```
**Example:**
```python
import tensorflow as tf
```

**MCQs:**
1️⃣ Creator → ✅ Google  
2️⃣ Use → ✅ Deep Learning  
3️⃣ High-level API → ✅ Keras

---

## 🔥 13. PYTORCH
**Concept:** Meta’s dynamic deep-learning framework.
```python
import torch
x=torch.tensor([1,2,3])
```

**MCQs:**
1️⃣ Creator → ✅ Meta  
2️⃣ GPU support → ✅ Yes  
3️⃣ Uses → ✅ Dynamic graphs

---

## ⚙️ 14. SCIKIT-LEARN
**Concept:** Classical ML toolkit.
```python
from sklearn.model_selection import train_test_split
```

**MCQs:**
1️⃣ Library type → ✅ ML toolkit  
2️⃣ Built on → ✅ NumPy/SciPy  
3️⃣ Function → ✅ fit/predict

---

## 🗣 15. NLP
**Concept:** Text understanding by computers.  
**Tasks:** Tokenization, POS tagging, NER
```python
from nltk.tokenize import word_tokenize
```

**MCQs:**
1️⃣ Handles → ✅ Text data  
2️⃣ Library → ✅ NLTK/Spacy  
3️⃣ Tokenization → ✅ Split text

---

## ❤️ 16. SENTIMENT ANALYSIS
**Concept:** Detect polarity (positive/negative).
```python
from textblob import TextBlob
TextBlob("Good work").sentiment
```

**MCQs:**
1️⃣ Output → ✅ Polarity score  
2️⃣ Library → ✅ TextBlob  
3️⃣ NLP task → ✅ Yes

---

## 🧬 17. NEURAL NETWORKS
**Concept:** Brain-inspired layered model.
```
Input → Hidden → Output
```
**Example:**
```python
from tensorflow.keras import layers, models
```

**MCQs:**
1️⃣ Inspired by → ✅ Brain  
2️⃣ Adds non-linearity → ✅ Activation  
3️⃣ Structure → ✅ Layers

---

## ⚖️ 18. OVERFITTING / UNDERFITTING
| Type | Meaning | Fix |
|------|----------|-----|
| Overfit | Learns noise | Regularization, dropout |
| Underfit | Too simple | Complex model |

**MCQs:**
1️⃣ Noise learning → ✅ Overfit  
2️⃣ Low accuracy → ✅ Underfit  
3️⃣ Fix → ✅ Regularization

---

## 🔁 19. CROSS-VALIDATION
**Concept:** K-Fold validation for robust testing.
```
Data → Split → Train/Test → Average score
```
**Example:**
```python
from sklearn.model_selection import KFold
```

**MCQs:**
1️⃣ Improves → ✅ Reliability  
2️⃣ Typical folds → ✅ 5/10  
3️⃣ In library → ✅ sklearn

---

## 🎮 20. REINFORCEMENT LEARNING
**Concept:** Agent learns via rewards.
```
Agent → Action → Env → Reward → Update
```
**Algorithms:** Q-Learning, DQN

**MCQs:**
1️⃣ Learns from → ✅ Reward feedback  
2️⃣ Interacts with → ✅ Environment  
3️⃣ Example algo → ✅ Q-Learning

---

## ☁️ 21. CLOUD AI SERVICES
| Platform | Service | Use |
|-----------|----------|-----|
| AWS | SageMaker | Model build/deploy |
| Azure | ML Studio | Drag-and-drop |
| GCP | Vertex AI | End-to-end ML |
| IBM | Watson | NLP APIs |

**MCQs:**
1️⃣ AWS ML → ✅ SageMaker  
2️⃣ GCP AI → ✅ Vertex AI  
3️⃣ IBM → ✅ Watson

---

## 🚀 22. DEPLOYMENT BASICS
**Concept:** Expose trained model via APIs.
```
Model → Pickle → Flask API → Client
```
**Example:**
```python
import joblib
joblib.dump(model,'model.pkl')
```

**MCQs:**
1️⃣ Save model → ✅ Pickle/joblib  
2️⃣ API → ✅ Flask/FastAPI  
3️⃣ Container → ✅ Docker

---

## 📘 FORMULA & LIBRARY QUICK SHEET
| Concept | Equation / Function | Library |
|----------|---------------------|----------|
| Linear Regression | y = β₀+β₁x | sklearn.linear_model |
| Logistic | Sigmoid: 1/(1+e^-x) | sklearn.linear_model |
| Eval | accuracy_score, r2_score | sklearn.metrics |
| Clustering | KMeans(n_clusters=k) | sklearn.cluster |
| NN | Dense(), Sequential() | tf.keras / torch.nn |
| Save Model | joblib.dump() | joblib |
| Cross-Val | KFold() | sklearn.model_selection |

---

## ✅ FINAL REVISION TABLE
| Concept | Key Idea | Example / Tool |
|----------|-----------|----------------|
| Supervised | Labeled data | Regression, Tree |
| Unsupervised | Unlabeled | K-Means |
| Preprocess | Clean data | Scaling, Encoding |
| Eval | Metrics | Accuracy, RMSE |
| Overfit | Too complex | Dropout |
| Cross-Val | Reliable test | K-Fold |
| Deployment | API serve | Flask/Docker |

---

## 🧠 IFSCA EXAM TIPS
✅ Supervised vs Unsupervised – labeled vs unlabeled  
✅ Regression → continuous, Classification → categorical  
✅ Overfitting → High train, low test accuracy  
✅ TensorFlow = Google; PyTorch = Meta; scikit-learn = classic ML  
✅ Reward-based RL = Q-Learning, DQ