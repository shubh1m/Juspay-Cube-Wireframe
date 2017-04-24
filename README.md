# Juspay-Cube-Wireframe

Technologies used:
 * HTML5
 * HTML5-canvas
 * Javascript
 
## Use cases:
 `drag`: Rotate cube along the axis passing through center. Initial speed of rotation depends on the drag length which then decreases by a factor of `rate`.  
 `click`: Decreases the velocity by a factor of `fric` (set to 0.001).


## Code functionality:
1. Create a `\<canvas>` element which is used to create graphics.
2. `canvas.getContext()` method returns a 2 dimensional drawing context on the canvas.
3. Create an array consisting of cube vertices in 3D. Also create a 'faces' array which has indexes of vertices which create each face of the cube.
4. Call `drawCube()` function after the page has been loaded
5. `drawCube()` function draws each each face of the cube by using `project()` method which projects 3D coordinates to 2D.
6. Create eventListener function for drag events which includes:  
 &nbsp;&nbsp;&nbsp;&nbsp;* mousedown: get mouse pointer coordinates of the time when the mouse button is pressed  
 &nbsp;&nbsp;&nbsp;&nbsp;* mouseup: get coordinates of the mouse pointer when the mouse button is released. Calculate change in coordinates from the time when mouse button is pressed to the time when it is released. If the change in coordinates is 0 => it is a click event, which further decreases rotation by a value `fric` each time a click event ocuurs.  
 Else it is a drag event which speeds up the rotation of cube with speed proportional to drag distance. On each frame change in angle decreases by a factor of `rate`.
7. On each drag, `fric` is set to 0.
