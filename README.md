This is a repo condensing my contributions to https://github.com/Nicholas-Schenk/AI_HW-1 into an easier-to-digest format. 

# Exploring A* Search Algorithm
A* is a search algorithm used for path-finding.

A* search alogirthm has been implemented in 3 flavors: 
- Repeated Forward A*
- Repeated Backward A*
- Adaptive A*

Our search algorithms operate in an 2D grid world, where the Agent is placed in 1 cell and the Target destination is placed in another.
A* Search can make use of different heuristics to decide how the agent can move. A* in the absence of any heuristic is the same as uniform cost search, where cells are added to the computed path at each step without any preferences. 

One obvious heuristic that can be used to improve the effectiveness of pathingfinding is using the straight-line distance between the agent and the target cells. Instead, we used the Manhattan Distance heuristic as that is more appropriate for the implementation enviornement.

The cost of exploring a cell in the grid given its current state s can be denoted by the function f:
f(s) = g(s) + h(s)

For each move the agent makes, it computes a path in preference of cells that moves it furthest away from it current position g(s) and cells that are closest to the target position h(s) via Manhattan Distance calculation.

##Running the program
Requirements:
- python
- some of your time

Run with:
python runner.py
