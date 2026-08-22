# Capacitated Vehicle Routing Problem (CVRP) Optimization

A Python-based optimization project comparing three constructive heuristic algorithms for solving the Capacitated Vehicle Routing Problem (CVRP).

This project was developed as part of my M.Sc. Engineering Management dissertation and focuses on evaluating different routing strategies for logistics and transportation optimization.

## Project Overview

The Capacitated Vehicle Routing Problem (CVRP) aims to determine efficient delivery routes for a fleet of vehicles while satisfying customer demand and vehicle capacity constraints.

In this project, three heuristic algorithms were implemented and compared:

- Sweep Heuristic
- Clarke & Wright Savings Heuristic
- Nearest Neighbour Heuristic

The algorithms were tested using the **A-n32-k5 benchmark instance** from CVRPLIB.

## Dataset

The A-n32-k5 benchmark instance contains:

- 1 depot
- 31 customers
- 5 vehicles
- Vehicle capacity: 100 units
- Best known solution: 784

Customer coordinates and demand values are used to construct the routing network and calculate the distance matrix.

## Methodology

The project follows the following workflow:

1. Load customer coordinates and demand data
2. Construct a Euclidean distance matrix
3. Generate feasible vehicle routes
4. Apply vehicle capacity constraints
5. Implement three heuristic algorithms
6. Improve generated routes using 2-opt local search
7. Calculate total travel distance
8. Compare results using optimality gap

The optimality gap is calculated relative to the best known solution of 784.

## Algorithms

### Sweep Heuristic

Customers are ordered according to their angular position relative to the depot and grouped into routes while respecting vehicle capacity.

A multi-start approach and 2-opt local search are used to improve the resulting routes.

### Clarke & Wright Savings Heuristic

The Clarke & Wright algorithm calculates the potential distance savings obtained by combining individual customer routes.

Routes are progressively merged while respecting vehicle capacity constraints, followed by 2-opt route improvement.

### Nearest Neighbour Heuristic

The Nearest Neighbour approach repeatedly selects the closest feasible unvisited customer.

A multi-start strategy is used together with 2-opt local search to improve solution quality.

## Results

| Method | Total Distance | Optimality Gap |
|---|---:|---:|
| Clarke & Wright | **829** | **5.74%** |
| Sweep | 946 | 20.66% |
| Nearest Neighbour | 1015 | 29.46% |
| Best Known Solution | 784 | 0% |

## Key Finding

**Clarke & Wright Savings Heuristic achieved the best solution among the three tested methods.**

It produced a total travel distance of **829**, only **5.74% above the best known solution of 784**.

The results demonstrate that relatively simple constructive heuristics can generate feasible and competitive solutions for medium-sized vehicle routing problems.

## Technologies Used

- Python
- Pandas
- Matplotlib
- Google Colab
- Operations Research
- Heuristic Optimization
- 2-opt Local Search

## Skills Demonstrated

- Supply Chain Optimization
- Vehicle Routing
- Operations Research
- Algorithm Implementation
- Logistics Analytics
- Data Analysis
- Performance Evaluation
- Python Programming

## Project Structure

```text
cvrp-heuristic-optimization/
│
├── cvrp_solver.py
├── CVRP_Analysis.ipynb
├── README.md
└── data/
    └── A-n32-k5.vrp
```

## How to Run

Install the required Python libraries:

```bash
pip install pandas matplotlib
```

Run the Python script:

```bash
python cvrp_solver.py
```

The program calculates routes for each heuristic and reports vehicle routes, route loads, total travel distance and optimality gap.

## Academic Context

This project was developed as part of my **M.Sc. Engineering Management dissertation (2026)**.

**Dissertation:**  
*Evaluating Constructive Heuristic Algorithms for the Capacitated Vehicle Routing Problem: A Benchmark and Survey-Based Study*

The full dissertation also includes primary research with logistics professionals to investigate practical challenges in route planning and transportation operations.

## Author

**Cansu Bora**

M.Sc. Engineering Management  
B.Sc. Industrial Engineering
