# Informed Search Algorithm — 8-Tile Puzzle

Python implementations of two informed search techniques applied to the classic 8-Tile (8-Puzzle) problem, comparing solution quality and search efficiency.

## Contents

| File | Description |
|---|---|
| `gbfs.py` | Greedy Best First Search using the **Misplaced Tiles** heuristic |
| `astar.py` | A* Search using the **Manhattan Distance** heuristic |
| `comparison.py` | Runs both algorithms on the same instance and prints a side-by-side comparison table |
| `requirements.txt` | Dependency list (none — standard library only) |

## Problem Setup

- **State representation:** a 3×3 grid flattened into a tuple of 9 elements, read row-wise, with `0` representing the blank tile.
- **Initial State:** `(0, 1, 5, 4, 8, 2, 7, 6, 3)`
- **Goal State:** `(1, 2, 3, 4, 5, 6, 7, 8, 0)`
- **Move cost:** every slide (UP, DOWN, LEFT, RIGHT) has a uniform cost of 1.

## Running

```bash
python3 gbfs.py
python3 astar.py
python3 comparison.py
```

Each solver script prints the initial and goal states, the full solution path step by step, the number of nodes expanded, and the final path cost. `comparison.py` runs both solvers and prints a summary table.

## Results

| Metric | Greedy Best First Search | A* Search |
|---|---|---|
| Heuristic | Misplaced Tiles | Manhattan Distance |
| Evaluation function | f(n) = h(n) | f(n) = g(n) + h(n) |
| Path cost (moves) | 10 | 10 |
| Nodes expanded | 47 | 11 |
| Optimality guaranteed | No | Yes (admissible heuristic) |
| Completeness guaranteed | No | Yes |

Both algorithms found the same 10-move solution for this instance, but A* reached it after expanding far fewer nodes, illustrating the benefit of combining an admissible, well-informed heuristic (Manhattan Distance) with the actual path cost g(n).

## Requirements

- Python 3.x (standard library only — no external dependencies)

## Author

Alonso Biju - 2562064