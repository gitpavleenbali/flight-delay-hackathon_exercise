# 🎯 Flight Delay Hackathon - Copilot Instructions

> 🤖 **This file is automatically read by GitHub Copilot!**
> 
> Everything below gives Copilot context about YOUR project, making its suggestions 
> more accurate and relevant. Notice how Copilot's responses change when it knows 
> about your dataset, tech stack, and coding standards!

---

## Project Overview

This is a Flight Delay Prediction application. Users select a day of the week 
and destination airport to see the probability of their flight being delayed 
by more than 15 minutes.

## Dataset Information

The `data/flights.csv` dataset contains 271,000+ flight records from 2013 with:

| Column | Description |
|--------|-------------|
| `DayOfWeek` | 1 (Monday) to 7 (Sunday) |
| `DestAirportID` | Unique numeric ID for destination airport |
| `DestAirportName` | Full name of destination airport |
| `ArrDel15` | Binary: 1 = delayed >15 min, 0 = on time |
| `ArrDelay` | Minutes of arrival delay (negative = early) |
| `DepDel15` | Binary: 1 = departure delayed >15 min |
| `DepDelay` | Minutes of departure delay |
| `Carrier` | Airline code (AA, UA, DL, etc.) |

## Technical Stack

When helping with this project, use:

- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Machine Learning**: scikit-learn (LogisticRegression recommended)
- **API Framework**: Flask or FastAPI
- **Frontend**: HTML/CSS/JavaScript (vanilla or React/Vue/Svelte)

## Key Tasks

1. **Data Cleaning**: 
   - Fill null values in `DepDel15` with 0
   - Remove outliers (flights beyond 90th percentile for `ArrDelay`)

2. **Model Training**:
   - Features: `DayOfWeek`, `DestAirportID`
   - Target: `ArrDel15`
   - Algorithm: Logistic Regression
   - Export: pickle format to `server/model.pkl`

3. **API Endpoints**:
   - `GET /predict?day_of_week={1-7}&airport_id={id}` → Returns delay probability
   - `GET /airports` → Returns sorted list of airports with IDs

4. **Frontend**:
   - Dropdown for day of week
   - Dropdown for airports (loaded from API)
   - Display prediction with color-coded risk levels

## Coding Standards

- Use descriptive variable names (e.g., `flight_data` not `fd`)
- Add docstrings to functions
- Handle errors gracefully with try/except
- Enable CORS for API endpoints
- Use type hints where possible

## File Structure

When generating code, follow this structure:
```
├── data/flights.csv           # Source dataset
├── manage-flight-data.ipynb   # Jupyter notebook for ML
├── server/
│   ├── app.py                 # Flask/FastAPI server
│   ├── model.pkl              # Trained model
│   ├── airports.csv           # Airport ID-name mapping
│   └── requirements.txt       # Python dependencies
└── client/
    └── index.html             # Web frontend
```

---

> 💡 **Try it!** Open Copilot Chat and ask: *"What columns are in the flights dataset?"*
> Copilot will use this file to give you an accurate answer!

