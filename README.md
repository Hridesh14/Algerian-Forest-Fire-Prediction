# Algerian Forest Fire FWI Prediction App

A **real-time Fire Weather Index (FWI) prediction web application** built with **Flask**, **Scikit-learn**, and **Ridge Regression**. Uses the **Algerian Forest Fires Dataset** to predict fire danger based on weather and fuel conditions.


---

## Features

- **Real-time FWI Prediction** via interactive web form
- **Side-by-side layout**: Input on left, result with **animated fire** on right
- **Fire Status & Region** dropdowns (Bejaia / Sidi Bel-abbes)
- **ISI field highlighted** for emphasis
- **Responsive & Mobile-Friendly**
- **Glassmorphism UI** with floating fire sparks
- **No rounding** — exact model output
- **Trained on 244 real fire events (2012)**

---

## Dataset

- **Source**: [Algerian Forest Fires Dataset](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset++)
- **Regions**: Bejaia (0), Sidi Bel-abbes (1)
- **Features Used**:
  - `Temperature`, `RH`, `Ws`, `Rain`
  - `FFMC`, `DMC`, `ISI`
  - `Classes` (fire / not fire)
  - `Region`

---

## Model Performance

| Model           | R² Score | MAE  |
|---------------|----------|------|
| **Ridge Regression** | **0.98** | **0.45** |
| Lasso         | 0.96     | 0.72 |
| Linear        | 0.97     | 0.58 |

**Ridge selected** for best balance of accuracy & robustness.

---

## Tech Stack

| Technology       | Purpose |
|------------------|--------|
| **Python**       | Core logic |
| **Flask**        | Web framework |
| **Scikit-learn** | Model training & scaling |
| **Pandas/NumPy** | Data processing |
| **HTML/CSS/JS**  | Frontend (glassmorphism + animations) |
| **Bootstrap 5**  | Responsive design |
| **Pickle**       | Model persistence |

---

## Project Structure
Algerian-Forest-Fire-Prediction/
│
├── application.py                  # Flask app
├── model/
│   ├── ridge.pkl                   # Trained model
│   └── Scaler.pkl                  # StandardScaler
├── templates/
│   ├── index.html                  # Landing page
│   └── home.html                   # Prediction page (side-by-side)
├── Algerian_forest_fires_dataset_cleaned.csv
├── model_training.ipynb            # Model training & comparison
├── requirements.txt
└── README.md

---

## How to Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/Algerian-Forest-Fire-Prediction.git
cd Algerian-Forest-Fire-Prediction

# 2. Create virtual environment (optional)
python -m venv venv
source venv/bin/activate    # Linux/Mac
venv\Scripts\activate       # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the app
python application.py
Open browser: http://127.0.0.1:5000
Input,Value
Temperature,32
RH,64
Ws,14
Rain,0.0
FFMC,79.9
DMC,7.3
ISI,2.3
Fire Status,not fire
Region,Bejaia , Sidi Bel-abbes 
## My Role
- Data preprocessing & EDA
- Model selection (Ridge > Lasso > Linear)
- Flask backend with prediction pipeline
- Full frontend design (with AI-assisted prototyping)
- Deployment-ready with `requirements.txt`


