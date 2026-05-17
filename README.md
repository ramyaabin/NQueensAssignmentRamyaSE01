# NQueensAssignmentRamyaSE01
Solving the N-Queens Problem Using DFS, Greedy Hill Climbing, Simulated Annealing, and Genetic Algorithms
This repository includes all the code, experiments, and the Overleaf report for my MSc Software Engineering project carried out under the supervision of Raja Hashim Ali at the University of Europe for Applied Sciences.
In this project, I explored four different algorithms to solve the classic N-Queens problem. The goal was to test how each method performs as the board size increases N=10, N=30, N=50, N=100, N=200, and N=500. I compared the algorithms based on how fast they run, how well they scale, and whether they can find valid solutions. The four approaches I implemented and evaluated are:

Depth-First Search (DFS)
Greedy Hill Climbing
Simulated Annealing (SA)
Genetic Algorithm (GA)
Project Goals (Simple Explanation)

The main aim of my project was to understand how different types of algorithms behave when solving the N-Queens problem. Specifically, I wanted to:

Compare deterministic, heuristic, and evolutionary algorithms
See how solution quality and runtime change when N increases
Use useful optimizations like:
O(1) attack-count arrays (for faster conflict checking)
Incremental conflict updates in Simulated Annealing
Population-based search in Genetic Algorithms
Create clear comparisons using graphs, tables, and heatmaps
Present everything in a detailed Overleaf LaTeX report

Algorithm Summaries (Easy to Understand)
1️. Depth-First Search (DFS)

DFS tries to place queens row by row and backtracks when it hits a conflict.

Always finds correct solutions
Very fast only for small boards
Becomes extremely slow as N grows (O(N!))
Works only up to N ≤ 12

Great for small N, but unusable for larger boards.

2️. Greedy Hill Climbing

Starts with a random board and tries to reduce conflicts step by step.

Uses fast O(1) conflict counts
Good for small and medium N
Often gets stuck in local minima
Failed to solve N = 50, 200, 500

Fast but unreliable for big boards.

3️. Simulated Annealing (SA) — This is best performing algorithm

A probabilistic method that sometimes accepts worse moves to escape traps.

Key improvements in my implementation:

O(N) conflict delta update (huge speed-up)
Cooling schedule: T₀ = 100 → multiplied by 0.995 each step
60,000 iterations per run

Performance:

Solved all cases up to N = 100
Small conflicts: 4 at N = 200, 19 at N = 500
Fastest algorithm overall (15.43s at N = 500)

Best mix of speed and accuracy. Performs well at large N.

4️. Genetic Algorithm (GA)

Uses a population of boards that evolve over generations.

Top 50% selected each generation
Single-point crossover
Mutation probability = 0.1
200 population, 2000 generations

Issues were :-

Lost diversity too quickly so premature convergence
Mutation disturbed good solutions
Failed for all N
Slowest method (274s at N = 500)

Needs better design (selection, crossover, mutation tuning).

Results were :-
a) Simulated Annealing: solved 4 out of 6
b) Greedy Hill Climbing: solved 3 out of 6
c) DFS: solved only small boards (N ≤ 12)
d) Genetic Algorithm: solved 0 out of 6

Runtime Comparisons were:-
SA = Fastest for all N
Greedy = Fast at small N but slow after N > 100
GA = Slowest
DFS = Only practical for small N
