This is the readme for 2025 WISER Quantum Project
Project Name: Quantum Walks and Monte Carlo
Team Name: Team-Q
Team Member: Jesmer Wong (ID: gst-lUiSStdno9Zl8Tn)

Project Summary
Project 1 – Quantum Walk and Monte Carlo
This project aims to implement the concept of Stochastic Random Walk in Quantum World, inspired by the simple toy Galton Board.

The Galton board consists of a vertical board with interleaved rows of pegs. Beads are dropped from the top and, when the device is level, bounce either left or right as they hit the pegs. Eventually they are collected into bins at the bottom, where the height of bead columns accumulated in the bins approximate a bell curve. Overlaying Pascal's triangle onto the pins shows the number of different paths that can be taken to get to each bin.

If a bead bounces to the right k times on its way down (and to the left on the remaining pegs) it ends up in the kth bin counting from the left. Denoting the number of rows of pegs in a Galton Board by n, the number of paths to the kth bin on the bottom is given by the binomial coefficient nCk. Note that the leftmost bin is the 0-bin, next to it is the 1-bin, etc. and the furthest one to the right is the n-bin - making thus the total number of bins equal to n+1 (each row does not need to have more pegs than the number that identifies the row itself, e.g. the first row has 1 peg, the second 2 pegs, until the n-th row that has n pegs which correspond to the n+1 bins). If the probability of bouncing right on a peg is p (which equals 0.5 on an unbiased level machine) the probability that the ball ends up in the kth bin equals nCk pk (1 – p)(n-k). This is the probability mass function of a binomial distribution. The number of rows correspond to the size of a binomial distribution in number of trials, while the probability p of each pin is the binomial's p. According to the central limit theorem, the binomial distribution approximates the normal distribution provided that the number of rows and the number of balls are both large. Varying the rows will result in different standard deviations or widths of the bell-shaped curve or the normal distribution in the bins.

To implement this, as per Fig. 1, we use lines of the qubit lines as to be our bins, flip the bit on its center of the board, and then we use continuous controlled swaps to flip the states so that goes with half the probability when observed, or with the introduction of the rotation gate Rx instead of the Hadamard gate H, mimicking the ball with biased probability. With this module we could then generalize for multiple layers n by considering the Input, Hidden and Output layers. By observing the individual behaviours and functionalities on each of the modules inside these layers, it is believed this generalization can produce corresponding results (Fig. 3).


