#Bouncing a Ball Around with HTML5 and JavaScript using a start and stop buttons to control the motion of the bouncing ball.
HTML

To start, you will need to create a basic HTML document. It’s best if you follow along with me as we go — so go ahead and create your HTML document now.
Let’s add our <canvas> element inside the <body> tag. Though we only have one <canvas> element in our HTML for this example, I have still assigned an ID to it (myCanvas) just to make it easier/quicker to select it later on via JavaScript. I also defined the element’s dimensions (width/height), however, you could just as well do that via CSS by targeting the #myCanvas ID.
<canvas id="myCanvas" width="500" height="400">
</canvas> 
  
JavaScript

Now let us start with the actual work of creating our shapes in JavaScript.
Draw the Circle
We are going to draw a circle using the arc[1] and fill[2] methods. We now define the context, initiate the drawing, then we use color and style methods to fill in the color and dictate the shape (using a Math object for a circle).

Move the Circle

Now that we have the circle, let’s try to move it. We’ll replace the hardcoded values of the coordinates in the .arc method (100, 100 — the first two arguments) with variables x and y, which we will then increment by an amount of dx and dy.
Also since we need to redraw the circle at the new positions, we’ll move the code into a function called draw() and call it every 10ms using JavaScript’s setInterval() function and To erase the old circles, we’ll need to call the clearRect method right at the start of our draw() function so that it clears out the previous circle before it draws the new one.

Limit the Area with an Imaginary Wall

Now it’s time to bounce the ball off the corners of the <canvas> element.
Well, that’s easy: All you need to do is check if the values of x and y are beyond the canvas dimensions, and if so, we need to reverse the direction by setting values of dx and dy to the negative values.

If all goes well, you should see a ball bouncing around the four corners of the canvas element.
