# An introduction to Processing with Processing.js

## Index of Files

> + [The local copy of the Processing.js library `(processing-1.4.1.js)`](#00)
> + [The basic Processing sketch `(01.html)`](#01)
> + [The simplest use of Processing `(02.html)`](#02)
> + [Introducing `setup()` and `draw()` `(03.html)`](#03)
> + [Drawing functions in Processing `(04.html)`](#04)
> + [Animation 0 -- A very simple animation `(05.html)`](#05)
> + [Animation 1 -- A falling ball `(06.html)`](#06)
> + [Animation 2 -- A bouncing ball `(07.html)`](#07)
> + [Special effects 1 -- Leaving a trail `(08.html)`](#08)
> + [Animation 3 -- Follow the mouse `(09.html)`](#09)
> + [Animation 4 -- A simple "paint" app `(10.html)`](#10)
> + [Animation 5 -- A responsive grid `(11.html)`](#11)
> + [Interaction 1 -- Changing the grid color based on a mouse event `(12.html)`](#12)
> + [Interaction 2 -- Additional mouse events `(13.html)`](#13)
> + [Interaction 3 -- Capturing key events `(14.html)`](#14)
> + [Interaction 4 -- listening for other keys (and using fonts) `(15.html)`](#15)
> + [External Data -- Incorporating JSON data `(16.html)`](#16)

### <a name='00'></a> The local copy of the Processing.js library: [`processing-1.4.1.js`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/processing-1.4.1.js)

This is the current version of the Processing library we are using for this sketch.

We can also link to the library [online](https://github.com/downloads/processing-js/processing-js/processing-1.4.1.js).


### <a name='01'></a> The basic Processing sketch: [`01.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/01.html)

The minimal code for incorporating Processing into a web page. Please note the Processing object instantiation. The default size of the canvas is `100 x 100` pixels.
 

### <a name='02'></a> The simplest use of Processing: [`02.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/02.html)

We are here using Processing as an in-page JavaScript console.


### <a name='03'></a> Introducing `setup()` and `draw()`: [`03.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/03.html)

Setting the basic attributes of the sketch; for example, note the Processing commands for setting the size of the sketch and the background color of its canvas. Our canvas shows up when these commands are run. In the inspector, note how the canvas tag is updated.


### <a name='04'></a> Drawing functions in Processing: [`04.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/04.html)

#### Notes

1. After calling `size()`, the environment variables width and height hold the dimensions of the sketch.

2. By default the `draw()` function is called repeatedly, and in this case, prints the frame rate that processing is aiming to maintain. The default frame rate is `60 fps`.

3. Processing offers a wide range of drawing functions that you can play around with. Please consult the [online documentation](http://processingjs.org/reference/)

4. If you uncomment the [`noLoop()` line (#27)](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/04.html#L27), you will see that `draw()` is then only run once.

5. The JavaScript functions `draw()` and `setup()` can be renamed to anything we wish. The function names that we assign to `p.setup` and `p.draw` determine the behavior of the Processing sketch.


### <a name='05'></a> Animation 0 -- A very simple animation: [`05.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/05.html)

#### Notes

1. We can use `frameCount` to control what is drawn in specific frames. in this case we ensure that a test pattern is drawn to the screen for the first 120 frames of the animation (which roughly corresponds to two seconds).

2. After the opening pattern is shown for roughly two seconds, a ball is drawn at the center of the canvas.


### <a name='06'></a> Animation 1 -- A falling ball: [`06.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/06.html)

#### Notes

1. The `x` and `y` variables will hold the position of the ball. You can see this [on line 42](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/06.html#L42) where they are being passed in ball as arguments and [on line 67](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/06.html#L67) where the arguments are used to set the position of the center of the ellipse representing the ball.

2. As you can see [on line 43](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/06.html#L43), every animation frame, we change the `y` position of the ball by one pixel. This means that the ball will move downwards at roughly 60 (frame rate) pixels per second.


### <a name='07'></a> Animation 2 -- A bouncing ball: [`07.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/07.html)

#### Notes

1. The variable `direction` holds the direction of the ball’s motion. It is used [on line 48](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/07.html#L48) to change the sign of the change to the amount by which the `y` position of the ball is changed [on line 46](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/07.html#L46).

2. [Line 48](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/07.html#L48) is run only if the ball moves outside the bounds of the sketch as determined by testing its `y` position compared to the top and bottom of the sketch on line 47. (`||` is a [logical OR](http://processingjs.org/learning/basic/logicaloperators/).)


### <a name='08'></a> Special effects 1 -- Leaving a trail: [`08.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/08.html)

Note that by a simple change in how the background of the sketch is refreshed, we can have the ball leave a small trail behind. 

Instead of drawing a solid color into the background of the sketch, draw a rectangle the size of the background with a fill color with a transparency.


### <a name='09'></a> Animation 3 -- Follow the mouse: [`09.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/09.html)

A simple animation in which the ball follows the mouse and leaves a small trail behind. Note that the ball's (ellipse's) position is set to the mouse position in [line 42](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/09.html#L42).


### <a name='10'></a> Animation 4 -- A simple "paint" app: [`10.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/10.html)

Processing not only makes it easy to get the current mouse position (`mouseX`, `mouseY`) but also saves the previous mouse position in the variables `pmouseX` and `pmouseY`.

By drawing a line from the current position of the mouse to its previous position, we can make a simple paint program. Note that to leave a trail on the canvas permanently, [lines 39 and 40](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/10.html#L39-40) need to be commented out.


### <a name='11'></a> Animation 5 -- A responsive grid: [`11.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html)

#### Notes

1. In [lines 53-62](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L53-62), we draw a regular grid where in each cell we have a squares with a circle at its centers.

2. The size of the circle drawn at a grid position depends on its distance from the mouse’s position. (lines [55](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L55) and [60](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L60)).

3. Change [line 55](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L55) to `var dotSize = gridSize;` to see a version of the grid that is not interactive.

4. The distances are measured in `gridSize` units, and that is why we multiply them by the grid size to draw them in the correct `px` dimensions in commands on lines like [58](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L58) and [60](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/11.html#L60).


### <a name='12'></a> Interaction 1 -- Changing the grid color based on a mouse event: [`12.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/12.html)

Each time the mouse is released, [line 53](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/12.html#L53) is run which changes the color used for drawing the grid.


### <a name='13'></a> Interaction 2 -- Additional mouse events: [`13.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/13.html)

#### Notes

1. Processing provided listeners for a variety of mouse events. We have written functions for handling the events fired when the mouse is pressed, released, moved, or dragged.

2. The dots closest to the mouse position are the smallest when the mouse is moved (but not dragged)

3. But when the mouse is dragged, the dots closest to the mouse position are largest.

4. Refinements: The mouse getting pressed changes the color of the grid and flips the behavior in (2) so that the dots closest to the mouse are largest. And when the mouse is released, the dots closest to the mouse become smaller again.


### <a name='14'></a> Interaction 3 -- Capturing key events: [`14.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/14.html)

#### Notes

1. We are using the arrow keys to move the white dot around.

2. Also a mouse interaction enhancement: when dragging the mouse, the dot appears at point opposite to the mouse position with respect to the center of the canvas.


### <a name='15'></a> Interaction 4 -- listening for other keys (and using fonts): [`15.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/15.html)

When a letter of alphabet is typed on the keyboard, the letter appears next to the active cell in the grid. The drawn letter is updated when a new key is pressed.


### <a name='16'></a> External Data -- Incorporating JSON data: [`16.html`](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/16.html)

The shape and location of the triangle drawn when the key `0` is held down is determined by [the JSON data provided](https://github.com/DGMD-E-15/Processing-Tutorial-01/blob/master/16.html#L26-30).

---

## Resources

+ [Processing.js reference](http://processingjs.org/reference/)
+ [JavaScript Quick Start for Processing.js](http://processingjs.org/articles/jsQuickStart.html)
+ [_Learning Processing: A Beginner's Guide to Programming Images, Animation, and Interaction_ by Daniel Shiffman](http://www.learningprocessing.com/)
+ [_Processing: A Programming Handbook for Visual Designers and Artists_ by Casey Reas and Ben Fry](https://mitpress.mit.edu/books/processing)