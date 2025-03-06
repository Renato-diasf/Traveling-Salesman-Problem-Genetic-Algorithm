# Traveling Salesman Problem - Genetic Algorithm

This repository contains a Python implementation of a **Genetic Algorithm** to solve the **Traveling Salesman Problem (TSP)**. The goal is to find the shortest possible route that visits a set of cities exactly once and returns to the starting city.

---

## Problem Description

The **Traveling Salesman Problem (TSP)** is a classic optimization problem where:
- A salesman must visit `n` cities.
- The journey starts and ends at the same city.
- The objective is to minimize the total distance traveled.

This project uses a **Genetic Algorithm** to approximate the optimal solution.

---

## Features

- **Random Distance Matrix Generation**: Distances between cities are randomly generated.
- **Population Initialization**: A small population of possible routes is created.
- **Fitness Function**: Calculates the total distance of a route.
- **Tournament Selection**: Selects parents for crossover based on fitness.
- **Order Crossover (OX)**: Ensures valid routes by preserving order and avoiding duplicates.
- **Mutation**: Swaps two cities in a route to introduce diversity.
- **Elitism**: Preserves the best routes across generations.
- **Permutation Enumeration**: Enumerates all possible routes to find the global minimum distance (for small `n`).

---

## How It Works

1. **Initialization**:
   - A distance matrix is randomly generated.
   - An initial population of routes is created.

2. **Genetic Algorithm**:
   - The algorithm runs for a fixed number of generations.
   - In each generation:
     - The fitness of each route is calculated.
     - The best routes are preserved (elitism).
     - New routes are created using crossover and mutation.

3. **Comparison**:
   - All possible routes are enumerated for small `n` to verify the global minimum distance.

---

## Code Structure

- **Distance Matrix**: Randomly generated distances between cities.
- **Population Initialization**: Routes start and end at the same city.
- **Fitness Function**: Sums the distances of a route.
- **Selection**: Tournament selection to choose parents.
- **Crossover**: Order Crossover (OX) to create valid child routes.
- **Mutation**: Swaps two cities in a route.
- **Elitism**: Preserves the best routes.
- **Permutations**: Enumerates all possible routes for comparison.

---

## Example Output

```plaintext
Distance Matrix:
[[ 0 23 45 67 89 12]
 [23  0 34 56 78 90]
 [45 34  0 12 34 56]
 [67 56 12  0 78 90]
 [89 78 34 78  0 12]
 [12 90 56 90 12  0]]

Initial Population:
[0 2 1 4 5 3 0]
[0 3 1 2 4 5 0]
...

Best Route in Generation 1: [0 2 1 4 5 3 0] with cost 234
Global Minimum Distance: 200
