# graphics-project
Sarabjeet Kumar
Snake Game works on grid basis 
number of columns and number of rows 
and used queue data structure "FIRST IN FIRST OUT ".
In the canvas where is snake is denoted by 1
Where is food is denoted by 2
Where is empty place is denoted by 0

#setting the food for a snake 

Setting the food for a snake is denoted by setFood method 

# function setFood(){
                
                //create a empty array 
                var array = [] ;
                
                //loop throgh the grid and check the empty place in the grid
                //to loop through the grid we need a loop and some variables to check.
                for(var x =0;x<grid.width;x++){
                    for(var y =0 ;y<grid.height;y++){
                    //checks where is empty place 
                        if(grid.get(x,y) === EMPTY)
                        
                        And Math.Random () to select the sandom number and * by empty array to get random place on the grid.
                        
                        
#In the main fuction just create the canvas 
   function main(){
    
                //create the canvas 
                canvas = document.createElement("canvas");
                canvas.width = COLS*20;
                canvas.height = ROWS*20;
                ctx = canvas.getContext("2d");
                //canvas element added to the body
                document.body.appendChild(canvas);
                ctx.font = "12px Helvetica";
                frames = 0;
                keystate = {}; //empty object
                
                	// sets an base font for bigger score display
	                ctx.font = "12px Helvetica";
                
                // keeps track of the keybourd input
                document.addEventListener("keydown", function(evt) {
                    keystate[evt.keyCode] = true;
give it a rows and columns 
and add the event listner to keeptrack on which key is been pressed .on the 

after that init()

 #function init() {
                score = 0;
                grid.init(EMPTY, COLS, ROWS);
                var snakePosition = {x:Math.floor(COLS/2), y:ROWS-1};
                snake.init(DOWN, snakePosition.x, snakePosition.y)
just start position of snake represents by snake snakePosition on the grid and used math.fool(col/2) so 
we can add both odd and even numbers.

#Then there is update function
  //update function 
            function update(){
                frames++;
                
                //***************************************
                //accorrding to the key which is pressed . 
                //***************************************
                
                    switch(keystate){  
                            
                        case KEY_LEFT: 
                          if (snake.direction !== RIGHT) {
                           snake.direction = LEFT;
                          }
                          break;

                        case KEY_RIGHT:
                          if (snake.direction !== LEFT) {
                          snake.direction = RIGHT;
                          }
                          break;

                        case KEY_UP:
                          if (snake.direction !== DOWN) {
                          snake.direction = UP;
                          }
                          break;
In this function switch statement figure out the direction of the snake according to
the key pressed on the keyboard . Like if pressed the left arrow key and 
 if (snake.direction !== RIGHT) 
 snake.direction = left .
 
 if (snake.direction === UP) { 
                        snakeY--;
                    }
                    else if (snake.direction === LEFT) { 
                       snakeX--; 
                    }
                    else if (snake.direction === RIGHT) { 
                       snakeX++; 
                    } 
                    else if(snake.direction === DOWN) { 
                        snakeY++; 
                    }
  getting the direction of the snake where it is in the grid.
  
  
  
#collisions 
//check the collisions 
                    if (0 > snakeX || snakeX > grid.width-1  || 0 > snakeY || snakeY > grid.height-1 ) {
                        //calls the init function
			           return init();
		            }
		            
		  This part of the game isnt working fine because of that my whole game isnt working fine 
		  i was trying to fix it but could't do.
		  
#draw function
		   
            function draw(){
                //calculate the width and height of the cell
                var cellW = canvas.width/grid.width;
                var cellH = canvas.height/grid.height;
                
                //give all those cell a colour 
                //first loop over the grid 
                //need 2 for loops for looping over the grid
                
                for(var x=0;x<grid.width;x++){
                    for(var y = 0;y<grid.height;y++){
                        // sets the fillstyle depending on the id of
                        //Means If == SNAKE then colour 
                        //if == FOOD give it a diifrent colour 
                        //if == EMPTY give it a diffrent colour
                        //we need some if conditions to do that 
                        //some ctx.fillRect
                        if(grid.get(x, y) === EMPTY){
                           ctx.fillStyle = "#0ff"; 
                        }
		                
                        else if(grid.get(x, y) === SNAKE){
                           ctx.fillStyle = "#000"; 
                        }
		
                        else if(grid.get(x, y)=== FOOD){
                           ctx.fillStyle = "#0f0"; 
                        }
		tracking the position which id denoted by SNKAE EMPTY and FOOD 
		If on the grid there is empty place which is denoted bt 0 give it a colour 
		    if(grid.get(x, y) === EMPTY){
                           ctx.fillStyle = "#0ff"; 
                           
  if it is denoted by 2 so its food for a snake and give it a diffrent colour .
  else if(grid.get(x, y)=== FOOD){
                           ctx.fillStyle = "#0f0"; 
  if it is denoted by 1 so its the position of the snake give it a diffrent colour.
else if(grid.get(x, y) === SNAKE){
                           ctx.fillStyle = "#000"; 
                        }
Last call the main method.
  
