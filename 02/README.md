Lesson 2
========

Prerequistes
-----

* Projector
* Instructor laptop
* Laptops for the students

Goals
-----

* Show students that they have the ability to tell the computer exactly what to do
* Show that the computer is only as smart as the person who is programming
* Start off creating a sequence of actions that makes a character on the screen move
* Added an event so that the character reacts to the user's input

Introduction
-----

Today we are going to be making game with Scratch. We may not be able to finish the game today, but we will continue to add on to it as time allows. We will be creating a goalie shoot out game. Where your character will be at the bottom of the screen and you are trying to shoot a goal at the top of the screen. However, it won't be that easy because there is also going to be a goalie that is trying to stop you.

Before we can make a game, we need to learn some basics.

Creating a Project
-------

The following is going to be done on your computer as well as the students. There should be a projector in the room that you can use to show what's on your screen. You will be doing the following.

1. Click on the Chrome browser (we had problems with the laptops needing Adobe Flash otherwise.)
2. Go to http://scratch.mit.edu/
3. Log into your account, if you don't have make one. (If this ends up being the kid's first time here, have one of the mentors walk them through signing up for an account).
4. On the top of the page there is a tab called "Create" click that. This will bring up a new project.
5. Go ahead and give the project a name, you choose which name (suggestion "Super Awesome Soccer Shootout 2014")
6. Then save the game, so that we can keep this project by going to File -> Save Now

Introduction to the tool
--------

Last week (unpublished 1st lesson, which is recapped here), we signed up for Scratch and we starting messing around with it by throwing blocks all willy nilly into the grey box and making this cat do something. For instance, we did something like this (have them copy what you are doing):

1. Drag out the `move 10 steps` block into the grey area
2. Click on the block. This should move the cat a few spaces. But this was boring right?
3. Click on the white area and change the 10 steps to 200. Cat should move to the edge of the screen
4. Click it one more time, "Oh no, now our cat is off the screen!"

The Grid
--------

How do we get our cat back into the middle of the screen?

Here you'll be asking students to try and get the cat back. Ask for suggestions and try it on your screen.

Some of the solutions:

* `move -200 steps`
* `turn clockwise 180` + `move 200 steps`
* `go to x:0 y:0`
* `set x to 0` + `set y to 0`

etc.

So you can't see it, but the area is really a grid. This is just a way that the computer knows where to put different images at. A lot of different computer technologies uses this system to position things. Say I want to add a red block to webpage (`⌥``⌘``j` to open the javascript console):

```js
$("body").append($("<div style='position:absolute; width: 100px; height: 100px; top: 100px; left: 100px; background-color:red;' id='test'>&nbsp;</div>"));
```

Will make a red block on the screen on the webpage.

```js
$('#test1').remove();  // To remove it once, done showing the kids.
````

Grids are everywhere. So this canvas is a grid. If you move your mouse around in the stage and you can see at the bottom where your mouse is. So check it out!

The max size of the canvas (at least for our purposes) is 480 px wide x 360 px high. So cut everything in half and that is the where the corners our. Do the following to touch the four corners:

1. top right: `got to x: 240 y: 180`
2. top left: `got to x: -240 y: 180`
3. bottom right: `got to x: 240 y: -180`
4: bottom left: `got to x: -240 y: -180`

This will become important for our game because we need to know where to place things.

Let's create our game
------

First thing is first, let's get our character back to the middle of the screen. (`got to x: 0 y:0`). This white space is kind of boring right? Let's pick something interesting.

1. Click on the "Stage" at the bottom left of the screen next to the sprint
2. Click now on "Backdrops" tab
3. Click on "image" icon looking thing (the left most icon under "New Backdrop:" text)

Although we are doing a soccer shoot out, feel free to pick any background you want. Let them pick a background, choose a silly background yourself.

Sprites
-------

OK, now that we got our background, this cat looks silly right? Let's get rid of him.

1. Right click on the cat
2. Select "delete"

Now, we need something new:

1. Click on the "troll" looking icon next to the "New Sprite:" text. This will open up a panel that will show them all of the different sprites.
2. Look around and select a different sprite. Allow them time to also find a character that they want to use. Just make sure that they are kind of small, as to not take up a lot of room.
3. Select a sprite and click on the "Costumes" tab.
4. If he is too big, you may want to resize the Sprite, click on the Sprite and resizing options appear. Change it to the size that you want.
5. There is also a "Custom Center" button at the top right of the Costume tab that you can use to set the center of the sprite. Use this to do that.
5. Note the height of the Sprite.

Ok, so we want to move our character to the bottom of stage because he is going to kick the ball to the top of the screen.

There are a number of different ways to do this. Firstly, you can move the sprite manually and as it updates "Motion" blocks. Move your sprite to the bottom of the stage. You can also use math to determine this.

Formula for the position:

.5 * (height_of_sprite) - 180

Once, you position your sprite there, move the `go to x:0 y:<x>` into the gray area to save that position for later.

Controls
-------

Now, so we have a background and our characters. However, he doesn't do anything. This is boring. So, let's make him move right when we click on the right arrow key.

1. In the scripts tab, click on "Events"
2. Drag the `when space key pressed` block into the gray area.
3. Click on the drop down arrow and select "right arrow"
4. Now click on "Motion"
5. Drag the `move 10 steps` block and connect it to the `when right arrow key pressed` block.

In Scratch we can connect blocks together and make one unit. As soon as you connect the block, press the "right arrow" key on your computer. Your character is moving now. Keep pressing the right arrow key.

Oh no, so we got the character to move right. Can you make them move left now? (Have the kids try this on their own.)

Solution:

`when left arrow key pressed`
`move -10 steps` (instead of moves you can also do change `change x by <>`)

Costumes (Animation)
--------

So, that's fun we are able to get him to move left and right, but who walks backwards like that? How do we get him to turn around and walk the direction that he is going? Field questions and try some of their answers if they are doing things like using the `turn *` command. Also if you are using the `move <x> steps` command, you'll notice that the character moves the way he is rotated. This may be a good way to get them to think about using `change x by <x>` instead of `move...`.

Onces they show that that rotation is not going to work. Talk to them about needing to do a mirror flip of the image. Do the following:

1. Go to the costumes tab
2. Right click on the sprite
3. Click on "duplicate", this will create another costume using the same image
4. Click on the "flip left-right" icon at the top right
5. Name the costume something useful like 'sprite-left' (name other sprite "sprite-right" or something)

Ok, now we just create our sprite looking the other way. But how do we get him to turn around? Do some discussion and see if they can figure it out?

Solution:

`switch costume to <sprite-left>` after the `when left arrow pressed`
`switch costume to <sprite-right>` after the `when right arrow pressed`

So, not that we figured that out. Look at him go! We just discovered how to do animations. When you look at a video, flip book, etc, they are just images that are changing really fast that you can't detect with your eye. The same thing here. You are just switching costumes and it gives the illusion that he is turning around, again, we can also make it a smoother animation by adding more images during the turn.

Extra Time
---------

If extra time allows, can do one of the following:

1. Add a ball to the graphics, this may be a little complicated because now we have to do more math and add states and stuff to the ball. Will need to go over variables and how to use if statements to change the position of the ball, so that it is at the feet of the sprite and going the same direction.
2. Go "file" > "Save as a copy", and allow them to explore some with what we just created. Have them add sounds or change up sprites, or make the character move faster.

