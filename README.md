# Game of Life on Graphs (GLG)
A generalization of John Conway's famous Game of Life from the 2-dimensional grid to an arbitrary graph.

 The Game of Life serves as a classic example of how large-scale order and complexity can emerge out of systems with fundamentally simple components. Conway's simulation takes place on a 2-dimensional grid of nodes, each of which can be initialized as "alive" or "dead". Then, the following rules dictate how the system will evolve:

  - Any live cell with fewer than two live neighbors dies, as if by underpopulation.
  - Any live cell with two or three live neighbors lives on to the next generation.
  - Any live cell with more than three live neighbors dies, as if by overpopulation.
  - Any dead cell with exactly three live neighbors becomes a live cell, as if by reproduction.
  
 Here, a "neighbor" is defined as the set of eight directly adjacent horizontal, vertical, and diagonal cells. Iterating this set of rules to update the board, complex self-organized structes are seen to emerge, which exhibit macrosopic properties like spinning, locomotion, and replication. In fact, the game itself is Turing complete, meaning it can in theory perform any computation that a general purpose computer can.
 
 There are many ways to tweak the game to observe novel behavior. For instance, the grid could be made of hexagonal cells instead of square ones, changing the number of neighbors and structure of the board. Periodic boundary conditions could be imposed to effectively play the game on an alternate geometry. The modification I explore in this project is to generalize the structure to that of an arbitrary graph.
 
 The file "GLG.ipynb" contains the Python code to generate a randomly connected graph and play the Game of Life on it. Now, a node's neighbors are simply the set of directly connected nodes in the network. This adjustment calls for a slight modification to the rules:

  - Any live cell with fewer than <b><em>a</em></b> live neighbors dies, as if by underpopulation.
  - Any live cell with fewer than <b><em>d</em></b> dead neighbors dies, as if by overpopulation. 
  - Any dead cell with exactly <b><em>r</em></b> live neighbors becomes a live cell, as if by reproduction.

 We are free to explore different structures that arise by modifying <b><em>a</em></b>, <b><em>d</em></b>, and <b><em>r</em></b>. The classic Game of Life's 2-dimensional grid and rules can now be thought of as a special case of the Game of Life on Graphs.
 
 The example given in the Jupyter Notebook sets these three parameters all to 1. The graph is set to a size of 15 nodes and edges are added at random. Initially, only node 0 is set to "alive" (green) and all other nodes are "dead" (black). Iterating, we find that a repeating cycle emerges: state 9 is equivalent to state 3, yielding a cycle length of 6. Modifying these paremeters, we can explore conditions that lead to larger or smaller cycles. In certain cases, the game will find a stable state, or all the nodes will die out.
 
 Learn more at https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life  
  Inspiration from https://arxiv.org/pdf/2111.01780.pdf
 
