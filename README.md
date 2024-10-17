# Electric-Field-Project
You can see the electric field lines by inputting different types of charges in pygame. The output will be in matplotlib.

It is a collaborative project between me and two other classmates. My classmates were in charge of coding the theory part of the electric fields (see test_matrix_rod.py; matplotlib)
I was in charge of the visualizing part (by using the pygame module; visualize.py).

A project that spanned during October, while having classes.




Window: The interface of the pygame window
Screen: The gray area in the pygame window


-------------------------- FOR THE USER --------------------------

How does it work?

    - Run visualize.py

    - You will see the interface. On the right of the screen, click either the blue (point charge),
        the yellow (plane), the green (rod) or the orange (disk)

    - On the left side of the screen, set up its sign (red for positive or blue for negative)

    - Under the screen, set up its charge. If you want to go an exponent up, click the green button 
        on the right of the charger. Click the red button on its left to go an exponent down

    - If it's a point_charge:
        - Click the screen where you want the center of it to blue
    - If it's a plane:
        - Click the screen where you want one of the rectangle's corner to start. Click another in a different position. These two 
          coordinates will form the 2 opposite diagonal corners of the rectangle.
    - If it's a rod:
        - Similar to the plane, but it is a bit buggy. To make sure that you get what you want, start with the top left corner of the 
          rod (its width is fixed).
          If you want the rod to be horizontal, click the screen a second time more on the right than down
          If you want the rod to be vertical, click the screen a second time more down than on the right

    - If it's a disk:
        - Click a first time in the screen to mark the center of the disk. Click a second time to determine its radius

    - If ever you want to go back, click the red button on the top left of the window. (It may bug a little bit)

    - If you are satisfied with the screen, click the red button on the bottom right to send the values to matplotlib



----------------------------------------------------------------------------






-------------------------- FOR R. AND T. --------------------------


What is the output in pygame?

    - It will output a list containing the charges that you have put in pygame, and the last line in main_akira stores the output as charges_info:

    - charges_info[i]: the charge i itself (either point charge, plane, rod or disk)

    - We characterize the charges by their type. We get its type by printing charges_info[i][1]:

        - "point": point charge
            - charges_info[i][0]: It returns a list [x_coords, y_coords] containing the center coordinates of the point charge

        - "plane": plane
            - charges_info[i][0]: It returns a list [x_start, y_start, x_length, y_length]. x_start and y_start are the coords 
              of the top left of the rectangle. x_length is the rectangle's length on the right and y_length is the 
              rectangle's length downwards

        - "rod": rod
            - charges_info[i][0]: Idem as plane, except, depending on where you put your starting coords and your end coords, either
              x_length or y_length will hold a fixed value (of 12 pixels as width)

        - "disk": disk
            - charges_info[i][0]: It returns a list [(x_center, y_center), radius]. x_center and y_center are the coordinates of the 
              disk's center; radius is the radius of the disk

    - To have access to the "charge number" of the charges, print charges_info[i][2]. It gives the "charge number" of the charge.

Here is an example:

[
    
    [(457, 112), 'point', 6.9400000000000004e-09], (positive point charge)
    [(177, 78), 'point', -4.5400000000000005e-09], (negative point charge)
    [[469, 178, 24, 40], 'plane', 6.160000000000001e-08], (positive plane)
    [[184, 278, 107, 64], 'plane', -4.63e-10], (negative plane)
    [[299, 92, 12, 61], 'rod', 4.63e-10], (positive rod stretching in the y direction)
    [[427, 368, 81, 12], 'rod', -4.63e-13], (negative rod stretching in the x direction)
    [[(361, 397), 37.0], 'disk', -8.06e-06], (negaative disk)
    [[(303, 222), 74.72616676907762], 'disk', 8.06e-12] (positive disk)
    
]


-------------------------- !!! CAREFUL !!! --------------------------

The coordinates of all charges are relative to the pygame window. I set the pygame window to be (700, 550), i.e.
700 pixels lond (on the right) and 550 pixel wide (down)

The screen starts at the coordinates (150, 50) and its dimensions are 400 pixels long and 400 pixels wide, i.e.
the center of the screen is at (350, 250)


