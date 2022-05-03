This is a repo condensing my contributions to https://github.com/Nicholas-Schenk/AI_HW-1 into an easier-to-digest format. 

# Exploring A* Search Algorithm
A* is a search algorithm used for path-finding.

A* search alogirthm has been implemented in 3 flavors: 
- Repeated Forward A*
- Repeated Backward A*
- Repeated Adaptive A*

Our search algorithms operate in an 2D grid world, where the Agent is placed in 1 cell and the Target destination is placed in another.
A* Search can make use of different heuristics to decide how the agent can move. A* in the absence of any heuristic is the same as uniform cost search, where cells are added to the computed path at each step without any preferences. 

One obvious heuristic that can improve pathingfinding is straight-line distance between the agent and the target. Instead, we used the Manhattan Distance heuristic as that is more appropriate for the implementation enviornement.

The cost of exploring a cell in the grid given its current state *s* can be denoted by the function *f*:

*f(s) = g(s) + h(s)*

For each move the agent makes, it computes a path in preference of cells that moves the agent furthest away from the its current position *g(s)* and cells that are closest to the target position *h(s)* via Manhattan Distance calculation.


## Technical Details

### *Grid Generation*

By default, the program randomly generates a square grid of size *n*. The grid is initially empty, but is later populated with an Agent and Target destination cell. Grid generations makes use of Depth First Search to then fill the grid with blocking cells using random probability, which do not allow the Agent to pass through. 

### *Program Execution*

Within the 3 different algorithms, the program runs two variations of Repeated Forward A*, the only difference between these two is how the algorithm handles tie-breaking when competing cell states share equal decision cost *f(s)*. In all variations of A*, a minimum heap is used to prioritize which cell the Agent should add to its computed path. When decision costs are equal in the aforementioned scenario, we use *g(s)* to break the tie. The default configuration is for higher *g(s)* values to be prefered.

Upon execution, the program will run each algorithm and its variations. Each generated grid with its corresponding Agent will display. On completion, the program will output statistical data such as runtime and steps to reach the target for comparison.

### *Agent Performance*

The Agent is always assumed to be blind. It can only observe 1 cell in each direction at any given time. However it is capable of remembering the state of the grid observed thus far. The agent will rarely find the exact shortest path to the Target because the A* search algorithm as implemented under these conditons is inherently at the mercy of the Agent's "vision" contraints. 

If the Agent had access to the entire grid at all times, then the bottleneck would fall onto the heuristic A* makes use of. In this case, that would be the Manhattan Distance. In this environment this heuristic can never overestimate the distance between the Agent and the Target. Therefore, the Agent would always be able to consistenly find the shortest path every time.

## Running the program

Requirements:
- python
- *colorama* for python `pip install colorama`
- some of your time

Run with:
`python runner.py`
