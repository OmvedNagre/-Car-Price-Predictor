# Car Price Predictor

A Flask-based web application that predicts the selling price of a used car based on user inputs such as company, model, year, fuel type, and kilometers driven.

---

## Overview

This project uses a trained Scikit-learn Linear Regression model to estimate car prices. The frontend collects user input and sends it to the Flask backend using AJAX. The predicted price is returned instantly and displayed on the page.

---

## Tech Stack

- Flask  
- Scikit-learn  
- Pandas  
- NumPy  
- Bootstrap  
- Gunicorn  

---

## Project Structure

Car_Predictor/
│
├── app.py  
├── requirements.txt  
├── Procfile  
├── LinearRegressionModel.pkl  
├── Cleaned_Car_data.csv  
├── templates/  
│   └── index.html  
└── static/  
    └── css/  
        └── style.css  

---

## Run Locally

Create virtual environment:

python3 -m venv myenv  
source myenv/bin/activate  

Install dependencies:

pip install -r requirements.txt  

Run the application:

python app.py  

Open in browser:

http://127.0.0.1:5000  

---

## Deployment (Render)

Build Command:
pip install -r requirements.txt  

Start Command:
gunicorn app:app  

---
