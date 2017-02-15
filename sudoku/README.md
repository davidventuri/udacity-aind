# Udacity Artificial Intelligence Nanodegree
## Introductory Project: Sudoku Solver

1. Implement the Sudoku technique called "naked twins"
2. Modify your code to solve a diagonal Sudoku

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.

## Questions for Evaluation

### Question 1 (Naked Twins)
**Q:** How do we use constraint propagation to solve the naked twins problem?  
**A:** The constraint for the naked twins technique is that no squares in the unit(s) that contain both of the naked twins squares except for those two squares can contain the twin values. By eliminating these twin values from the digit possibilities of the non-naked twin squares, we have made our sudoku simpler to solve. In other words, we used a local constraint to reduce the search space. We give ourselves the opportunity to enforce constraints in other parts of the grid that were previously unidentifiable, whether it is using the naked twins strategy again or a different strategy. These steps get us closer to a grid where each box only has one possible digit remaining, i.e., a solution.

### Question 2 (Diagonal Sudoku)
**Q:** How do we use constraint propagation to solve the diagonal sudoku problem?  
**A:** All that is required to solve the diagonal sudoku problem is to introduce two new units - one for each diagonal - and to add them to our unit list. Two new constraints are created: the digits 1-9 must appear only once in each of these new units. Each box along the diagonal now belongs to another unit and now has new peers. The strategies (in this project's case: elimination, only choice, and naked twins) do not change, there is just another set of constraints to enforce. More specifically, more units and peers of which to be aware. We continue the process of enforcing a constraint to reduce the search space to enforce more constraints to find a solution.

## Software Requirements

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).
