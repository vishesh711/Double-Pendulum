Lyapunov Exponent Heatmap and Double Pendulum Animation
Overview
This project visualizes the Lyapunov exponent heatmap for a double pendulum system and allows the user to interactively animate the double pendulum based on selected initial conditions from the heatmap. It includes both 2D and 3D heatmap visualizations and provides an interactive way to explore the dynamics of the double pendulum.

Prerequisites
To run this project, you need the following libraries:

numpy
matplotlib
animation
pygame
Install the required packages using pip:

sh
Copy code
pip install numpy matplotlib animation pygame
Files
main.py: Main script for plotting the Lyapunov exponent heatmap and handling user interaction for animation.
data.csv: CSV file containing the Lyapunov exponent values for the heatmap.
animation.py: Script for animating the double pendulum using Pygame.
Usage
Plotting the Lyapunov Heatmap

The main script reads the Lyapunov exponent values from data.csv and plots a heatmap. The user can interact with the heatmap to select initial conditions for the double pendulum animation.

python
Copy code
import numpy as np
from matplotlib import pyplot as plt
import animation

def plot_lyapunov_heatmap(lyapunov_heatmap, theta1_range, theta2_range):
    # Code for plotting the heatmap...
Reading Lyapunov Heatmap from CSV

The function read_lyapunov_heatmap_from_csv reads the heatmap data from a CSV file.

python
Copy code
def read_lyapunov_heatmap_from_csv(input_file):
    lyapunov_heatmap = np.loadtxt(input_file, delimiter=',')
    return lyapunov_heatmap
Running the Heatmap Plot

python
Copy code
input_file = "/content/data.csv"
lyapunov_heatmap = read_lyapunov_heatmap_from_csv(input_file)

Hdimensions = 1260
Wdimensions = Hdimensions

theta1_range = np.linspace(0, 2 * np.pi, Hdimensions)
theta2_range = np.linspace(0, 2 * np.pi, Wdimensions)

plot_lyapunov_heatmap(lyapunov_heatmap, theta1_range, theta2_range)
3D Heatmap Visualization

The plot_lyapunov_heatmap_3d function provides a 3D visualization of the heatmap.

python
Copy code
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

def plot_lyapunov_heatmap_3d(lyapunov_heatmap, theta1_range, theta2_range, downsample_factor=10):
    # Code for 3D plotting...
Animating the Double Pendulum

The animate function handles the double pendulum animation using Pygame.

python
Copy code
import numpy as np
from numpy.linalg import inv
from matplotlib import pyplot as plt
from math import cos, sin, pi
import pygame
import sys
import os

def animate(t1, t2):
    # Code for animation...
Interaction
Key Press Events: The script listens for key press events to handle user interaction.
Press 'u' to update and animate the double pendulum based on selected initial conditions.
Press 'y' to save the current initial conditions to a file.
Screenshots
Screenshots can be taken at specific times during the animation and saved to the Images/screenshots directory.

License
This project is licensed under the MIT License. See the LICENSE file for more details.

Acknowledgements
The double pendulum dynamics are based on the equations of motion for a double pendulum system. The heatmap visualization is inspired by studies on the chaotic behavior of double pendulums.

