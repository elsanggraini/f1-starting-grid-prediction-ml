# 🏎️ F1 Australian GP 2026 – Starting Grid Prediction

This project predicts the starting grid order for the Formula 1 Australian Grand Prix 2026 using machine learning (Random Forest Regression) based on historical qualifying performance.

The prediction focuses on qualifying-based grid positions, not race results.

---

## 🎯 Prediction Target
- Event: Formula 1 Australian Grand Prix 2026
- Output: Starting Grid Position (P1–P22)
- Method: Regression → sorted into grid order

---

## 📊 Data Source
All data is retrieved dynamically using the FastF1 Python library, which provides access to official Formula 1 timing and session data.

No static datasets are stored in this repository.  
An active internet connection is required when running the notebook.

---

## 🗂️ Historical Data Used
- Session type: Qualifying (Q)
- Grand Prix: Australian GP
- Seasons: 2019, 2022, 2023, 2024

Extracted variables:
- Driver full name
- Team name
- Final qualifying position

---

## 🧮 Feature Engineering
From historical qualifying data, the following features are calculated:

- Average Driver Qualifying Position  
  Mean qualifying result of each driver at the Australian GP.

- Average Team Qualifying Position  
  Mean qualifying result of each team at the Australian GP.

- Grid Average (Fallback)  
  Overall average qualifying position across all drivers and seasons, used when no driver or team history exists.

---

## 👥 2026 Driver Lineup
The 2026 driver lineup is defined manually due to lineup changes compared to historical seasons.

Each driver is assigned:
- Driver code (e.g. VER, LEC, ANT)
- Team

Historical averages are merged when available.

---

## 🧠 Special Case Handling
- Returning drivers → driver + team average
- Rookie drivers (existing teams) → team average
- Rookie drivers + new teams → grid average

This ensures no missing values and consistent treatment for all drivers.

---

## 🤖 Machine Learning Model
- Algorithm: Random Forest Regressor
- Features:
  - Average Driver Qualifying Position
  - Average Team Qualifying Position
- Target: Qualifying position (numerical)

Model output is sorted to produce the predicted starting grid.

---

## 📈 Evaluation
Model performance on historical data is evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

Note: Metrics measure pattern learning, not future certainty.

---

## 📊 Output
- Predicted starting grid for Australian GP 2026
- Driver codes used instead of full names
- Grid order visualization

---

## ⚠️ Disclaimer
This project is a data-driven simulation, not an official prediction.  
Major technical regulation changes in 2026 may significantly affect real-world results.

---

## 🛠️ Tech Stack
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" width="50"/>
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/googlecolab/googlecolab-original.svg" width="50"/>
<img src="https://image2url.com/r2/default/images/1768403793348-ae168673-02cb-449a-b41e-44e0361eeca7.png" alt="gambar" loading="lazy" />
- pandas
- scikit-learn
- matplotlib
