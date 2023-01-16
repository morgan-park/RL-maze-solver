# Maze Solving Using Reinforcement Learning (Dynamic Programming) 

Selected code (Image Processing and Dynamic Programming) from a final team project that I led in Reinforcement Learning at Tufts University (Fall 2022). Four images of square maze with different complexities are randomly chosen and downloaded from Google and image processed to transfer to a grid for Markov Decision Process (the images of square maze: https://github.com/demipin/RL-maze-solver/tree/main/images). 

<p align="center">
  <img src="https://user-images.githubusercontent.com/94096127/212436312-0e993fa9-f153-4334-b36b-cf264e9768b3.png">
</p>
<p align="center">
  From Maze To Grid
</p>

In the team project, different Reinforcement Learning techniques (Dynamic Programming, Temporal Difference, and Deep Q Reinforcement Learning) are used to solve the maze and the performance of the techniques are compared. This repository includes the codes for Dynamic Programming only.

## Setup 

* **Each cell of a grid**: a state <br />


* **Possible actions**: Up, Down, Right, Left <br />


* **Environment (Deterministic and Non-deterministic Maze)**: <br />
    On top of the above-mentioned four different mazes based on deterministic environment, non-deterministic elements are added and experimented. 
    Slippery cells are randomly assinged to the four mazes. In the slippery cells, the agent has only a 50% of chance moving in the intended direction.
    With the other 50% of chance, the agent stays at the current state. <br />


* **The use of value functions**: <br />
    The goal of RL techniques used in this project is to learn and obtain an optimal policy by maximzing the rewards. 
    The key idea of Dynamic Programming is the use of value functions to organize and structure the search for optimal policy.
    The following equation is used to compute the state-value function in policy evaluation:
    
    <p align="center">
      <img src="https://user-images.githubusercontent.com/94096127/212459585-7f6a4235-b285-4ff0-899a-759e5927c212.png">
    </p>    
    
     where S is the set of all nonterminal states; π(a|s) is the probability of taking action a in a state s under policy π; r is the reward; 
     γ is discounting factor for the future state-action rewards.
     
     To obtain optimal policies, the following equation, which satisfy the Bellan optimality equations, is used:
     
     <p align="center">
       <img src="https://user-images.githubusercontent.com/94096127/212460135-4cd08016-f81c-4722-9a46-306a67b9b07e.png">
     </p>
     
     where q*(s,a) is the value of taking action a in state s; A(s) is the set of all actions available in state s.
 
     The pseudocode (policy iteration) is as follows:
      <p align="center">
       <img src="https://user-images.githubusercontent.com/94096127/212460221-9c97c3b6-2939-48ea-803b-b718684a7923.png">
      </p>

## Description
  * Eight different cases in total: deterministic mazes 1, 2, 3, 4 & non-determinisitc mazes 1, 2, 3, 4
  
 <p align="center">
 <img src="https://user-images.githubusercontent.com/94096127/212537707-38b53393-2a74-477b-b73c-8d28581244e9.jpg" width="200" height="200">
 <img src="https://user-images.githubusercontent.com/94096127/212537708-5e2aa448-753a-40fe-be4b-9d12269d151b.jpg" width="200" height="200">
 <img src="https://user-images.githubusercontent.com/94096127/212537709-caff73a9-2c0d-4a0a-af2c-35e7606209fd.jpg" width="200" height="200">
 <img src="https://user-images.githubusercontent.com/94096127/212537710-13cb5a3a-4535-4f25-8b7b-1080cb7661c6.jpg" width="200" height="200">
</p>
 <p align="center">
  Maze 1, 2, 3, 4 (From Left To Right)
 </p>
  
  
  * The codes take an image of maze, image process to transfer the maze to a grid, visualize the environment, and return the environment as a numpy array based on which the agent can learn. 
  
  <p align="center">
   <img src="https://user-images.githubusercontent.com/94096127/212535080-18923c35-c8be-47ef-b492-c6c1f1e1cb2f.png" width="250" height="250"> 
    <img src="https://user-images.githubusercontent.com/94096127/212535084-253094f8-d9a2-40b2-ba71-0ecada79863a.png" width="250" height="250" />
    <img src="https://user-images.githubusercontent.com/94096127/212535089-3bb7160d-7b07-4540-9bfd-0d32a1a7080b.png" width="250" height="250" />
    </p>
 <p align="center">
  Example(Maze 1): Numpy Array(Left) Environment Visualized (Center) and Path Visualized (Right)
  </p>

  * It prints the information on the image
  * It shows the number of policy iteration performed, execution time, and memory usage that it takes to learn.
  * The path found is visualized.
  * It also generates a csv file which traces the updates of Q table.
  
## Contents
Codes written in Python with Jupyter Notebook (ipynb file)

  * [Maze 1 (Deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_deterministic_maze1.ipynb)
  * [Maze 1 (Non-deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_NON-deterministic_maze1.ipynb)
  * [Maze 2 (Deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_deterministic_maze2.ipynb)
  * [Maze 2 (Non-deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_NON-deterministic_maze2.ipynb)
  * [Maze 3 (Deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_deterministic_maze3.ipynb)
  * [Maze 3 (Non-deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_NON-deterministic_maze3.ipynb)
  * [Maze 4 (Deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_deterministic_maze4.ipynb)
  * [Maze 4 (Non-deterministic)](https://github.com/morgan-park/RL-maze-solver/blob/main/image_processed_DP_NON-deterministic_maze4.ipynb)


## Experiment Result
  * asterisk(*): non-deterministic
  * max # of policy iteration: 100
  * reward for goal state: 1,000
  * reward for all other states: -1
<p align="center">
 <img src="https://user-images.githubusercontent.com/94096127/212538844-43b656cc-f89c-4427-997a-f9104e9d9159.png">
 </p>
 

## Reference
* Sutton, R., & Barto, A. (2015). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
