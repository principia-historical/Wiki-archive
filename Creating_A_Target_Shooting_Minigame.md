# Creating a Target Shooting Mini Game
![](https://i.imgur.com/qG4YUr3.png)

In this tutorial you will learn how to create a simple target shooting mini game! You will find the finished example level at the bottom of this page.

## Objects Used in this Tutorial
Before we begin, let's look at an overview of the objects we will use in this tutorial:
* Linear Servo for the moving targets and the shooter
* Power Supply to power the motors
* CT Servo to control the states of the Linear Servos
* SFX Emitter for sound effects
* Pixel to design the game's layout
* Mini transmitter and Receiver for wireless communication
* Mini emitter to shoot Land mine at the targets
* Plastic Beam to color the targets
* Game Manager to increase and decrease the score and finish the game
* Cam Targeter and Cam Zoomer to position the camera
* Sine wave for the target motions
* Impact sensor to detect when a target is hit
* RC Basic for on-screen controls
* Prompt to display a message if the game is lost

## Creating the Game
First, create a new custom level, then go to level properties in the top right corner. Click the World tab, and remove all borders by changing the background to space, then set Gravity X and Y to 0 to prevent the land mines from falling back down midair after using the shooter. Click the Gameplay tab, set the Final score to 10000 and add a checkmark to Disable Zoom and Disable Cam Movement since moving the camera isn't a part of this mini game.

We'll begin by creating a frame for our mini game. We will use colored **pixel** objects for this. Press quickadd ('space' button on PC) and type in **pixel** to add the object to the sandbox. Open up the configuration window for the pixel object to change the color. I'll use red (#FF0000) for this example.

Duplicate the **pixels** and build the bottom frame of the mini game like on the screenshow below. The object at the bottom is a **Linear Servo** which the player will be able to control and where the shooter will be placed. After you've added the **Linear Servo**, adjust the size slider to maximum and attach it between the **pixels**.

![](https://i.imgur.com/K4bJpeE.png)

Now build the rest of the frame with **pixels** and add two more **Linear Servo** motors like on the screenshot below.

![](https://i.imgur.com/8NxacJx.png)

Now we'll create the shooter at the bottom using a **mini emitter**. A **mini emitter** spawns an object when activated. Add it to the level, then rotate it upwards and attach it to the **Linear Servo**. Adjust the Emit velocity to maximum and Emit Interval to about 0,40. You can change these later.

Now add a **Power Supply** and a **CT Servo** to the mini game. The **Power Supply** gives power to the controllers that we're going to use for all the **Linear Servo** motors. Double click and drag to add a cable between the **CT servo** and the **mini emitter** and then a power cable from the **Power Supply** to the **CT Servo** (to the IN0 socket). The **CT Servo** is a controller that allows you to control the precise state or angle of a motor. You can click the information button for a more detailed description and to see what the different sockets do.

![](https://i.imgur.com/SW6BsTK.png)

Now add a **RC Basic** beside the **Power Supply**. Then open up the configuration window for the **RC Basic**. Here we can choose what buttons we will use for the shooter. Pick the long slider for changing the position and the F button for shooting. Make sure the slider's default state is in the middle.

![](https://i.imgur.com/JGD15Y7.png)

Drag a cable from the **RC Basic** to the **CT Servo** controller. For the shooter we will use a wireless connection instead of a cable. Add a **mini transmitter** and a **receiver**. You can click the configuration button to change the frequency used but just leave them as default for this. Attach the **mini transmitter** to the **RC basic** (OUT1) and attach the **receiver** to the **mini emitter**, first click the layer button (or 'X' button if you're on a PC) to put it in layer 2.

We have now two working buttons for the shooter but in order to shoot stuff we first need to select what to shoot. We will use a **land mine** for this tutorial. Some other objects that can be emitted are: Ball, metal ball, corner, land mine, bomb, interactive ball.

So add a **land mine**, click the **mini emitter** and then use the crosshair button to select the **land mine** as its used object. After that you can delete the **land mine**.

You can now click the play button to test the shooter.
To automatically activate the **RC Basic** at start we can use an **RC activator**. Click the target button and select the RC as shown in the screenshot.

![](https://i.imgur.com/VUqdMmB.png)

Now go up and add a **CT Servo** to each **Linear Servo** motor and attach a **sine wave** for each **CT Servo**.
The **sine wave** is an electronic device that outputs a smooth repetitive oscillation. You can connect it to a **Grapher** object to see its pulse in action.
We will use a different frequency HZ for each **sine wave** so that the mini game targets move at different speed. As you can see on the screenshot, the bottom **sine wave** should have a frequency Hz of 0.20, the middle one 0.40, the top 0.60. You can fine tune these later if needed.

![](https://i.imgur.com/xxmiVL0.png)

Attach a power cable from the **Power Supply** to each **CT servo** (to IN0).

Now add 3 **plastic beams**. They should have different sizes, different colors and be attached to each **Linear Servo**.
The first one should be large and easy to hit, the second one a bit smaller and the last one should be smallest and hardest to hit but will give highest score.
Pick any color you like, I'll use White, Orange and Blue. Put them in layer 2 and attach them to the motors.

![](https://i.imgur.com/I8ji74z.png)

If you click the play button you can see that they now move back and forth.

In order to set a different score for each target we need a way to know when the target has been hit. We can use an **impact sensor** for that, just attach one below each **plastic beam**. The **impact sensor** must have the same size as the **plastic beam**. When an object (the **land mine**) collides with the **impact sensor**, a value is sent through OUT0 which will be connected to a **Game Manager** object that adds a specific score from that target.

After you've attached an **impact sensor** to the **plastic beams**, add 3x **SFX Emitters** to the level, one for each target. Open up the configuration window for the **SFX emitters** and change the sound to "Ding" and add a checkmark to "Global sound". These objects will now make a Ding sound every time a target is hit and the score is increased.

![](https://i.imgur.com/pqm5wrw.png)

Add a **Game Manager** object at the bottom of the mini game and we will start connecting these objects.

We will use wireless connections for this. You can use cables if you prefer but then you'll need to add a **Y-splitter** for each **SFX Emitter**. With a wireless connection we don't need that since we'll have two **receivers** for each **mini transmitter**.

Add 3x **Mini Transmitters**, one for each **impact sensor**. Then add 6x **Receivers**. Click the info button on the **Game Manager** to see what sockets you can use. For this example we'll use **IN3** (score +50) for the first target, **IN4** (score +100) for the second target and **IN6** (score +500) for the third target.

You can use the score number as frequency Hz for the transmitters/receivers to easier keep track of the different connections. See screenshot for example.

![](https://i.imgur.com/zW3OqIE.png)

When you attach the **receivers** to the **SFX Emitter**, make sure to use the **IN0** socket.

Now we're almost done. We just need to set the camera to a fixed position in the middle of the screen.
To do that, add a **Cam Targeter** and a **Cam Zoomer**. Click the crosshair button on the **cam targeter** and select an object near the middle. For me it's a **Linear Servo**. If yours is not in the middle, you can add a black pixel in the middle of the screen and use the **cam targeter** on that. Then click the **Cam Zoomer** and increase the zoom slider a bit (click play and see what works best for your level).

![](https://i.imgur.com/UXXsvqv.png)

When the player reaches 10000 score points the level is completed.
We can add some difficulty by adding a timer that will end the game if that score isn't reached within X seconds.

Add a **timer** object and click its configuration button. choose a number you prefer for your level (mine is 60 seconds), leave the tick at 0 and click ok.

To have a popup message after the game has ended we can use a **prompt** object. Just connect it to a **Y-splitter** before it's connected to the **Game Manager**. Also, make sure to use **IN1** on the **Game Manager** (which is the socket for ending the game). Open up the configuration window of the **prompt** object and set whatever message you like.

![](https://i.imgur.com/ZnQYq4P.png)

Congrats! Your target shooting mini game is now finished!

![](https://i.imgur.com/zJiYAN8.png)

## [Example Level](http://archive.principiagame.com/level/5600)
