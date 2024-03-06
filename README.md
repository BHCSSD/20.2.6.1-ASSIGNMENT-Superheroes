# 20.2.6.1-ASSIGNMENT-Superheroes
# Data Structures Assignment 3
## Superheroes

In class, you created the start file for this assignment. Scroll down if you need that code.

1. Add one more superhero of your choice to the arrays.   (/1)
2. Set up 1 additional Array that stores the superpowers for the 5 characters in your original Array.  (/2)
   - Superpower Array should store one superpower of your choice for each hero such as:    `superpower[0] = “super strength”`
    -  You can set up the Array and add the contents in any of the ways you choose. 
3. Alter the original code so that the images print horizontally across the screen. (/1)
4. Change the window size and arrange and resize everything so it all fits nicely.  (/1)
      - (You will need to look this up, look into windowWidth, windowHeight from the reference)
5. In the Draw Function, print their names, superpowers and humanity below their pictures.  Alter textSize, color etc. for easy reading. This can be at the bottom or the top (/2)
    - In the end, it should look professional, and clean. Make sure you do not say true or false for the isHuman array. You need to say 'Human' or 'Non-Human'  
    
6. Two of your superheroes have decided they want more modern and cooler names. (/1)
    - When the mouse is clicked, change the names of only the first and last superhero to something better. 
    - You do not need to ask the user for any input and you should not use a new `FOR` loop.  Just hard code a new name so that when you hit play it prints the original name but when you click the mouse, you see the new name. 
      - This should take 2 lines of code such as:  `allHeroes[?] = "something new"`


7. The superhero for hire is currently chosen at random.   (/1)
    - Add a way for the user to choose a hero (mouse, key, other?) to make it **very** clear on the screen how to choose.   ()
    - No one should appear in the hero box until someone is chosen. 


8. Challenge (not for marks) - When the user presses the `‘c’` key, all our heroes have all been exposed to ‘Hobbsinite’ but it only affects those not from Earth.  This means that when the `‘c’` key is pressed, if they are non-human, they lose all their powers.  

  Write a new For Loop that is triggered by the `‘c’` key:
    - It then uses an `IF` statement with the `isHuman` Array
    - If they are not human, it changes their superpower to `“NONE”`.  Note that you simply need to change it with a line such as:  `superpowers[i] = "none"`




## Complete Starter Code
```
let allHeroes = ["Thor", "Ironman", "Superman", "Storm", "Wonder Woman"];
let isHuman = [false, true, false, true, true];
let allPics = [];

let rand;
let angle = 0;


function preload() {
    allPics.push(createImg("", "Thor"  )   );
    allPics.push(createImg("", "Iron Man"  )   );
    allPics.push(createImg("", "Superman"  )   );
    allPics.push(createImg("", "Storm"  )   );
    allPics.push(createImg("", "W.W."  )   );

    for (let i = 0; i < allHeroes.length; i++) {
        allPics[i].hide();
    }

}//end preloading of images

function setup() {
    createCanvas(800, 600);
    rand = floor(  random(0, allHeroes.length)    );
    print(rand);
    angleMode(DEGREES);

}//end setup

function draw() {
    background(200, 200, 80);

    //all pictures
    imageMode(CORNER);
    for( let i=0; i<allPics.length; i++ ){
        image(  allPics[i], 700, i*100+50,  75, 75    );
    }

    fill(255);
    noStroke();
    textSize(20);
    text("Your superhero for hire is: " + allHeroes[rand], 50, 100  );

    //spinning pictures
    imageMode(CENTER);
    translate(250, 250);   //the location of the spinning image
    rotate(angle);
    image( allPics[rand],  0, 0, angle/2, angle/2  );
    resetMatrix();
    if(angle<360){
        angle+=3;
    }
    


}//end draw

function mousePressed() {
    print("MouseX: " + mouseX + "     MouseY: " + mouseY);
}//end mousePressed


```
