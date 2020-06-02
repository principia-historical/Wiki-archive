# Creating a Transforming Adventure Boss
![](http://i.imgur.com/tO4WXCl.png)

For a beginner boss tutorial, see [this](Creating_A_Simple_Adventure_Boss) tutorial.

In this tutorial you will see some examples on how to create a transforming adventure boss! Since this is a tutorial for more advanced users we'll mostly just go through what objects can be used and assume you already know some of the basics of Principia, e.g how to connect and build simple things. If you're very new to Principia, you should check out some of the [Beginner Tutorials](Tutorials#Beginner_Tutorials) first.

You will find a finished example level at the bottom of this page.

## Phase 1: Destructible Parts (Legs)
The legs used in this example are the same as in the [Simple Walker](Creating_A_Simple_Walker) tutorial but duplicated to make it a four legged boss.

![](http://i.imgur.com/lXQk4Qg.png)

To make the player able to shoot off the legs we can use a **FX emitter** to destroy the connections after x amount of damage and make the legs fall off.

Basic objects used for destructible legs:
* **Impact sensor** - To sense when the leg has been hit
* **Condenser** - To calculate the damage done to the leg
* **FX emitter** -  To destroy connections and make explosions
* **Auto Absorber** - Use with timer to remove the legs some time after being destroyed

Use *Connection Edit* and click a connection you want to make destructible and decrease the strenght slider just a bit (0.95). Add a **FX emitter** somewhere near it and set its config to "Destroy Connections", and "Explosion" if you want explosions when its being destroyed.

![](http://i.imgur.com/pWIeRG5.png)

To activate the FX emitter after a certain emount of damage we can calculate the health of the legs by using an **impact sensor** connected to a **condenser**. See Boss HP below for a more detailed example. Make sure to have a separate HP calculation for the legs.

To delete the legs after they fall off you can connect a **timer** to an **Auto Absorber**. Set the **timer** to e.g 2 seconds and connect it to the **FX emitter** output socket.

## Phase 2: Activate Hovering
To make the boss start hovering over the player after the legs have been destroyed you can use these objects:

* **Toggler** - To activate the rockets and used objects after the legs have been destroyed
* **Rocket**
* **Proximity sensor**
* **Tiltmeter**
* **Gyroscope**
* **Servo Motor** - To change angle of some rockets when the boss is tilting
* **Object finder** - To find the player's angle and hover towards it
* **Stabilizer**

For a more detailed tutorial for basic hovering, see [this hovercraft tutorial](Building_A_Hovercraft).

![](http://i.imgur.com/i8o0d54.png)

The amount of Rockets that you should use depends on the size and weight of the boss.

Here's an example of a setup that will make the boss hover:
* Four pointed down **rockets** (two at each side) that are connected to a **Proximity sensor** at the bottom. The **proximity sensor** senses how far the boss is from the ground and powers the rockets according to that.
* Two **rockets** that are activated by the **tiltmeter** and attached to **Servo Motors** that are connected to a **gyroscope**.
* Four **rockets** that point to left/right and are connected to **proximity sensors** at the sides and/or an **Object Finder** to find the angle of the player. Use together with a **sincos** to convert an angle to positive x/y and negative x/y.
* Some extra **thrusters** if needed to fine tune the stability

Add a **stabilizer** if needed.

## Phase 2: Activate Body Parts (Shooting Arms & Head)
![](http://i.imgur.com/F0J1lzi.png)

To activate new body parts after the legs have been destroyed you can simply hide them behind a body made of e.g **plastic boxes** or **breadboards**, then use **Linear Servos** or **Linear Motors** uncover them when activated.

If you have separated body parts like the head in this tutorial example, you can use **rubber beams** attached to **Linear Servos** to lock them in place.

To make the Arms or other body parts destructible, see the steps for destructible parts.

## Phase 3: Moving Head
In this example: After the body is destroyed the head with two eyes will be dropped on the ground and balance itself on a wheel. For a transformation like this, hide the head or separated body part behind the main body, then when the body is damaged enough, use **Auto Absorber** to remove it and only the separated body part will remain. Use a **Toggler** to activate the objects needed so it doesn't move around inside the boss.

![](http://i.imgur.com/BBz3IHF.png)

![](http://i.imgur.com/eHLJReo.png)

## Boss HP & visible HP bar
Objects needed:
* **Impact sensor**
* **Condenser**
* **Sub**
* **ceil**
* **inverter**

The **condenser** can be used as HP for the boss. A **condenser** has two inputs, IN0 and IN1. IN0 will "fill" the **condenser**. Send 0.1 to it and it increments its internal value by 0.1, for example. IN1 decrements the **condenser**. The output, OUT0, is the percentage of how filled the **condenser** is. If you read 1.0 from OUT0, it means it is full, and 0.0 means it is empty.

You can set the **condenser's** *Initial Fraction* to 1 and *Max Value* to 1. Attach **Impact Sensors** where the boss will take damage. Connect the Impact **Sensors** to a **sub**, set the **sub** to 0.9 for example. Connect the **Sub** to the **condenser**. Now when the **Impact sensors** have been hit a value of 0.10 will be decremented from the **condenser**. Add a **ceil** and **inverter** to only ouput 1 when the condenser (HP) is empty. Then you can connect it to a **Game Manager** to complete the game or a **toggler** to activate some other features on the boss. So when the boss has been hit about 10 times (this might vary a bit depending on the sensitivity used on the impact sensors). If you want it to have more HP, adjust the values used for the **condenser** and/or **sub**.

![](http://i.imgur.com/h4mXO6m.png)

If you want the boss HP to be visible to the player, there are different ways you can do that:

### Using a Grapher
The simpliest way is to connect the **condenser** used for the HP to a **Grapher** and attach it somewhere on the boss.

![](http://i.imgur.com/JzBvFRH.png)

### Using Active Displays
The HP bar we're using for the example level on this page is this one, it uses **Active Displays** lined up together to display the current boss health.

Credits to *that guy* for this method http://principiagame.com/level/4471 You can click edit to see how it's made or copy it with multi-select.

![](http://i.imgur.com/rrBSLIE.png)

### Using a Linear Servo
This method uses a **Linear Servo** and colored **plastic beams** on different layers to create a mechanical HP bar.

![](http://i.imgur.com/9Hnf4FN.png)

You can place it somewhere on the side or on the boss if there is space.

## Other useful tips
* You can use a **Time Ctrl** with a **Timer** for a short slow motion effect when the boss transforms or breaks down.
* Use a **Game Manager** to set score or complete/end game
* **HP Control** can be used to change the player HP. You can use it with an **ID field** to heal the player when walking near it.
* **Emitter** or **Multi-emitter** can be used to spawn mini adds during the boss fight.
* **Event listener** can detect when the player dies and then recharge the boss HP for example.
* **SFX Emitter** can be used for different sound effects.

## Example Level
http://principiagame.com/level/7616