# Linear Programming Optimization: Dietary Plan Problem

This repository contains the implementation and analysis of a linear programming problem focused on finding an optimal daily dietary plan. The objective is to minimize the total cost of a meal plan consisting of four specific foods while satisfying mandatory nutritional requirements.

## Problem Description

The project aims to determine the exact quantities (in grams) for a diet including:
- Bun (Chiflă)
- Fish (Pește)
- Yogurt (Iaurt)
- Apple (Măr)

### Constraints and Objectives
- **Objective Function**: Minimize the total cost based on price per 100g for each food item.
- **Nutritional Requirements**: The plan must provide at least 2000 kcal, 70g of protein, and 40g of carbohydrates daily.
- **Quantity Limits**: Specific upper bounds are set for buns (250g), apples (300g), and yogurt (300g).
- **Variable Type**: All food quantities are treated as integers (Integer Linear Programming).

## Technical Implementation

The project explores several optimization techniques to compare performance and accuracy:

### 1. Exact Solvers (PuLP)
The problem is modeled using the `PuLP` library in Python. This method provides the global optimum by interfacing with standard solvers like CBC.

### 2. Branch and Bound
A custom implementation of the Branch and Bound algorithm is included. This technique is specifically suited for Integer Linear Programming (ILP) as it explores the solution space by branching on fractional variables and pruning sub-optimal nodes.

### 3. Hill Climbing
A local search algorithm that starts from a random feasible solution and iteratively moves to neighboring solutions with lower costs. While efficient, it is prone to getting stuck in local optima.

### 4. Simulated Annealing
A metaheuristic algorithm designed to overcome the limitations of Hill Climbing. It uses a "temperature" parameter to occasionally accept worse solutions in the early stages, allowing it to escape local optima and converge toward the global optimum.

## Results Comparison

| Optimization Method | Best Cost Found | Solution Status |
|---------------------|-----------------|-----------------|
| PuLP (Solver)       | 53.74 RON       | Global Optimum  |
| Branch and Bound    | 53.74 RON       | Global Optimum  |
| Simulated Annealing | 53.739 RON      | Near Optimum    |
| Hill Climbing       | 56.62 RON       | Local Optimum   |

## Project Structure
- Modeling of the objective function and 10 distinct constraints.
- Search space analysis (estimated at $O(10^{10})$ to $O(10^{14})$ solutions).
- Sensitivity analysis by changing input instances and observing solver behavior.
- Comparative analysis between exact and stochastic methods.

## Documentation
For a detailed explanation of the mathematical modeling, variable characterization, and in-depth analysis of the results, please refer to the full documentation in Romanian:

[Read Documentation (Romanian)](TO_LP_Cosereanu_Emanuel_problema1.pdf)

## Author
Coșereanu Emanuel
INFO, Year 3, Group 40322
Oil & Gas University of Ploiești
