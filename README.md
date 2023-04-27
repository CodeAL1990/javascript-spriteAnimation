# javascript-game

Key learning points are sprite animation, parallax background, different enemy types, state design patterns, collision detection, and particle effects
Starting with sprite animation
Initialize canvas and link to html
Initialize context to desired context (2d, 3d etc)
Create basic canvas of fixed width and height
Initialize playerImage variable to new Image()
Link playerImage variable to asset source
Create animate function
Add clearRect() to erase canvas at start of each animation
Add drawImage() specifies a specific area to draw onto canvas using up to 9 parameters
Add requestAnimationFrame(animate) to call animate function at to update animation before next repaint
Initialize frameX and frameY globally to control the coordinates in drawImage
Initialize spriteWidth and spriteHeight globally to carve out the desired pose for each frame;
