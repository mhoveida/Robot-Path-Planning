This project focuses on **Robot Path Planning**, where you use different search algorithms to find the shortest or most efficient path through a maze. The maze is represented as a grid where "s" is the start, "g" is the goal, and "o" represents obstacles you can't pass through.

## Project Overview: Maze Solver

The code defines a `MazeState` class that tracks the robot's current position, the path cost, and its "parent" state (how it got there). The robot can move **Up, Down, Left, or Right**, provided there isn't an obstacle in the way.

### Search Algorithms Implemented

I implemented four classic Artificial Intelligence search strategies to compare how they perform:

* **Breadth-First Search (BFS)**: Explores all neighbors at the current depth before moving deeper. It's guaranteed to find the shortest path in an unweighted maze.
* **Depth-First Search (DFS)**: Goes as deep as possible down one path before backtracking. It uses less memory than BFS but doesn't always find the shortest path.
* **A* Search**: An "informed" search that uses a heuristic (Manhattan Distance) to estimate how far it is from the goal. This helps it find the path much faster by prioritizing promising directions.
* **Iterative Deepening A* (IDA*): Combines the low memory usage of DFS with the guided search of A* by gradually increasing the allowed "cost limit".

---

## Key Metrics

For every algorithm, the script tracks and prints:

* **Cost**: The length of the path found.
* **Nodes Expanded**: How many states the robot actually "visited".
* **Max Search Depth**: The furthest the robot went into the maze.
* **Running Time & RAM Usage**: How much processing power and memory the search required.

---

## How to Use

You can run the script from the terminal by specifying the algorithm and the map file:

```bash
python maze.py -astar -m map.txt

```

The solver will print the maze to the console and mark the final path with `*` characters.

### Requirements

* **Python 3**
* Standard libraries: `collections`, `heapq`, `argparse`, `time`, and `resource`.