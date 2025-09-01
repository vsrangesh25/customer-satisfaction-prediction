# 📝 Customer Satisfaction Prediction

This project uses **Machine Learning** to predict customer satisfaction ratings from customer support tickets.  
It analyzes text (ticket subject, description, resolution) and metadata (priority, purchase date, resolution time, etc.) to classify customer satisfaction on a scale of 1–5.

---

## 📂 Project Structure
```
customer-satisfaction-prediction/
│── customer_satisfaction_prediction.py   # Main script (training + evaluation)
│── customer_support_tickets.csv          # Dataset
│── README.md                             # Project documentation
│── requirements.txt                      # Python dependencies
│── .gitignore                            # Git ignore rules
```
---

## 🚀 Features
- Data preprocessing:
  - Handling missing values
  - Feature engineering (dates, priorities, keyword signals)
  - TF-IDF vectorization of ticket text
- Models implemented:
  - Logistic Regression
  - LightGBM (Gradient Boosting)
- Evaluation metrics:
  - Accuracy
  - Macro F1-Score
  - Quadratic Weighted Kappa (QWK)
  - Confusion Matrix
  - Precision-Recall and ROC curves
- Model persistence with **joblib** (saves the best model for reuse)

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/customer-satisfaction-prediction.git
cd customer-satisfaction-prediction
```

Create a virtual environment (recommended) and install dependencies:

```bash
python -m venv .venv
# Windows PowerShell:
.\.venv\Scripts\Activate.ps1
# Git Bash:
source .venv/Scripts/activate

pip install -r requirements.txt
```

---

## ▶️ Usage

Make sure `customer_support_tickets.csv` is in the repository root (same folder as the script), then run:

```bash
python customer_satisfaction_prediction.py
```

The script will:
1. Load the dataset (`customer_support_tickets.csv`)
2. Train Logistic Regression & LightGBM models
3. Print metrics for both
4. Plot performance comparisons
5. Save the best model as `customer_support_model.pkl`

> If you see a `FileNotFoundError`, ensure the CSV file is named exactly `customer_support_tickets.csv` and is placed in the project root.

---

## 📊 Example Output

Example (truncated) metrics:

```
Logistic Regression Metrics:
{
  "model": "logreg",
  "cv_accuracy_mean": 0.72,
  "test_accuracy": 0.74,
  "macro_f1": 0.71,
  "qwk": 0.68
}
```

---

## 📈 Future Improvements
- Deploy as a REST API with Flask/FastAPI
- Add more advanced NLP features (BERT embeddings)
- Hyperparameter optimization with Optuna
- Expand dataset for better generalization

---

## 👨‍💻 Author
**V. S. Rangesh**  
GitHub: https://github.com/<your-username>

---

⭐ If you find this project useful, don’t forget to **star the repo**!
