# Fraud-detection-system-using-ML

A machine learning project that predicts whether a financial transaction is potentially fraudulent. The project includes a Jupyter notebook for data analysis and model development, along with a Streamlit application for making predictions through a simple web interface.

## Features

- Explore transaction data using Pandas, Matplotlib, and Seaborn.
- Preprocess numerical and categorical features using a scikit-learn pipeline.
- Classify transactions using Logistic Regression.
- Handle class imbalance using balanced class weights.
- Evaluate predictions using a classification report and confusion matrix.
- Enter transaction details through an interactive Streamlit application.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Joblib
- Streamlit
- Jupyter Notebook

## Project Files

| File | Description |
|------|-------------|
| `analysis_model.ipynb` | Data analysis, preprocessing, model training, and evaluation |
| `fraud_detection.py` | Streamlit application for transaction predictions |
| `fraud_detection_pipeline.pkl` | Saved preprocessing and classification pipeline |
| `README.md` | Project overview and setup instructions |

## Model Workflow

1. Load and explore the transaction dataset.
2. Separate the input features from the target column, `isFraud`.
3. Split the data into training and testing sets using stratification.
4. Scale numerical features using `StandardScaler`.
5. Encode transaction types using `OneHotEncoder`.
6. Train a Logistic Regression model with `class_weight="balanced"`.
7. Evaluate the model on the test set.
8. Save the pipeline using Joblib and load it in the Streamlit application.

## Application Inputs

| Input | Description |
|-------|-------------|
| Transaction Type | PAYMENT, TRANSFER, or CASH_OUT |
| Amount | Transaction amount |
| Old Balance (Sender) | Sender's balance before the transaction |
| New Balance (Sender) | Sender's balance after the transaction |
| Old Balance (Receiver) | Receiver's balance before the transaction |
| New Balance (Receiver) | Receiver's balance after the transaction |

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/yasaswininarava/Fraud-detection-system-using-ML.git
cd Fraud-detection-system-using-ML
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

**Windows PowerShell:**

```powershell
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install streamlit pandas numpy matplotlib seaborn scikit-learn joblib notebook
```

For loading the saved model reliably, use the same scikit-learn version that was used during training.

### 4. Run the application

Keep `fraud_detection_pipeline.pkl` in the project folder and run:

```bash
python -m streamlit run fraud_detection.py
```

Open the local URL displayed in the terminal, usually:

```text
http://localhost:8501
```

## How to Use

1. Select the transaction type.
2. Enter the transaction amount.
3. Enter the sender's and receiver's balances before and after the transaction.
4. Click **Predict**.

The application displays:

- **0:** Predicted non-fraudulent transaction.
- **1:** Predicted potentially fraudulent transaction.

## Exploring the Notebook

To review the analysis or retrain the model, run:

```bash
jupyter notebook analysis_model.ipynb
```

Before running the notebook, download the dataset used for training and update its file path in the data-loading cell.

## Evaluation and Limitations

The notebook evaluates the model using a classification report and confusion matrix. Because fraud datasets are imbalanced, precision, recall, and F1-score should be considered alongside accuracy.

This is an educational project. Predictions can include false positives and false negatives and should not be treated as confirmed fraud decisions.

