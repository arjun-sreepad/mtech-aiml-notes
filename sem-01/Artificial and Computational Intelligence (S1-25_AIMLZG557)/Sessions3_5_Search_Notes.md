# 📘 Sessions 3–5 Notes: Problem Solving Agents & Search Strategies

---

## 1. Problem Solving Agent (PSA)

**Definition**:  
A Problem Solving Agent is a **goal-based agent** that decides on a **sequence of actions** to reach a goal state.

### Phases of PSA
1. **Goal Formulation** → What to achieve.  
   - *Eg*: Travel from Arad to Bucharest.
2. **Problem Formulation** → Define state space and operators.  
   - Components: Initial state, Actions, Transition model, Goal test, Path cost.
3. **Search Phase** → Explore state space using a search strategy.
4. **Execution Phase** → Carry out the chosen sequence.

**Assumptions**: Environment is **static, fully observable, discrete, deterministic**.

---

## 2. Problem Formulation – 5 Components

1. **Initial State** – starting position.  
   - Eg: In(Arad)
2. **Actions/Operators** – possible actions at each state.  
   - Eg: From Arad → Sibiu, Timisoara, Zerind
3. **Transition Model (Successor Function)** – outcome of an action.  
   - Eg: Result(In(Arad), Go(Sibiu)) = In(Sibiu)
4. **Goal Test** – check if state = goal.  
   - Eg: In(Bucharest)?
5. **Path Cost Function** – numeric cost of path.  
   - Eg: Distance traveled

**Solution** = sequence of actions with **minimum path cost**.

---

## 3. Graph Search vs Tree Search

- **Tree Search**: May revisit same states, risk of infinite loops.
- **Graph Search**: Keeps an **explored set**, avoids revisiting.

**Terminology**:  
- Node, State, Parent, Action, Depth, Path cost g(n), Branching factor b.

---

## 4. Uninformed Search Strategies

| **Strategy** | **Description** | **Completeness** | **Optimality** | **Time Complexity** | **Space Complexity** | **Advantages** | **Disadvantages** | **Examples** |
|--------------|-----------------|------------------|----------------|----------------------|-----------------------|----------------|-------------------|--------------|
| **Breadth-First Search (BFS)** | Explores shallowest nodes first (FIFO queue). | ✅ | ✅ (if costs equal) | O(b^d) | O(b^d) | Finds shortest path | Memory intensive | Metro map shortest path |
| **Depth-First Search (DFS)** | Explores deepest node first (LIFO stack). | ❌ | ❌ | O(b^m) | O(bm) | Memory efficient | May loop, not optimal | Maze exploration |
| **Uniform Cost Search (UCS)** | Expands lowest cost node g(n). | ✅ | ✅ | O(b^{1+C*/ε}) | Same | Always finds optimal cost | Slow | GPS least-cost routes |
| **Depth-Limited Search (DLS)** | DFS with depth cutoff l. | ❌ | ❌ | O(b^l) | O(bl) | Avoids infinite loops | May miss solution | Chess with depth cutoff |
| **Iterative Deepening Search (IDS)** | DFS with increasing depth limit. | ✅ | ✅ (if unit costs) | O(b^d) | O(bd) | BFS completeness + DFS space | Re-expands nodes | 8-puzzle solver |
| **Bi-Directional Search** | Runs two searches: from start and goal. | ✅ | ✅ | O(b^(d/2)) | O(b^(d/2)) | Faster than BFS | Needs reversible ops | Word ladder puzzles |

**Key formulas**:  
- BFS: Time O(b^d), Space O(b^d)  
- DFS: Time O(b^m), Space O(bm)  
- UCS: Time O(b^{1+C*/ε})  
- IDS: Time O(b^d), Space O(bd)  
- Bi-Directional: Time O(b^(d/2)), Space O(b^(d/2))

---

## 5. Informed (Heuristic) Search Strategies

### (a) Greedy Best-First Search
- **f(n) = h(n)** (choose node with lowest heuristic)
- ✅ Fast, ❌ Not optimal, ❌ Not complete
- Eg: Nearest neighbor in TSP, robot moving toward beacon.

### (b) A* Search
- **f(n) = g(n) + h(n)**
- ✅ Complete (admissible h), ✅ Optimal (consistent h)
- Eg: GPS navigation combining distance traveled + estimated distance.

### (c) Iterative Deepening A* (IDA*)
- Depth-first search with cost cutoff, increases gradually.
- Space: O(bd)
- Eg: 15-puzzle solver.

### (d) Recursive Best-First Search (RBFS)
- Uses recursion with limited memory. Tracks best alternative f-costs.
- Space: O(bd)
- Eg: Routing in large networks, wireless sensor case study.

---

## 6. Comparison – Informed Searches

| **Strategy** | **Evaluation Function** | **Completeness** | **Optimality** | **Time Complexity** | **Space Complexity** | **Example** |
|--------------|--------------------------|------------------|----------------|----------------------|-----------------------|-------------|
| **Greedy Best-First** | f(n) = h(n) | ❌ | ❌ | O(b^m) | Exponential | Robot beacon, TSP heuristic |
| **A*** | f(n) = g(n) + h(n) | ✅ (admissible h) | ✅ (consistent h) | O(b^d) worst | Exponential | GPS, Pac-Man AI |
| **IDA*** | DFS + cost cutoff | ✅ | ✅ (if h admissible) | O(b^d) | O(bd) | 15-puzzle |
| **RBFS** | Recursive f-cost | ✅ | ✅ (if h admissible) | O(b^d) | O(bd) | Network routing |

---

## 7. Case Studies & Applications

- **BFS**: Shortest metro route
- **DFS**: Web crawler, maze exploration
- **UCS**: Road navigation (least distance/time)
- **IDS**: Solving 8-puzzle or 15-puzzle
- **Bi-Directional**: Word ladder, social network shortest path
- **Greedy**: Robot navigation to beacon
- **A***: Game AI, GPS navigation
- **IDA***: Large puzzles with limited memory
- **RBFS**: Memory-efficient routing in sensor networks

---

## 8. Visual Intuition (Summary)

- **BFS** → Expands nodes level by level.  
- **DFS** → Goes deep, backtracks.  
- **UCS** → Chooses least cost so far.  
- **IDS** → DFS repeated with increasing limits.  
- **Bi-Directional** → Meet in the middle.  
- **Greedy** → Chooses node with lowest h(n).  
- **A*** → Balances cost so far + heuristic.  
- **IDA*** → A* with iterative cost cutoff.  
- **RBFS** → A* with memory limitation.  

---

# ✅ Quick Revision Checklist

- PSA phases: Goal → Problem → Search → Execution
- Problem = (Initial state, Actions, Transition, Goal test, Path cost)
- Tree Search vs Graph Search
- Uninformed: BFS, DFS, UCS, DLS, IDS, Bi-Directional
- Informed: Greedy, A*, IDA*, RBFS
- Key formulas for time/space complexity
- Examples: BFS → Metro, UCS → GPS, A* → Games, IDS → 8-puzzle, RBFS → Routing

