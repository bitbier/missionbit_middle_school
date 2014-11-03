Roblox
========

Checkin
------

1. Who did halloween this weekend?
2. What did you go as?

Activity
------

Today, we are continuing with what we are normally doing. If you have a project in Scratch, continue that. If you are working on a website please continue that. For those who are doing Robloxs, we are going to do a lesson to try and show you some cool stuff that you may not know about.

### Scripting

Today we are going to discuss a few things about scripting. In Roblox, you can create complicated games and interactions. Most of this stuff you can do normally with just the blocks that you put down. For instance, you can create a door and when you walk to it, you can open it normally.

In order to create complicated interactions in Roblox, we'll need to do scripting. Roblox has a simple lightweight scripting language that you can use to manipulate objects. Everything that you see in Roblox is an object and thus you can modify those properties with scripts.

Unlike Scratch to create these interactions, you'll need to write down the program and learn some syntax. Don't worry we will walk you through a script.

The first thing we are going to do is a secret wall!

1. Open up Rolbox studio
2. Click on the "Baseplate" template for the game.
3. Now you should see the overworld of your level
4. Insert a part to the world
5. You can change this part to be any color or material that you would like
6. Increase the size of the block to make it wall size
7. Once you got the size correct, then make a copy of the wall and add it to the left and right of the first wall to make a group of 3.
8. Now test play the game. Check out the wall. It's solid right, you can't pass through it at all.

Now, Let's make the middle wall a secret wall, so that we can pass through it. We will be using scripts to so this.

1. Click on "Reset" to get out of testing.
2. If you don't already have the "Explorer" window and the "Properties" windows on the editor, open them up. By click on "View" -> "Explorer" and "View" -> "Properties".
3. The explorer tab shows everything about the current environment. Notice the hierarchy under "Workspace"
4. Rename the middle wall "SecretWall", this way it is easier to understand what is going on.
5. When, we select the "SecretWall", we will see the properties of the object. Here you can edit a lot of different things. You can change the color, the transparency, etc. There is also a behavior that we care about called "CanCollide". This option is used to determine what happens when other objects hit it. If it is collidable, then things will get stopped the moment you hit them. We need to disable this to be able to walk through it.

While, we can do this in the properties, we are going to do this in code for now.

In order to add code/scripts to the game, we need to insert a script object.

1. Right click the "SecretWall" object in the explorer and go to "Insert Object" -> "Script". This will insert the script object to the SecretWall object. This is how you can attach scripts to just about any objects. A script file should appear with the following code:

    print 'Hello world!'

Delete this code as we do not need it. Instead we will be putting in the following code:

    function onTouched(hit)
        script.Parent.CanCollide = false
        wait(3)
        script.Parent.CanCollide = true
    end

    script.Parent.Touched:connect(onTouched)

There is a lot of stuff that is new happening here that I will try to explain. Don't worry if you don't understand right away. We will get more practice and get this going.

The first thing is that we are defining a "function". Functions are a way of grouping together code in one place, so that you don't have to repeat it. It also helps with keeping code clean and easy to understand. When you look at this function being called, you can say "oh, this does something that happens when it is touched." "Hit" is a little weird and not used here but this is the object that is touching the parent. We are not doing anything, but we could later.

The next line "script.Parent.CanCollide = false" does a number of things. First, notice how the Explorer view everything is in this tree. Notice, how script is underneath "SecretWall"? In coding we think of things in these higher places on the list as being "Parents" and the things underneath it as being "Children". So, "script" is the current script that is being run has an attribute called "Parent" which points to the object. We also could go from the top and instead say "game.Workspace.SecretWall" instead of "script.Parent".

"CanCollide" is that property that I told you about that enabled things to stop when they hit other objects. So, we want to disable it. We can do this by setting something to "false".

"wait(3)" does exactly what is looks like it does. It waits 3 seconds.

After waiting 3 seconds, we can then change the CanCollide back to "true". Just so that we have this change. But if this wall is always collideable then we probably don't care, but will do it anyways.

"end" is a special word used in this programming language. It is used to tell the computer when a function or special operator is finished.

The last line "script.Parent.Touched:connect(onTouched)" the meat of this. When this script runs, it grabs the Parent which is the "SecretWall" and then accesses this special property on the object called an "event". This event is aptly named "Touched". So, everytime something touches this wall, the "Touched" event is fired. The ":connect(onTouched)" is us connecting the function we wrote so that when "Touched" event is fired, it will call our special method.

Now, let's save and go into the world.

Test play the world. Now you can interact with the wall. Notice that the other walls are solid, but that you can go through the wall in the middle without any resistence.

That's an introduction to scripting in Roblox. Can you make the wall turn invisible and then reappear?


Checkout
------

1. Is there anything that was tough?
2. Do you enjoy the excerises?

Free Time
-----

At 5pm allow free time.


Resources
-----


