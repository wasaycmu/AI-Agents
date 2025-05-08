# Connect 4 AI Agents

This project implements and evaluates various AI agents to play the classic game of **Connect 4**. It was developed as part of an AI course assignment and explores multiple approaches, including random play, Minimax search with alpha-beta pruning, and Pure Monte Carlo Search.

---

## 🎮 Game Description

Connect 4 is a two-player board game where players alternate dropping discs into a vertical 6×7 grid. The first to align four of their discs vertically, horizontally, or diagonally wins.

Agents are implemented to:
- Simulate gameplay with random moves
- Make optimal decisions using Minimax and Alpha-Beta pruning
- Use heuristic evaluation functions to improve decision-making efficiency
- Run Monte Carlo simulations to select probabilistically favorable moves

---

## 🧠 AI Techniques Implemented

### 1. **Search Problem Definition**
- **Initial State**: Empty 6×7 board
- **Actions**: Drop a disc into any non-full column
- **Transition Model**: Board updates to reflect the move, turn switches
- **Goal State**: A player connects four discs, or the board is full (draw)
- **Utility Function**: +1 for Player 1 win, -1 for loss, 0 for draw

### 2. **Random Agent**
- Selects a move randomly from available columns

### 3. **Minimax Algorithm with Alpha-Beta Pruning**
- Depth-limited to reduce computation
- Uses heuristics to evaluate non-terminal board states
- Orders moves to prioritize center columns and immediate wins

### 4. **Heuristic Evaluation**
- Considers:
  - Potential winning lines
  - Opponent blocking
  - Center control
- Outperforms pure minimax in time and effectiveness

### 5. **Monte Carlo Simulation**
- Simulates random playouts to estimate move quality
- Used to determine "best first move"
- Assumes opponent plays randomly

---

## 📦 Technologies Used

### Programming Language:
- Python 3.10+

### Python Libraries:
- `numpy` — board representation
- `math` — infinity, numerical ops
- `random` — for random moves and simulations
- `time` — performance measurement

---

## 🧪 Experiments & Observations

- **Random vs Random**: Over 1000 games, Player 1 had ~54.6% win rate due to first-move advantage
- **Minimax**: Performs well but is computationally expensive without pruning
- **Heuristics**: Greatly reduce computation time and improve move quality
- **Monte Carlo**: Effective in identifying strong moves but limited by simulation count and randomness

---

## 🏁 Performance Insights

| Board Size | Minimax Time (s) | Heuristic Minimax Time (s) |
|------------|------------------|-----------------------------|
| 4 columns  | 0.0102           | 0.0011                      |
| 6 columns  | 0.0574           | 0.0046                      |
| 7 columns  | 0.1217           | 0.0098                      |

- Move ordering and heuristics drastically reduce decision time
- Time increases exponentially with board size

---

## 🔍 Bonus: Best First Move (Monte Carlo)

Using Monte Carlo simulations with 100 iterations, the agent identified central columns (3 or 4) as optimal starting points—assuming random opponent behavior.

---

## 🎯 How to Use

1. Clone the repo
2. Run the simulation script:  
   ```bash
   python connect4_simulation.py
