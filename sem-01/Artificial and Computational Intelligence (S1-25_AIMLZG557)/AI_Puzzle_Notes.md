# 📘 Notes – Classic AI Puzzle Problems with Heuristics

---

## 1. 8-Puzzle Problem  
- **Goal**: Arrange tiles from scrambled state to the goal configuration by moving the blank space.  
- **Heuristics**:  
  - Misplaced Tiles → count of tiles not in correct position.  
  - Manhattan Distance → sum of horizontal and vertical distances from goal positions.  
- **Approach**: Generate successor states by moving the blank (Up, Down, Left, Right). Always expand the state with the lowest heuristic value.  
- **Example**:  
  - Start state has h=3 (3 misplaced tiles).  
  - Successors have h=4, h=4, h=2 → choose h=2.  
  - Expanding h=2 yields h=1, h=3, h=3, h=3 → choose h=1.  
  - Expanding h=1 reaches the goal.  
- **Advantages**: Simple heuristics, admissible and effective.  
- **Disadvantages**: Misplaced tiles heuristic is less accurate than Manhattan distance, leading to more expansions.  
- **Use Case**: Foundational problem in heuristic search design.  

---

## 2. 8-Queens Problem  
- **Goal**: Place 8 queens on a chessboard such that no two queens attack each other.  
- **Heuristic**: Number of pairs of queens attacking each other.  
- **Approach**:  
  - Place queens randomly and use Hill Climbing to reduce conflicts.  
  - If stuck, apply Random Restart or Simulated Annealing.  
- **Example**: If 5 pairs of queens attack each other, h=5. Moving one queen may reduce h to 3.  
- **Advantages**: Easy to model, good demonstration of local search.  
- **Disadvantages**: Hill Climbing often gets stuck in local maxima or plateaus.  
- **Use Case**: Illustrates optimization under constraints (e.g., timetabling, scheduling).  

---

## 3. Travelling Salesman Problem (TSP)  
- **Goal**: Find the shortest possible tour visiting all cities once and returning to the start.  
- **Heuristics**:  
  - Nearest-neighbor (choose the closest city next).  
  - Minimum Spanning Tree estimates for remaining cities.  
- **Approach**:  
  - A* with MST-based heuristics for smaller TSP instances.  
  - Metaheuristics (Genetic Algorithms, Simulated Annealing) for larger cases.  
- **Example**: For 5 cities, nearest-neighbor builds a tour by always choosing the closest city at each step.  
- **Advantages**: Heuristics drastically reduce computation compared to brute-force (n!).  
- **Disadvantages**: NP-hard → optimal solution infeasible for large n. Heuristics may be suboptimal.  
- **Use Case**: Logistics, delivery optimization, airline route planning.  

---

## 4. Missionaries and Cannibals Problem  
- **Goal**: Safely move 3 missionaries and 3 cannibals across a river using a boat that carries two people. Cannibals must never outnumber missionaries on either side.  
- **Heuristic**: Number of people left on the starting side (or estimated trips remaining).  
- **Approach**: Use state-space search with constraints enforced. Apply BFS or A* with simple heuristic.  
- **Example**: Start: (3M, 3C, left). Goal: (0M, 0C, left). Moves generate states like (2M, 2C, left).  
- **Advantages**: Demonstrates constraint satisfaction in search problems.  
- **Disadvantages**: State space grows quickly if more people are added.  
- **Use Case**: Safety-critical planning under constraints.  

---

## 5. N-Queens Generalization (e.g., 100-Queens)  
- **Goal**: Place N queens on an N×N board without attacks.  
- **Heuristic**: Number of conflicts (attacking pairs).  
- **Approach**: Large-scale problems solved with Genetic Algorithms or Simulated Annealing rather than classical search.  
- **Example**: In a 100-Queens problem, GA evolves board configurations until conflicts are eliminated.  
- **Advantages**: Scales better with metaheuristics.  
- **Disadvantages**: Hard to guarantee optimality; may take many iterations.  
- **Use Case**: Large constraint optimization problems in scheduling, resource allocation.  

---

# ✅ Takeaways  
- **8-Puzzle** → Shows heuristic efficiency (misplaced tiles, Manhattan distance).  
- **8-Queens** → Local search with conflict-count heuristic; highlights Hill Climbing issues.  
- **TSP** → NP-hard optimization; solved with nearest-neighbor, GA, SA.  
- **Missionaries & Cannibals** → Classic constraint satisfaction puzzle.  
- **N-Queens** → Generalization solved with advanced local search/metaheuristics.  

---
