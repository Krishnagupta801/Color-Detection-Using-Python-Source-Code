Project Title: Color Detection using Python
What it does (Overview)
This program lets you:
Load any image (e.g., test_image.jpg).
Click on any point in the image.

Instantly shows:

The color name of that point (e.g., "Sky Blue")

The RGB values (e.g., R=135, G=206, B=235)

Draws a rectangle filled with the clicked color and displays the color name.

This is useful for:

Designers and artists to identify colors.

Learning about computer vision & OpenCV.

As a mini project for a Python/AI/Data Science course.

What files you need
To make this work, you’ll need:

Python script — the main code that runs the project.

colors.csv — a CSV file that contains a database of color names and their RGB values.

An image file — any image you want to test (e.g., test_image.jpg).

*How it works (Step by Step)
1. Read color data
Use pandas to load colors.csv.

This file has color names and their RGB values, so the program knows what colors exist.

Example of colors.csv:

color_name	hex	R	G	B
Red	#FF0000	255	0	0
Green	#00FF00	0	255	0
Blue	#0000FF	0	0	255

2️. Load image
Use cv2.imread() to load the image file.

Resize it if needed so it fits on the screen.

3️.  Capture mouse click
Use cv2.setMouseCallback() to detect when the user clicks on the image.

Get the pixel’s RGB value at the clicked position.

4️.  Find closest color name
The script loops through all colors in the CSV.

Calculates the sum of differences:

cpp
Copy
Edit
diff = abs(R - csv_R) + abs(G - csv_G) + abs(B - csv_B)
Finds the color with the smallest difference — this is the best match.

5️.  Show result
Draw a rectangle filled with the clicked color on top of the image.

Display the color name and RGB values as text.

Choose white or black text so it’s always visible (depending on background brightness).

6️. Exit
Program keeps running until you press the ESC key.

⚙ Technologies & Libraries Used
Python — main programming language.
OpenCV (cv2) — to load images, detect mouse clicks, and draw.
pandas — to read and use the CSV color data.
