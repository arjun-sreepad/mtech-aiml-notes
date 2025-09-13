# Intelligent Agents & Task Environments – Master Notes with Extra Examples

---

## 1. Rational Agent – Core Idea

- **Agent**: Any entity that perceives the environment via **sensors** and acts upon it using **actuators**.  
- **Rational Agent**: Chooses actions that maximize its performance measure, i.e., **best outcome or best expected outcome under uncertainty**.  
- **Formal Function**:  
  \( f : P^* \rightarrow A \)  
  - \( P^* \): percept history.  
  - \( A \): action chosen.  
- **Design Principle**: Design the best-performing agent within resource limits.  
- **Limitation**: Perfect rationality is unachievable → we design for **bounded rationality**.  

---

## 2. Properties of Rational Agents

1. **Omniscience vs Actual Performance** → Agents cannot know everything.  
2. **Learning Capability** → Improve through experience.  
3. **Autonomy** → Independent decision-making.  
4. **Performance Measure** → Objective criteria, e.g., vacuum cleaner → dirt cleaned, time, energy, noise.  

---

## 3. PEAS Framework (Task Specification)

- **P** → Performance measure  
- **E** → Environment  
- **A** → Actuators  
- **S** → Sensors  

**Examples**:  
- **Path-Finding Robot** → Maze solving (P: shortest path, E: maze, A: wheels, S: camera).  
- **Medical Diagnosis AI** → Hospital system (P: accuracy of diagnosis, E: patients, A: display/treatment suggestions, S: test reports, sensors).  
- **Self-Driving Car** → (P: safe, quick travel, E: roads, traffic, A: steering/brakes, S: lidar, GPS, cameras).  

---

## 4. Dimensions of Task Environment

### (a) Sensor Based – Observability  
- **Fully Observable** → Chess, Sudoku, ATM machine.  
- **Partially Observable** → Poker, medical diagnosis, driving in fog.  

### (b) Action Based – Dependency  
- **Episodic** → Image classification, spam filtering, credit card fraud detection.  
- **Sequential** → Chess, stock trading, self-driving cars.  

### (c) State Based – Number of States  
- **Discrete** → Tic-tac-toe, online shopping cart choices.  
- **Continuous** → Robot arm movement, airplane altitude, temperature control.  

### (d) Agent Based – Cardinality  
- **Single-Agent** → Crossword solver, personal assistant bot (single user).  
- **Multi-Agent** → Multiplayer online games, traffic systems, e-commerce bidding bots.  

### (e) Action & State Based – Outcome & Change  
- **Deterministic** → Maze solving (always predictable).  
- **Stochastic** → Weather prediction, disease spread modeling.  
- **Strategic** → Business negotiations, military strategy games.  
- **Static** → Crossword puzzles, offline image recognition.  
- **Dynamic** → Stock market, air traffic control, autonomous drones.  
- **Semi-Dynamic** → Chess with timer, online exams with countdown.  

---

## 5. Glossary of Key Terms

(Expanded with extra examples)  

- **Deterministic** → Fixed outcome (e.g., solving arithmetic).  
- **Stochastic** → Randomness (e.g., rolling dice).  
- **Strategic** → Competitive (e.g., football, auctions).  
- **Static** → Stable (e.g., jigsaw puzzle).  
- **Dynamic** → Changing (e.g., real-time video streaming quality).  
- **Semi-Dynamic** → Static env. + changing score (e.g., timed test).  
- **Discrete** → Countable states (e.g., turn-based games).  
- **Continuous** → Smooth states (e.g., robot arm motion).  
- **Episodic** → Independent cases (e.g., X-ray analysis).  
- **Sequential** → Dependent (e.g., driving).  
- **Fully Observable** → Chess.  
- **Partially Observable** → Driving in traffic.  
- **Single-Agent** → Sudoku solver.  
- **Multi-Agent** → Online poker.  
- **Known vs Unknown** → Chess vs Martian exploration.  
- **Benign vs Adversarial** → Weather vs Cybersecurity.  
- **Autonomy** → Agent decides based on its own experience.  
- **Omniscience** → Hypothetical perfect knowledge (not possible in real world).  

---

## 6. Types of Agents (with more examples)

### 1. Simple Reflex Agents  
- **Examples**: Thermostat, vending machines, traffic lights.  
- ✅ Simple, fast.  
- ❌ Cannot handle uncertainty.  

### 2. Model-Based Reflex Agents  
- **Examples**: Roomba vacuum, anti-lock braking system (ABS), elevator system.  
- ✅ Handles partial observability.  
- ❌ Needs accurate models.  

### 3. Goal-Based Agents  
- **Examples**: GPS navigation, delivery drones, Mars rovers.  
- ✅ Flexible.  
- ❌ Needs planning power.  

### 4. Utility-Based Agents  
- **Examples**: Self-driving car, airline booking systems (choose cheapest + safest + fastest), ride-hailing (Uber AI).  
- ✅ Optimizes trade-offs.  
- ❌ Utility design is hard.  

### 5. Learning Agents  
- **Examples**: AlphaZero chess AI, Google Translate, recommender systems (Netflix, Amazon), stock trading bots.  
- ✅ Adaptive.  
- ❌ Needs training data.  

---

## 7. Examples of Task Environments

| Task Environment                 | Observability         | Agent Type     | Determinism  | Episodic/Sequential | Static/Dynamic | Discrete/Continuous |
|----------------------------------|-----------------------|----------------|--------------|----------------------|----------------|---------------------|
| **Medical Diagnosis System**     | Partially Observable  | Single Agent   | Stochastic   | Sequential           | Dynamic        | Continuous          |
| **Satellite Image Analysis**     | Fully Observable      | Single Agent   | Deterministic| Episodic             | Static         | Continuous          |
| **Interactive English Tutor**    | Partially Observable  | Multi-Agent    | Stochastic   | Sequential           | Dynamic        | Discrete            |
| **Autonomous Drone Delivery**    | Partially Observable  | Single Agent   | Stochastic   | Sequential           | Dynamic        | Continuous          |
| **Stock Market Trading Bot**     | Partially Observable  | Multi-Agent    | Stochastic   | Sequential           | Dynamic        | Continuous          |
| **Chess Game Agent**             | Fully Observable      | Multi-Agent    | Strategic    | Sequential           | Semi-Dynamic   | Discrete            |

---

## 8. Mapping Agents to Environments

- **Simple Reflex** → Deterministic, observable (traffic lights, vending machines).  
- **Model-Based Reflex** → Partial info (Roomba vacuum, ABS braking).  
- **Goal-Based** → Sequential, planning (GPS navigation, Mars rover).  
- **Utility-Based** → Trade-offs, multi-objective (self-driving cars, airline booking).  
- **Learning** → Adaptive, evolving (Netflix recommender, AlphaZero).  

---

# ✅ Quick Revision Checklist

- **Agent = Sensors + Actuators + Program + Environment**  
- **Rational Agent** → acts for best expected outcome.  
- **PEAS** → specifies task environment.  
- **Task Environment Dimensions** → Observability, Episodic/Sequential, Discrete/Continuous, Single/Multi, Deterministic/Stochastic/Strategic, Static/Dynamic/Semi-Dynamic.  
- **Types of Agents** → Reflex → Model-Based → Goal-Based → Utility-Based → Learning.  
- **Extra Concepts** → Omniscience, Autonomy, Semi-Dynamic.  
- **Examples**:  
  - Diagnosis = Partial, Stochastic, Sequential.  
  - Satellite = Full, Deterministic, Episodic.  
  - Tutor = Partial, Multi-Agent, Sequential.  
  - Stock Trading = Partial, Stochastic, Dynamic.  
  - Chess = Full, Strategic, Semi-Dynamic.  
