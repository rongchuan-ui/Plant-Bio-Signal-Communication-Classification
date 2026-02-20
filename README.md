# Plant-Bio-Signal-Communication-Classification

A multi-class machine learning pipeline that combines **K-means clustering** with supervised models (**XGBoost, Random Forest, SVM, MLP**) to classify plant bio-signal communication states.

The project acts as a *plant signal translator*, identifying four communication states:

- **Contentment** — stable & healthy  
- **Warning** — early stress  
- **Distress** — severe stress  
- **Invitation** — growth opportunity  

---

## Motivation

Traditional plant monitoring relies on environmental thresholds or visible damage.  
However, plants emit internal physiological signals *before symptoms appear*.

**Research Question**

> Can machine learning decode plant biological signals and detect stress earlier than environmental indicators?

---

## Dataset

Simulated biological dataset (Kaggle)

- **1,000 samples**
- **10 features**
- **4 classes**

### Feature Groups

**Environmental Variables**
- Temperature
- Soil moisture
- Sunlight
- Growth rate

**Bio-Signals**
- Leaf vibration frequency
- Pollen scent complexity
- Bioluminescence intensity
- Root electrical signal
- Symbiotic fungus presence

**Target**
> Plant message type (4 communication states)

---

## Modeling Strategy

We evaluate how feature types affect prediction performance:

| Model Type | Features Used |
|----------|-------------|
| Baseline | Environmental only |
| Full | Environmental + Bio-signals |
| Full + Clustering | Adds latent cluster features |

Latent features are generated using **K-means (k = 4)** to capture hidden biological patterns.

---

## Algorithms

- Random Forest
- XGBoost
- SVM (RBF kernel)
- MLP Neural Network

### Training Setup
- Stratified train/test split (80/20)
- Feature scaling
- Cross-validation hyperparameter tuning

---

## Evaluation Metrics

Due to class imbalance, accuracy alone is insufficient.

We evaluate using:

- Accuracy
- F1-Macro
- AUC-Macro

---

## Results

### Key Findings
1. Bio-signals outperform environmental variables
2. Cluster-derived latent features consistently improve performance
3. Tree-based models generalize better than SVM/MLP

**Best Model**
> XGBoost + Bio-signals + Clustering features

---

## Insights

Feature importance reveals the strongest predictors are physiological signals:

- Pollen scent complexity
- Bioluminescence intensity
- Growth rate

This suggests plant communication is primarily encoded **internally rather than environmentally**.

---

## Visualization

The project includes:

- Feature distributions
- PCA projections
- Model comparison plots
- Confusion matrix
- Feature importance analysis

These visualizations reveal hidden structures captured by clustering features.

---

## Tech Stack

**Python · Pandas · Scikit-learn · XGBoost · Matplotlib**
