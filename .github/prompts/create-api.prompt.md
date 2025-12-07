# ⚡ Create API Server

> 📋 **This is a Prompt File!** Use it by typing `#create-api` or `/create-api` in Copilot Chat.
> 
> - `#` attaches the prompt as context (you can add more to your message)
> - `/` runs the prompt directly as a command

---

## My Goal

Create an API that serves predictions and airport data.

## Endpoints I Need

| Endpoint | Method | Parameters | Returns |
|----------|--------|------------|--------|
| `/predict` | GET | `day_of_week` (1-7), `airport_id` (int) | JSON with delay probability (0.0-1.0) |
| `/airports` | GET | none | JSON array of airports [{id, name}] sorted by name |
| `/health` | GET | none | JSON status for health checks |

## Technical Details

- Framework: Flask with Flask-CORS
- Port: 5000
- CORS: Enabled for all origins (frontend runs separately)
- Host: 0.0.0.0 (accessible from network)

## Files I'll Need

- Model file: server/model.pkl (trained Logistic Regression model)
- Data file: server/airports.csv (columns: DestAirportID, DestAirportName)
- Dependencies: flask, flask-cors, pandas, scikit-learn, joblib
- Output file: server/app.py

## Error Handling

Implement proper error handling:
- Return 400 for missing/invalid parameters
- Return 500 if model file not found
- Return JSON error messages with helpful descriptions

## Response Format

### /predict response:
```json
{
  "day_of_week": 1,
  "airport_id": 10397,
  "delay_probability": 0.23,
  "risk_level": "low"
}
```

### /airports response:
```json
[
  {"id": 10397, "name": "Atlanta, GA: Hartsfield-Jackson Atlanta International"},
  {"id": 10423, "name": "Austin, TX: Austin - Bergstrom International"}
]
```

---

> 💡 **Try it!** Type `#create-api` in Copilot Chat to generate your Flask server!
