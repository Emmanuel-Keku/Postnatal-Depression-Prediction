# Predictive Models for Early Detection of Postnatal Depression in Women

### 📚 Course: Math 5364 - Data Science 1 | Spring 2025
### 🏫 Tarleton State University
### 👨‍🎓 Author: Emmanuel Keku (001143396)
### 👨‍🏫 Supervisor: Dr. Scott Cook

---

## 📌 Problem Statement
Postnatal depression (PND) affects 10%–20% of women globally,
with rates as high as 30% in low- and middle-income countries.
Despite its prevalence, many cases go undiagnosed due to 
limited screening tools and healthcare access.

This project develops and evaluates machine learning models 
to predict feelings of anxiety — a key early indicator of 
postnatal depression — using self-reported symptom data from 
postpartum women.

---

## 🎯 Objectives
- Identify key risk factors associated with postnatal depression
- Build and compare multiple predictive machine learning models
- Evaluate model performance using F1-score and AUC metrics
- Provide actionable insights for clinical decision support

---

## 📊 Dataset
- **Source:** Kaggle 
  (Originally collected via Google Forms by a medical hospital)
- **Records:** 1,503 postpartum women
- **Features:** 10 attributes (after dropping Timestamp)
- **Target Variable:** `feeling_anxious` 
  (Binary: Yes/No — proxy for postnatal depression)
- **Class Distribution:** 65% anxious, 35% not anxious 
  (slightly imbalanced)

### Key Features
| Variable | Description |
|----------|-------------|
| Age | Age group: 25–50 |
| Feeling sad or tearful | Emotional state |
| Irritable towards baby & partner | Behavioral response |
| Trouble sleeping at night | Sleep pattern |
| Problems concentrating | Cognitive symptoms |
| Overeating or loss of appetite | Eating habits |
| Feeling of guilt | Emotional symptom |
| Problems bonding with baby | Attachment issues |
| Suicide attempt | Self-harm risk indicator |
| **Feeling anxious** | **Target Variable** |

---

## 🛠️ Tools & Technologies
- **Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Libraries:** 
  - Data: `Pandas`, `NumPy`
  - Visualization: `Matplotlib`, `Seaborn`, `Plotly`
  - Modeling: `Scikit-learn`, `FLAML (AutoML)`, `XGBoost`
  - Imbalance Handling: `imbalanced-learn` (SMOTE, SMOTETomek)
  - Explainability: `Permutation Importance`

---

## 📋 Methodology

### 1. Data Preprocessing
- Dropped non-informative Timestamp column
- Handled 27 missing values using mode imputation 
  grouped by age bracket
- Applied label encoding to target variable
- Applied ordinal encoding for age
- Applied dummy encoding for all other categorical features

### 2. Exploratory Data Analysis (EDA)
- Visualized class distribution of target variable
- Generated count plots for all features vs target
- Computed Theil's U (Uncertainty Coefficient) 
  for feature correlation
- Key Finding: `Problems of bonding with baby` showed 
  the strongest positive correlation with anxiety

### 3. Model Building
Used **FLAML (Fast and Lightweight AutoML)** framework 
to automatically select and optimize the best model.

Models trained and evaluated:
- ✅ **HistGradientBoostingClassifier** ← Best Model
- ✅ **ExtraTreesClassifier** (via FLAML AutoML)
- ✅ Logistic Regression
- ✅ Random Forest
- ✅ Support Vector Machine (SVM)
- ✅ Gradient Boosting

### 4. Evaluation Strategy
- 80/20 Holdout train-test split
- 5-Fold Cross Validation
- Primary Metric: **F1-Score** (due to class imbalance)
- Secondary Metrics: AUC, Accuracy, Precision, Recall
- Subgroup analysis across demographic groups

---

## 🏆 Results

| Model | CV Accuracy | Holdout Accuracy |
|-------|-------------|-----------------|
| **HistGradientBoostingClassifier** | **97.42%** | **97.67%** |
| ExtraTreesClassifier (FLAML) | 95.93% | 97.34% |

### Key Findings
- 🥇 **Best Model:** HistGradientBoostingClassifier
- 📈 **Holdout Accuracy:** 97.67%
- 🎯 **F1-Score:** Above 0.94 for both classes
- ⚖️ **Equity:** Consistent performance across all subgroups

### Most Important Predictive Features
1. 😴 Trouble sleeping at night
2. 😢 Feeling sad or tearful
3. 🍽️ Appetite disturbances
4. 🧠 Concentration problems
5. ⚠️ Suicidal thoughts

---

## 💡 Conclusions
- Machine learning models can accurately predict anxiety 
  in postpartum women using routine screening data
- The HistGradientBoostingClassifier is the preferred model 
  due to its superior accuracy and robustness
- Models showed low risk of bias across demographic subgroups
- Insomnia, persistent sadness, and suicidal thoughts are 
  the strongest clinical indicators

## 🔮 Future Work
- Model calibration and temporal validation
- Integration with Electronic Health Record (EHR) systems
- Deployment as a real-time clinical decision support tool
- Exploration of deep learning approaches (RNN-LSTM)

---

## 📁 Project Files
| File | Description |
|------|-------------|
| `DS1_FINAL_PROJECT_Emmanuel-Keku.ipynb` | Full Jupyter Notebook |

---

## 🔗 Related Projects
- [Capstone: Hybrid Bayesian-Ensemble Framework 
  for Perinatal Depression Detection](link-coming-soon)
- [Mayaro Virus Transmission Modeling](link-coming-soon)

---

## 📚 Key References
1. Wilson et al. (2022). Prevalence of postnatal depression 
   in LMICs. *Psychological Medicine*
2. Zhang et al. (2020). ML algorithms for predicting PPD. 
   *Frontiers in Psychiatry*
3. Zafar et al. (2025). Deep learning for perinatal 
   depression prediction. *Computers in Biology and Medicine*

---

## 📫 Contact
- 📧 **Email:** ekekuinchrist247@gmail.com
- 🔬 **ORCID:** https://orcid.org/0000-0001-5864-4843
- 🐙 **GitHub:** https://github.com/Emmanuel-Keku
