# 🦴 Osteoporosis Risk Prediction using Machine Learning  
*A Clinical Decision Support System (CDSS) for Early Detection*

---

## 📌 Project Overview

Osteoporosis impacts more than **200 million individuals globally**, leading to approximately **8.9 million fractures each year**. Despite this burden, DXA scanning—the gold standard for diagnosis—remains underutilized due to cost, accessibility challenges, and inconsistent screening practices.

This project presents a **Machine Learning–powered Clinical Decision Support System (CDSS)** designed to predict osteoporosis risk using demographic, lifestyle, and nutritional factors. The workflow includes:

- Data preprocessing  
- Model development and comparison  
- Explainable AI using SHAP  
- Clinical utility evaluation using Decision Curve Analysis (DCA)

The goal is to support **early detection** and demonstrate how ML can enhance preventive healthcare.

---

## 📂 Dataset

**Source:** Kaggle — *Lifestyle Factors Influencing Osteoporosis*  
🔗 https://www.kaggle.com/datasets/amitvkulkarni/lifestyle-factors-influencing-osteoporosis/data

- **Total Records:** 1,958  
- **Number of Features:** 15  
- **Target Variable:** `Osteoporosis` (0 = No, 1 = Yes)

### Key Features
| Feature | Type | Description |
|--------|------|-------------|
| Age | Numeric | Major determinant of bone loss |
| Gender | Categorical | Women have higher risk |
| Family History | Binary | Indicates inherited susceptibility |
| Hormonal Changes | Binary | Related to menopausal effects |
| Body Weight | Numeric | Low weight increases risk |
| Calcium Intake | Numeric | Essential for bone strength |
| Vitamin D Intake | Numeric | Supports calcium absorption |
| Physical Activity | Categorical | Helps preserve bone density |
| Prior Fractures | Binary | Significant clinical predictor |

Zero-variance features (`Alcohol Consumption`, `Medications`) were removed before modeling.

---

## 🧹 Data Preprocessing

- Duplicate removal and dataset validation  
- Median imputation for numeric variables  
- Mode imputation for categorical variables  
- One-Hot Encoding for categorical fields  
- Standardization of numeric features  
- Binary encoding of the target variable  
- SHAP applied to assess feature importance and biomedical plausibility  

---

## 🤖 Models Trained

Seven machine learning models were developed and evaluated:

1. Logistic Regression  
2. Random Forest  
3. Gradient Boosting Classifier ⭐ **Best Performer**  
4. Support Vector Machine (RBF)  
5. K-Nearest Neighbors  
6. Naïve Bayes  
7. Deep Neural Network (optional extension)

---

## 🧪 Model Evaluation

Performance was assessed using:

- **Accuracy**  
- **Precision & Recall**  
- **F1-score**  
- **Confusion Matrix**  
- **ROC Curve & AUROC**  
- **Calibration Curve**  
- **Decision Curve Analysis (DCA)**  
- **SHAP Explainability**

### ⭐ Best Model: Gradient Boosting Classifier  
Chosen because it provided:

- Excellent AUROC  
- Well-calibrated probability estimates  
- Strong net clinical benefit in DCA  
- Clinically coherent SHAP explanations  

---

## 📊 Visualizations Included

The project includes the following visual outputs:

- Confusion Matrix  
- ROC Curves  
- Calibration Curve  
- Decision Curve Analysis  
- SHAP Summary Plot  
- SHAP Force Plot (Individual Explanations)  
- Distribution Plots (Age, Calcium Intake)  
- Correlation Heatmap  

---

## 🧠 Explainable AI (XAI)

SHAP was used to interpret both global and individual predictions.

### Most Influential Predictors:
- Age  
- Hormonal Changes  
- Calcium Intake  
- Vitamin D Intake  
- Body Weight  
- Family History  

SHAP validated that the model’s reasoning aligns with established clinical literature.

---

## 🏥 CDSS Prototype

A prototype CDSS tool was developed to:

- Accept patient input data  
- Generate real-time osteoporosis risk predictions  
- Display SHAP explanations for transparent decision support  
- Assist clinicians in preventive decision-making  

Future enhancements may include EHR integration or a mobile application.

---

## 🚧 Limitations

- Dataset consists of self-reported values  
- Underrepresentation of typical older osteoporosis populations  
- Missing clinical biomarkers (e.g., BMD, laboratory values)  
- Demographic diversity limitations  

---

## 🔮 Future Work

Planned improvements include:

- Incorporation of longitudinal or clinical EHR data  
- Integration of DXA, biomarkers, or imaging features  
- Deployment of a fully interactive web/mobile CDSS  
- Fairness evaluation across demographic groups  

---

## 📁 Repository Structure

Osteoporosis-Risk-Prediction/
│
├── data/
│ └── osteoporosis.csv
│
├── notebooks/
│ └── osteoporosis_risk_prediction.ipynb
│
├── reports/
│ ├── Progress_Report_1.docx
│ ├── Progress_Report_2.docx
│ └── Final_Report.docx
│
├── images/
│ ├── confusion_matrix.png
│ ├── roc_curve.png
│ ├── calibration_curve.png
│ ├── dca_plot.png
│ └── shap_summary.png
│
└── README.md

---
## 🎥 Video Recording

A full project walkthrough demonstrating the workflow, models, and clinical decision support system is available here:

📺 **Project Walkthrough Video:**  
👉 *(Insert your video link here)*

> This includes:
> - Overview of dataset and preprocessing  
> - Model training and results  
> - SHAP explainability  
> - DCA findings  
> - CDSS prototype demonstration  

---

## REFERENCES

[1] J. A. Kanis, C. Cooper, R. Rizzoli, and J.-Y. Reginster, “European
guidance for the diagnosis and management of osteoporosis in postmenopausal
women,” Osteoporosis International, vol. 31, no. 1, pp. 3–
44, 2020.

[2] A. H. Warriner and K. G. Saag, “The use of FRAX and other clinical
risk assessment tools in osteoporosis,” Current Osteoporosis Reports,
vol. 21, no. 2, pp. 67–75, 2023.

[3] S. R. Cummings and L. J. Melton, “Epidemiology and outcomes of
osteoporotic fractures,” The Lancet, vol. 359, no. 9319, pp. 1761–1767,
2002.

[4] A. J. Vickers and E. B. Elkin, “Decision curve analysis: a novel method
for evaluating prediction models,” Medical Decision Making, vol. 26,
no. 6, pp. 565–574, 2006.

[5] S. M. Lundberg and S.-I. Lee, “A unified approach to interpreting model
predictions,” in Advances in Neural Information Processing Systems,
vol. 30, 2017, pp. 4765–4774.

[6] I. Y. Chen, P. Szolovits, and M. Ghassemi, “Interpretability and
explainability: A machine learning zoo mini-tour,” arXiv preprint
arXiv:1901.04592, 2019.

[7] Y. Du et al., “Developing and comparing deep learning and machine
learning models for osteoporosis risk prediction,” Frontiers in Artificial
Intelligence, vol. 7, 1355287, 2024.

[8] F. Amani et al., “Diagnostic accuracy of deep learning in prediction
of osteoporosis: A systematic review and meta-analysis,” BMC Musculoskeletal
Disorders, vol. 25, 991, 2024.


## Contributors
Mary Nnipaa Meteku

Instructor: Dr. Guy Hembroff

Course: Clinical Decision Support & AI Modeling


## ⚠️ Disclaimer

This project is an academic research exercise and **is not intended for clinical use, diagnosis, or treatment**.  
The machine learning models were developed using publicly available, self-reported data and have **not been clinically validated**.  
Predictions generated by this system should **not** replace professional medical judgment or standardized diagnostic procedures such as DXA scanning.  
The code, models, and analysis are provided for **educational and research purposes only**.

---

