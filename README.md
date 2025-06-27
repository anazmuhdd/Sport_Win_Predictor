# 🎾 Real-Time Tennis Score Tracker & Winner Probability Predictor

A Python-based system that continuously monitors a live-updated CSV file to track tennis match progress and predict player win probabilities based on score, momentum, and game logic. Built using `watchdog`, `pandas`, and `numpy`, it simulates a smart scoreboard with real-time updates.

---

## 📌 Project Objective

To simulate a real-time tennis game tracker that:

* Watches for score updates from a CSV file.
* Tracks server and receiver scores dynamically.
* Computes momentum based on recent points.
* Uses a logistic function to predict win probabilities in real time.
* Displays formatted game information after each point.

---

## 📊 Features

* ⏰ Real-time monitoring of CSV updates using `watchdog`
* 🏋️ Score standardization logic to handle server/receiver changes
* 📊 Momentum tracking from last 5 points
* 🔬 Logistic model to predict win probabilities
* 📝 Intelligent game-end detection based on scoring rules

---

## 🚀 How It Works

1. Monitors the current directory for changes to a specified CSV file (e.g., `game 1.csv`).
2. On detecting new rows, it:

   * Extracts player names, scores, and scorer.
   * Updates internal score state.
   * Tracks recent 5 points to calculate momentum.
   * Computes win probabilities using a logistic formula with momentum boost.
   * Prints a detailed breakdown after each new point.

---

## 🎯 Logistic Win Probability Model

Uses this function:

```python
p1_win_prob = 1 / (1 + np.exp(-(α * score_diff + β * momentum)))
```

Where:

* `α = 0.05`, `β = 0.02`
* `score_diff` = player1\_score - player2\_score
* `momentum` = sum of recent 5 point outcomes

---

## ⚙️ Installation & Setup

1. Clone this repo:

```bash
git clone https://github.com/yourusername/tennis-score-predictor.git
cd tennis-score-predictor
```

2. Install dependencies:

```bash
pip install pandas numpy watchdog
```

3. Run the tracker:

```bash
python main.py
```

Make sure `game 1.csv` is in the same directory and formatted correctly.

---

## 📝 CSV File Format

The system expects the CSV file to contain the following columns:

```csv
SCORE_SHEET_ID,SET_NO,SERVER,RECIEVER,SCOREDBY,SCORE,TIME,OPPONENT SCORE
```

Each new row simulates a point being scored.

---

## 📁 Project Structure

```
📆 tennis-score-predictor
🔺 main.py                # Core script for real-time tracking
🔺 game 1.csv             # CSV file with ongoing game data
🔺 README.md              # This documentation
```

---

## 🛡️ Example Output

```
Time: 00:05:43 | Server: Player A | Receiver: Player B
Score: Player A 28 - Player B 26
Player A scored the point
Momentum: 3 (last 5 points)
Player A win probability: 72.42% | Player B win probability: 27.58%
```

---

## 🤝 Contributions

Feel free to contribute!

* Open an issue for any bugs or suggestions
* Fork the repo and submit a pull request for improvements

---

## 👥 Author

**Developer**: Mohammed Anas A R
**Email**: [anasmonar@gmail.com](mailto:your_email@example.com)
**LinkedIn**: [linkedin.com/in/anazmuhdd](https://linkedin.com/in/yourprofile)
**College**: Mar Baselios College of Engineering and Technology

---

## 📄 License

MIT License
