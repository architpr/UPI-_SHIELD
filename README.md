# UPI-_SHIELD
🛡️ UPI Shield: Real-Time Fraud Detection API & Web App
This project is an end-to-end machine learning application designed to detect fraudulent transactions in real-time. It uses a powerful XGBoost model trained on a credit card fraud dataset to simulate a UPI fraud detection system. The model is served via a high-performance FastAPI backend and includes an interactive web interface built with Streamlit.

(Action Required: Replace the link above with a link to your own screenshot of the Streamlit app running!)

✨ Features
Real-Time Predictions: Get instant fraud risk scores for transaction data.

High-Performance API: Built with FastAPI for fast, asynchronous request handling.

Powerful ML Model: Utilizes an XGBoost Classifier, optimized to handle highly imbalanced datasets.

Interactive UI: A user-friendly web interface built with Streamlit to demonstrate the model's predictions visually.

End-to-End Workflow: Covers the complete machine learning lifecycle from data preparation and model training to deployment as an API.

🛠️ Tech Stack
Backend: Python, FastAPI

Machine Learning: Scikit-learn, XGBoost, Pandas, Joblib

Frontend: Streamlit

API Server: Uvicorn

Data Communication: Requests

📂 Project Structure
upi-shield/
│
├── venv/                 # Virtual environment folder
├── creditcard.csv        # The raw dataset used for training
├── fraud_model.pkl       # The serialized, pre-trained XGBoost model
├── main.py               # The FastAPI application script
├── train_model.py        # The script to train and save the ML model
├── streamlit_app.py      # The Streamlit frontend application script
└── README.md             # This file

🚀 Local Setup and How to Run
Follow these steps to set up and run the project on your local machine.

Prerequisites
Python 3.8+

A virtual environment tool (like venv)

Step 1: Clone the Repository
git clone [https://github.com/YOUR_USERNAME/upi-shield.git](https://github.com/architpr/UPI-_SHIELD)
cd upi-shield



Step 2: Create and Activate a Virtual Environment
# For Windows
python -m venv venv
.\venv\Scripts\activate



Step 3: Install Dependencies
Install all the required libraries from the requirements.txt file.
(First, create a requirements.txt file by running pip freeze > requirements.txt in your activated terminal).

pip install -r requirements.txt


Step 4: Train the Model (One-time setup)
Run the training script to generate the fraud_model.pkl file.

python train_model.py


Step 5: Run the Application
You need to run two servers in two separate terminals.

Terminal 1: Start the FastAPI Backend

uvicorn main:app --reload

The API will be available at http://127.0.0.1:8000.

Terminal 2: Start the Streamlit Frontend

streamlit run streamlit_app.py

The web application will open automatically in your browser at http://localhost:8501.




🔗 API Endpoints
The FastAPI server provides the following endpoints:

GET /

Description: A root endpoint to check if the API is running.

Response: {"message": "UPI Shield Fraud Detection API is running!"}

POST /predict

Description: Analyzes transaction data and returns a fraud prediction.

Request Body: A JSON object containing 30 features (Time, V1-V28, Amount).

