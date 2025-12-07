# 🤖 Build Prediction Model

> 📋 **This is a Prompt File!** Use it by typing `#build-model` or `/build-model` in Copilot Chat.
> 
> - `#` attaches the prompt as context (you can add more to your message)
> - `/` runs the prompt directly as a command

---

## My Goal

Create a machine learning model that predicts flight delays.

## What I Know

- Dataset: `data/flights.csv`
- Target: Predict if a flight will be delayed more than 15 minutes
- Inputs: DayOfWeek (1-7) and DestAirportID (numeric airport identifier)

## Help Me With

1. Clean the data
   - Fill null values in DepDel15 column with 0
   - Remove outliers: flights where ArrDelay exceeds 90th percentile
   - Verify no nulls in ArrDel15 (target variable)

2. Prepare features
   - Features: DayOfWeek, DestAirportID
   - Target: ArrDel15 (binary: 1 = delayed >15 min, 0 = on time)
   - Split: 70% training, 30% testing

3. Train a model
   - Algorithm: Logistic Regression (sklearn.linear_model.LogisticRegression)
   - Use solver='lbfgs' and max_iter=1000
   - Evaluate with: accuracy, precision, recall, confusion matrix

4. Export the model
   - Save to: server/model.pkl
   - Format: pickle (using joblib or pickle module)
   - Also export airport list to: server/airports.csv

## Code Structure

Generate code that:
- Uses pandas for data manipulation
- Uses scikit-learn for ML
- Includes comments explaining each step
- Has proper error handling
- Prints model accuracy metrics

---

> 💡 **Try it!** Type `#build-model` in Copilot Chat to get step-by-step ML code!
