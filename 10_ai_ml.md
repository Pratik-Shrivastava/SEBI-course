# Machine Learning Comprehensive Notes

# 📘 Machine Learning Comprehensive Notes

## 1. Machine Learning (ML: Machine Learning)
Machine Learning is a branch of Artificial Intelligence (AI: Artificial Intelligence) that enables computers to learn patterns from data. Instead of being explicitly programmed with rules, ML systems learn from examples and use statistical methods to make predictions. ML improves automatically as experience (data) grows.

---

## 2. Supervised Learning
Supervised Learning uses labeled data, where both input and output are known. The algorithm learns the mapping from input features to output labels. It is used when historical examples exist.

### Types
- **Regression**: Predicts continuous values (e.g., house prices).
- **Classification**: Predicts categories (e.g., spam or not spam).

### Algorithms
- Linear Regression
- Logistic Regression
- SVM (Support Vector Machine)
- Decision Trees
- Random Forest
- Gradient Boosting (XGBoost, LightGBM, CatBoost)

---

## 3. Unsupervised Learning
Unsupervised Learning deals with unlabeled data where the algorithm identifies hidden patterns without predefined outcomes.

### Types
- **Clustering**: Groups similar data points (e.g., customer segmentation).
- **Dimensionality Reduction**: Reduces high-dimensional data (e.g., PCA: Principal Component Analysis).
- **Association Rules**: Finds relationships among variables (e.g., Apriori for market basket analysis).

### Algorithms
- K-Means
- DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
- Hierarchical Clustering
- PCA (Principal Component Analysis)
- Apriori Algorithm

---

## 4. Data Preprocessing
Data Preprocessing prepares raw data for ML models by cleaning, transforming, and structuring it.

### Subtopics
- **Handling Missing Values**: Replace with mean/median or remove.
- **Encoding Categorical Variables**: Convert categories to numerical values.
- **Feature Scaling**: Normalize or standardize features.
- **Outlier Detection**: Identify and handle abnormal data points.
- **Train-Test Split**: Divide data for fair evaluation.

### Important Formulas
**Standardization (Z-score):**  
`z = (x - μ) / σ`

**Min-Max Scaling:**  
`x' = (x - min) / (max - min)`

---

## 5. Model Evaluation
Evaluates model performance on unseen data.

### Classification Metrics
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**
- **ROC-AUC**

### Regression Metrics
- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R² Score (Coefficient of Determination)

---

## 6. Linear Regression
Linear Regression predicts a continuous output by fitting a best-fit line.

### Formula
`y = β0 + β1x1 + ... + βnxn`

---

## 7. Logistic Regression
Used for binary classification.

### Sigmoid Function
`σ(z) = 1 / (1 + e^-z)`

---

## 8. Decision Trees
Decision Trees split data using rules based on features to classify or predict outcomes.

### Split Criteria
- Gini Impurity
- Entropy (Information Gain)

---

## 9. Clustering
Unsupervised technique to group similar data.

### K-Means Formula (Distance)
`d = √((x1 - x2)² + (y1 - y2)²)`

---

## 10. Feature Engineering
Transforms raw data into meaningful features.

### Techniques
- Binning
- Polynomial Features
- Encoding
- Log Transform
- Interaction Features

---

## 11. Python for ML
### Libraries
- NumPy (Numerical Python)
- Pandas (Python Data Analysis Library)
- Matplotlib
- Seaborn
- Scikit-learn

---

## 12. TensorFlow
Deep learning framework by Google.

### Key Features
- Static computation graph (older versions)
- TF 2.x supports eager execution
- TensorBoard visualization
- Strong deployment support

---

## 13. PyTorch
Deep learning library by Meta (Facebook).

### Why PyTorch > TensorFlow (for research)
- Uses **Dynamic Computation Graph** → easier debugging.
- More pythonic and intuitive.
- Preferred in academia.

---

## 14. Scikit-Learn
Library for classical ML algorithms.

### Features
- Preprocessing
- Model Selection
- Classification & Regression
- Clustering
- Pipelines

---

## 15. NLP (Natural Language Processing)
Allows computers to understand human language.

### Tasks
- Tokenization
- Stopword Removal
- Lemmatization/Stemming
- Named Entity Recognition (NER)

---

## 16. Sentiment Analysis
Determines emotional tone in text.

### Methods
- Traditional ML (Logistic Regression, SVM)
- Deep Learning (LSTM: Long Short-Term Memory)
- Transformers (BERT: Bidirectional Encoder Representations from Transformers)

---

## 17. Neural Networks (NN: Neural Networks)
ML models inspired by biological neurons.

### Components
- Input Layer
- Hidden Layers
- Output Layer
- Weights
- Activation Functions (ReLU, Sigmoid, Tanh, Softmax)

---

## 18. Overfitting & Underfitting
### Overfitting
Model memorizes training data.

**Fixes:** Regularization, Dropout, Early Stopping

### Underfitting
Model fails to learn correctly.

**Fixes:** Add features, increase model complexity

---

## 19. Cross-Validation
Technique to measure generalization performance.

### K-Fold CV
Data is split into K parts; model trains on K-1 parts and tests on 1.

---

## 20. Reinforcement Learning (RL: Reinforcement Learning)
Algorithm learns by interacting with an environment.

### Key Terms
- Agent
- Environment
- Reward
- Policy
- Value Function

---

## 21. Cloud AI Services
### AWS
- SageMaker
- Comprehend
- Rekognition

### GCP (Google Cloud Platform)
- Vertex AI
- AutoML

### Azure
- Cognitive Services
- ML Studio

---

## 22. Deployment Basics
### Methods
- REST API (Representational State Transfer Application Programming Interface)
- Docker
- Kubernetes
- TensorFlow Serving
- TorchServe

---

**End of Document**

