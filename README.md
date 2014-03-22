Processing-Screencast-01
========================

# Introduction to Processing with processingjs

## processing-1.4.1.js

    The local copy of the processingjs library

    This is the current version of the processing library we are 
    using for this sketch.
    
    We can also link to the libraru online:
    https://github.com/downloads/processing-js/processing-js/
    processing-1.4.1.js


## 01.html

    The basic processing sketch
    
    The minimal code for incorporating processing into a web page.
    Please note the processing object instantiation. 
    The default size of the canvas is 100 x 100 pixels.
   

## 02.html

    The simplest use of processing
    
    We are here using processing as an in-page javascript console.


## 03.html

    Introducing setup() and draw()
    
    Setting the basic attributes of the sketch; for example, note 
    the processing commands for setting the size of the sketch and 
    the background color of its canvas. our canvas shows up when 
    these commands are run. In the inspector, note how the canvas 
    tag is updated


## 04.html

    Drawing functions in Processing
    
    Notes:
    
    1. After calling size(), the environment variables width and 
    height hold the dimensions of the sketch.
    
    2. By default the draw() function is called repeatedly, and in
    this case, prints the frame rate that processing is aiming to
    maintain. The default frame rate is 60 fps.
    
    3. Processing offers a wide range of drawing functions that you 
    can play around with. Please consult the online documentation at
    http://processingjs.org/reference/
    
    4. If you uncomment the noLoop() line (line 27), you will see 
    that draw() is then only run once.
    
    5. The javascript functions draw() and setup() can be renamed to
    anything we wish. The function names that we assign to p.setup 
    and p.draw determine the behavior of the processing sketch.


## 05.html

    Animation 0. A very simple animation
    
    Notes:
    
    1. We can use frameCount to control what is drawn in specific frames.
    in this case we ensure that a test pattern is drawn to the screen for
    the first 120 frames of the animation (which roughly corresponds to 2
    seconds).
    
    2. After the opening pattern is shown for roughly 2 seconds, a ball 
    is drawn at the center of the canvas.


## 06.html

    Animation 1: A falling ball
    
    Notes:
    
    1. The x and y variables will hold the position of the ball. You can 
    see this on line 42 where they are being passed in ball as arguments 
    and on line 67 where the arguments are used to set the position of
    the center of the ellipse representing the ball.
    
    2. As you can see on line 43, every animation frame, we change the y
    position of the ball by one pixel. This means that the ball will move
    downwards at roughly 60 (frame rate) pixels per second.


## 07.html

    Animation 2: A bouncing ball
    
    Notes:
    
    1. The variable direction holds the direction of the ball’s motion. 
    It is used on line 48 to change the sign of the change to the amount 
    by which the y position of the ball is changed on line 46.
    
    2. Line 48 is run only if the ball moves outside the bounds of the
    sketch as determined by testing its y position compared to the top 
    and bottom of the sketch on line 47. (|| is a logical OR.)


## 08.html

    Special effects 1: Leaving a trail
    
    Note that by a simple change in how the background of the sketch is
    refreshed, we can have the ball leave a small trail  behind. 
    
    Instead of drawing a solid color into the background of the sketch, 
    draw a rectangle the size of the background with a fill color with a
    transparency.


## 09.html

    Animation 3: Follow the mouse
    
    a simple animation in which the ball follows the mouse and leaves a
    small trail behind: Note that the ball's (ellipse's) osition is set 
    to the mouse position in line 42.

## 10.html

    Animation 4: A simple "paint" app
    
    Processing not only makes it easy to get the current mouse position 
    (mouseX, mouseY) but also saves the previous mouse position in the 
    variables pmouseX and pmouseY.
    
    By drawing a line from the current position of the mouse to its 
    previous position, we can make a simple paint program. note that to
    leave a trail on the canvas permanently, lines 39 and 40 need to be
    commented.


## 11.html

    Animation 5: A responsive grid
    
    Notes:
    
    1. In lines 53 through 62, we draw a regular grid where in each 
    cell we have a squares with a circle at its centers.
    
    2. The size of the circle drawn at a grid position depends on its
    distance from the mouse’s position. (lines 55 and 60).
    
    3. Change line 55 to "var dotSize = gridSize" to see a version of
    the grid that is not interactive.
    
    2. The distances are measured in gridSize units, and that is why 
    we multiply them by the grid size to draw them in the correct px
    dimensions in commands on lines like 58 and 60.


## 12.html

    Interaction 1: Changing the grid color based on a mouse event
    
    Each time the mouse is released, line 53 is run which changes the 
    color used for drawing the grid.


## 13.html

    Interaction 2: Additional mouse events
    
    Notes:
    
    1. Processing provided listeners for a variety of mouse events. 
    We have written functions for handling the events fired when the 
    mouse is pressed, released, moved, or dragged.
    
    2. The dots closest to the mouse position are the smallest when 
    the mouse is moved (but not dragged)
    
    3. But when the mouse is dragged, the dots closest to the mouse 
    position are largest.
    
    4. Refinements: The mouse getting pressed changes the color of 
    the grid and flips the behavior in 2 so that the dots closest to 
    the mouse are largest. And when the mouse is released, the dots 
    closest to the mouse become smaller again.


## 14.html

    Interaction 3: Capturing key events
    
    Notes:
    
    1. we are using the arrow keys to move the white dot around.
    
    2. Also a mouse interaction enhancements: when dragging the 
    mouse, the dot appears at point opposite to the mouse position 
    with respect to the center of the canvas.


## 15.html

    Interaction 4: listening for other keys (and using fonts)
    
    When a letter of alphabet is typed on the keyboard, the letter 
    appears next to the active cell in the grid. The drawn letter 
    is updated when a new key is pressed.
    

## 16.html

    External Data: Incorporating JSON data
    
    The shape and location of the triangle drawn when the key ‘0’ 
    is held down is determined by the json data provided.
