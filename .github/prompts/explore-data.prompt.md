# 🔍 Explore Flight Data

> 📋 **This is a Prompt File!** Use it by typing `#explore-data` or `/explore-data` in Copilot Chat.
> 
> - `#` attaches the prompt as context (you can add more to your message)
> - `/` runs the prompt directly as a command

---

## Your Task

Help me explore and understand the flight dataset.

## Context

I have a dataset at `data/flights.csv` with flight information from 2013.

## What I Need

1. Load the dataset and show me:
   - First 10 rows to understand the structure
   - Total number of rows and columns
   - All column names with their data types
   - Memory usage of the dataset

2. Check for data quality issues:
   - Count null values in each column
   - Check for duplicate rows
   - Validate DayOfWeek is 1-7 and ArrDel15 is 0 or 1
   - Identify outliers in ArrDelay column (beyond 90th percentile)

3. Find interesting patterns:
   - Overall delay rate (mean of ArrDel15)
   - Delay rate by day of week (which day has most delays?)
   - Top 10 airports with highest delay rates
   - Delay patterns by carrier

4. Suggest which columns might be useful for predicting:
   - DayOfWeek - categorical feature (1-7)
   - DestAirportID - categorical feature for destination
   - Target variable: ArrDel15 (binary: delayed >15 min or not)

## Output Format

Provide:
- Python code cells I can run in Jupyter notebook
- Brief explanations of each finding
- Data cleaning recommendations before training

---

> 💡 **Try it!** Type `#explore-data` in Copilot Chat and watch it generate analysis code!
