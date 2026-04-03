🔋 VoltAI – Intelligent Battery Health Prediction System

VoltAI is an end-to-end machine learning framework for predicting State of Health (SOH) and Remaining Useful Life (RUL) of lithium-ion batteries used in electric vehicles (EVs). The project combines advanced feature engineering, multiple ML/DL models, and explainability techniques to deliver accurate and interpretable battery health insights.

📌 Project Overview

Accurate battery health monitoring is critical for:

EV safety and reliability
Predictive maintenance
Battery lifecycle optimization

VoltAI addresses this by building a unified ML pipeline that:

Predicts SOH (battery capacity degradation)
Estimates RUL (remaining charge-discharge cycles)
Translates predictions into a Battery Health Score (300–850) for real-world usability
🚀 Key Features
🔄 Unified Data Pipeline (NASA + Oxford datasets)
🧠 Multiple Models Evaluated
Random Forest ✅ (Best Performer)
XGBoost
GRU (Deep Learning)
BiLSTM + Attention
⚙️ Leakage-Safe Feature Engineering
📊 Explainability with SHAP
📈 Battery Health Score (Credit-score style)
🧪 Cross-dataset generalization
📂 Datasets Used
NASA Battery Dataset
Cycle-level lithium-ion battery data
Includes voltage, temperature, and capacity
Oxford Battery Degradation Dataset
Controlled environment dataset (40°C)
Used for validation and generalization
🧪 Methodology
1. Data Processing
Data cleaning and merging
Missing value imputation
Temporal ordering by battery cycles
2. Feature Engineering
Cycle-based features
Rolling statistics (mean, std)
Interaction features
Degradation trends
3. Target Variables
SOH = Current Capacity / Initial Capacity
RUL = Remaining cycles until end-of-life
4. Model Training
Group-based split (no data leakage)
Train / Validation / Test split
Hyperparameter tuning
🏆 Results
Model	SOH R²	RUL R²	Notes
Random Forest	0.9999	0.9982	⭐ Best overall
XGBoost	0.9820	0.9873	Strong baseline
GRU	0.1409	0.9931	Better for RUL
BiLSTM + Attention	Poor	Poor	Underperformed

👉 Insight:
Tree-based models outperformed deep learning due to structured tabular features and limited dataset size.

📊 Battery Health Score

VoltAI introduces a credit-style score (300–850):

Score = 300 + 550 × (0.65 × SOH + 0.35 × RUL_ratio)
Interpretation:
800–850 → Excellent
740–799 → Very Good
670–739 → Good
580–669 → Fair
300–579 → Poor
🔍 Explainability (SHAP)
Identifies key drivers of battery degradation
Top features:
Rolling capacity mean
Capacity change
Cycle ratio
Confirms alignment with real electrochemical behavior
🛠️ Tech Stack
Languages: Python
Libraries:
TensorFlow / Keras
Scikit-learn
XGBoost
NumPy / Pandas
Matplotlib / Seaborn
SHAP
📁 Project Structure
VoltAI/
│── data/
│── notebooks/
│── models/
│── src/
│── results/
│── README.md
⚙️ Installation
git clone https://github.com/your-username/VoltAI.git
cd VoltAI

pip install -r requirements.txt
▶️ Usage

Run the main notebook or script:

jupyter notebook

or

python main.py
📌 Applications
🚗 Electric Vehicle Battery Management Systems (BMS)
📊 Fleet Monitoring Dashboards
🔧 Predictive Maintenance Systems
🔋 Battery Lifecycle Optimization
⚠️ Limitations
Limited number of batteries in datasets
Deep learning models require more data
Battery Health Score weights are empirical
🔮 Future Work
Add real-world EV datasets
Implement Physics-Informed Neural Networks (PINNs)
Real-time model deployment in BMS
Uncertainty estimation (Bayesian models)
Model compression for embedded systems
👩‍💻 Authors
Nagham Murad
Heba Alsharif
📜 License

This project is for academic and research purposes.

⭐ Acknowledgments
NASA Battery Dataset
Oxford Battery Degradation Dataset
Fanshawe College – AI & Machine Learning Program
