# javascript-spriteAnimation

Key learning points are sprite animation, parallax background, different enemy types, state design patterns, collision detection, and particle effects
Starting with sprite animation
Initialize canvas and link to html
Initialize context to desired context (2d, 3d etc)
Create basic canvas of fixed width and height of 600px and center it with top left transform translate
Initialize playerImage variable to new Image()
Link playerImage variable to asset source
Create animate function
Add clearRect() to erase canvas at start of each animation
Add drawImage() specifies a specific area to draw onto canvas using up to 9 parameters
Add requestAnimationFrame(animate) to call animate function at to update animation before next repaint
Initialize frameX and frameY globally to control the coordinates in drawImage
Initialize spriteWidth and spriteHeight globally to carve out the desired pose for each frame;
Initialize frameX and frameY globally
frameX represents the rows on each sprite animation group
frameY represents the columns on each sprite animation group
Replace the hard coded width and height on drawImage with frameX and frameY
Initialize gameFrame globally
Initialize constant variable staggerFrames to 5
Create position variable inside animate
position = Math.floor(gameFrame/staggerFrames) % 6
The above calculation makes sure that position only cycles every 5 frames(?)
Inside animate, set frameX to spriteWidth multiply by position
Remove spriteWidth beside frameX in drawImage 2nd parameter
Initialize spriteAnimations globally and assign an empty array
Initialize animationStates globally and assign an object array to it, filling it with the name of the animation and the number of frames on each row
Loop through animationStates with forEach using states and index as parameters
Initialize frames inside the loop with as an object with locations and assign an empty array
loop through state.frames with a for loop, initializing positionX and assigning the variable assigned to the for loop multiplied by the spriteWidth (i.e j multiplied by spriteWidth);
Do the same for the vertical position(positionY) but using the index parameter instead (i.e index multiplied by spriteHeight)
Push x as positionX and y as positionY as object properties into frames.loc array in the for loop
Create new key value pair at the end of the for loop using empty array spriteAnimations, passing state.name, assigning it to frames variable
console.log(spriteAnimations) at the end of forEach loop to see the calculation of the coordinates
Replace hard coded number in position variable in animate to spriteAnimations[].loc.length
Remove global variables frameX and Y as it is not needed anymore
Initialize frameX and Y inside animate instead
frameY will be assigned to spriteAnimations[].loc[position].y;
Remove source height value (spriteHeight) as frameY calculates it
Fill the remaining names and number of frames inside animationStates if needed
Currently, you need to place hard coded text inside the property you want in spriteAnimations[] in both position and frameY variable
Instead, create global variable playerState and pass it into both [] so you only need to change the global value (i.e spriteAnimations[playerState]...)
Create new div in html below canvas1 with class of controls
Inside the div, create select element with id and name of animations
Create a label element above select with Choose Animation: as text and for attribute of animations
Create an option element within select element with a value of each animation row(i.e idle, jump etc) for each option
Style controls class with position absolute, put it on the front with z-index, and center it with top left transform translate
Change top value in css to a fix value to place it above the animation sprite
Back to js file, move playerState to the top and create a constant variable dropdown, pointing it towards the select element of id animations
Create event listener for dropdown, listen for change event
Use the event object as function and assign playerState to the values that you have created in the html via event target
