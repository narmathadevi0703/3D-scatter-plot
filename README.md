# 3D-scatter-plot


3D Point Cloud Visualization Using Rotation and Projection


1.	Project Overview:

This project demonstrates the visualization of randomly generated 3D points on a 2D screen. The system generates points in three-dimensional space, applies rotation transformations (Yaw, Pitch, and Roll), and then projects the transformed points onto a 2D canvas for display.
The project helps in understanding the fundamentals of:
•	3D coordinate systems
•	Random point generation
•	Rotation matrices
•	Degree-to-radian conversion
•	Orthographic projection
•	Perspective projection
•	Computer graphics visualization



2.	Workflow of the Project :

The project follows these steps:
1.	Generate random 3D points.
2.	Store the points in a JSON file (data.json).
3.	Load the points into the visualization program.

4.	Apply rotation transformations:
o	Yaw (Y-axis rotation)
o	Pitch (X-axis rotation)
o	Roll (Z-axis rotation)
5.	Convert rotation angles from degrees to radians.
6.	Apply projection:
o	Orthographic Projection OR
o	Perspective Projection
7.	Draw the projected points on the HTML canvas.
8.	Continuously update the display to create rotation animation.


Workflow Diagram:


Random Point Generation
↓ data.json
↓ Load Points
↓
Apply Rotations

(Yaw, Pitch, Roll)
↓ Projection
(Orthographic/Perspective)
↓
Draw on Canvas
↓
Display 3D Object


3.	Random Number Generation for 3D Points:
The project generates points randomly inside a specified range.


x = Math.random() * 200 - 100;
y = Math.random() * 200 - 100;
z = Math.random() * 200 - 100; Example Point:
(45.2, -23.6, 80.1)

Each point represents a position in 3D space.


4.	Rotation Formulas:
Rotations are used to change the orientation of the 3D object.


	Yaw Rotation (Rotation about Y-axis) Yaw rotates the object left or right.
Formula:
x' = x cos(θ) + z sin(θ) z' = -x sin(θ) + z cos(θ)
Where:
•	θ = yaw angle
•	x', z' = new coordinates after rotation


	Pitch Rotation (Rotation about X-axis):
Pitch rotates the object upward or downward.


Formula:
y' = y cos(θ) - z sin(θ) z' = y sin(θ) + z cos(θ)

Where:
•	θ = pitch angle

	Roll Rotation (Rotation about Z-axis):
Roll rotates the object clockwise or counterclockwise.


Formula:
x' = x cos(θ) - y sin(θ) y' = x sin(θ) + y cos(θ)

Where:
•	θ = roll angle .


5.	Degree-to-Radian Conversion:
x' = x cos(θ) - y sin(θ) y' = x sin(θ) + y cos(θ) Where:
•	θ = roll angle

6.	Degree-to-Radian Conversion

JavaScript trigonometric functions (sin, cos) require angles in radians.

Therefore, degrees must be converted to radians before calculations.
Formula:
Radians = Degrees × π / 180


Example:
90° × π / 180
= π/2
= 1.5708 radians JavaScript Code:
const radians = degrees * Math.PI / 180; Purpose:
•	Enables correct trigonometric calculations.
•	Required for rotation formulas.
6.	Orthographic Projection Explanation
Orthographic projection displays 3D objects without considering depth.
Objects remain the same size regardless of distance from the viewer. This projection is commonly used in:
•	Engineering drawings
•	CAD software
•	Technical diagrams

Formula
x_screen = x


y_screen = y After centering:
x_screen = x + canvasWidth/2


y_screen = y + canvasHeight/2
Characteristics
•	No perspective distortion
•	Parallel lines remain parallel
•	Easier mathematical calculations


7.	Perspective Projection Explanation
Perspective projection simulates human vision.
Objects farther away appear smaller, creating a realistic 3D effect. This projection is commonly used in:
•	Video games
•	Computer graphics

•	Virtual reality
Formula
Scale = D / (D + z) Where:
•	D = viewing distance
•	z = depth coordinate Projected coordinates: x_screen = x × Scale

y_screen = y × Scale Example:
Scale = 400 / (400 + z) Then:
x_screen = x × Scale


y_screen = y × Scale
Characteristics
•	Realistic depth perception
•	Distant objects appear smaller
•	Commonly used in 3D rendering

8.	Overall Implementation
The project starts by generating random points in 3D space. These points are saved in a JSON file and loaded into the visualization program.
During execution:
1.	The program reads the 3D coordinates.
2.	Rotation angles (Yaw, Pitch, Roll) are applied.
3.	Angles are converted from degrees to radians.
4.	Rotation formulas calculate new point positions.
5.	The transformed points are projected from 3D space onto a 2D canvas.
6.	Orthographic or Perspective projection is used depending on the selected mode.
7.	The projected coordinates are drawn on the screen.
8.	Continuous updates create smooth animation and allow the user to observe the object from different orientations.
The result is an interactive 3D point cloud visualization that demonstrates the fundamental principles of computer graphics, coordinate transformations, and projection techniques.
Output:
<img width="945" height="489" alt="image" src="https://github.com/user-attachments/assets/4404e3f6-e14b-4d6c-b42a-b0133697d0df" />



Conclusion
This project successfully demonstrates how randomly generated 3D points can be transformed and visualized on a 2D display using rotation matrices and projection techniques. Through the implementation of Yaw, Pitch, Roll, degree-to-radian conversion, orthographic projection, and perspective projection, the project provides a practical introduction to the core concepts used in modern computer graphics systems and 3D visualization applications.
