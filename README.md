# 🚗 Car Price Predictor

A machine learning web application that predicts the **resale price of a used car** based on key vehicle attributes. Built with Flask, scikit-learn, and Bootstrap — deployable to Heroku with a single command.

---

## 📸 Preview

> The UI features a clean, dark-themed card layout where users select their car's company, model, manufacture year, fuel type, and kilometres driven to instantly receive a predicted resale price in Indian Rupees (₹).

---

## ✨ Features

- 🔍 **Instant Price Prediction** — AJAX-powered, no page reload required
- 🏷️ **Dynamic Model Filtering** — Car models update automatically based on the selected company
- 📊 **Linear Regression Model** — Trained on real-world Indian used-car market data
- 🌐 **CORS Enabled** — API-friendly backend using `flask-cors`
- ☁️ **Production-Ready** — Deployed via Render

---

## 🛠️ Tech Stack

| Layer        | Technology                          |
|--------------|-------------------------------------|
| **Backend**  | Python 3, Flask 3.1                 |
| **ML Model** | scikit-learn (Linear Regression)    |
| **Data**     | pandas, NumPy                       |
| **Frontend** | HTML5, Bootstrap 4.5, Vanilla JS    |
| **Deploy**   | Render                              |

---

## 📁 Project Structure

```
Car_Predictor/
│
├── app.py                    # Flask application & prediction routes
├── LinearRegressionModel.pkl # Pre-trained Linear Regression model
├── Cleaned_Car_data.csv      # Cleaned dataset used for populating dropdowns
├── requirements.txt          # Python dependencies
├── Procfile                  
│
├── templates/
│   └── index.html            # Main UI (Jinja2 template)
│
└── static/
    └── css/
        └── style.css         # Custom styles
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip

### 1. Clone the Repository

```bash
git clone https://github.com/OmvedNagre/Car-Price-Predictor.git
cd Car-Price-Predictor
```

### 2. Create a Virtual Environment

```bash
python -m venv myenv
source myenv/bin/activate        # On Windows: myenv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

Open your browser and navigate to: **[http://127.0.0.1:5000](http://127.0.0.1:5000)**

---

## 🧠 How It Works

1. The app loads `Cleaned_Car_data.csv` on startup to populate all dropdown menus (companies, models, years, fuel types) dynamically.
2. The pre-trained `LinearRegressionModel.pkl` is loaded via `pickle`.
3. When the user fills out the form and clicks **"Predict Price"**, an AJAX `POST` request is sent to `/predict`.
4. The Flask backend constructs a `pandas` DataFrame from the form data and passes it to the model's `.predict()` method.
5. The predicted price (in ₹) is returned and displayed instantly on the page without a reload.

---

## 🔌 API Reference

### `GET /`

Renders the main prediction form with all dropdown options populated from the dataset.

---

### `POST /predict`

Predicts the resale price of a car.

**Request (form-data):**

| Field        | Type   | Description                          |
|--------------|--------|--------------------------------------|
| `company`    | string | Car manufacturer (e.g., `Maruti`)    |
| `car_models` | string | Car model name (e.g., `Maruti Swift`)|
| `year`       | int    | Year of manufacture (e.g., `2015`)   |
| `fuel_type`  | string | Fuel type (`Petrol`, `Diesel`, `CNG`)|
| `kilo_driven`| int    | Total kilometres driven              |

**Response:**

```
142500.75
```

A plain-text float representing the predicted price in Indian Rupees (₹).

---

## ☁️ Deployment (Render)

https://car-price-predictor-learning.onrender.com

---

## 📦 Dependencies

```
Flask==3.1.3
flask-cors==6.0.2
gunicorn==25.1.0
numpy==2.4.2
pandas==3.0.1
scikit-learn==1.6.1
scipy==1.17.0
```

> Full list available in [`requirements.txt`](./requirements.txt)

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add your feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**Omved Nagre**  
[GitHub](https://github.com/OmvedNagre) · Feel free to reach out for questions or collaborations.
