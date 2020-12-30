# Adventure Contraptions, Part 1: Doors and traps
On this page you'll find different examples of doors and traps that you can use or modify for your own adventure level. Each example has a list of used objects. Use the quickadd button to add these objects (space button on PC) or drag them from the box on the right side of the screen. To attach cables between objects, double click them and drag.

## Example level with all contraptions included
http://principiagame.com/level/5757

## Doors

### Simple door with button
This door is closed until the player presses a button (see door example 1)

Objects needed:
- Plank
- Linear Motor
- CT Servo
- Power Supply
- Button
- Platform

Begin by increasing the size of the **Linear Motor**, flip it over (marked button on screenshot), then attach it to a **platform** object or wherever you want your door. Attach the **plank** on the **Linear Motor** as shown on the screenshot.
Add a **Power Supply** and a **CT Servo** on top of the **platform**. The **CT servo** is a controller we can use to control the state of the **Linear Motor**.
Attach a cable between the **power supply** and the **CT Servo** and then a cable between the motor and controller.

Now add a **button** somewhere and drag a cable to the **CT Servo** (IN1 socket).

Now when the player presses the button by shooting or touching it the door should open.

![](https://i.imgur.com/EvW8tlX.png)

### Door opened by object
This door is closed until the player uses the builder tool to place an object of specific type over an object field (see door example 2)

Objects used:
- Linear Servo
- Power Supply
- Linear Servo
- CT Servo
- Object field
- Box
- Item (config: builder)

Attach a **Linear Servo** to a platform, increase its size and flip it. Connect it to a **CT Servo** and then connect the **CT Servo** to a **power supply**

Now add an **object field** somewhere. Click it and use the crosshair button to select an object, the box for example. You can put some other objects beside it so that the player is forced to try them out to see which one is correct. Connect the **object field** to the **CT Servo**

Add an **item**, found under "Game" in the inventory panel, then click its configuration button and choose builder. That's an object the player must pick up before he can move the box.

![](https://i.imgur.com/aswC6nI.png)

## Traps

### Hidden spike trap
The player is instantly killed by spikes if he walks under this hidden trap (see trap example 1)

Objects used:
- Linear Motor
- CT Mini
- Object field
- Power Supply
- Spikes
- Pixels
- Plank

Add a **Linear Motor**, increase its size, flip it over and attach it to a platform. Attach 3x **spikes** to a **plank** as shown on the screenshot below, then attach the **plank** to the **Linear Motor**. Connect the **Linear motor** to the **CT Mini** and connect the **CT Mini** to a **power supply**. The **CT mini** is a controller that controls the speed and direction of a motor. It will be set so that the trap is in a reversed state by default and then pushed down when the player walks under it).

Attach an **object field** to the platform and point it downwards, adjust the length to cover the whole trap and the sensor height all the way down to the ground as shown on the screenshot, then connect it to the **CT Mini** (IN2 ~reverse socket). Add 2x maximum sized **Pixels** on layer 2 in front of the trap to cover it. Then one maximum sized **pixel** for each layer below the trap, the one under the trap should be colored red as a warning (layer 1 in this case).

![](https://i.imgur.com/g5kzWRw.png)

![](https://i.imgur.com/Ag2VMUq.png)

### Laser trap
The player must jump between platforms on different layers or he will be killed by laser (see trap example 2).

Objects used:
- Laser x6
- Platforms

Attach **lasers** on the platforms, pointing sideways toward other platforms. These **laser** objects will damage robots if the wavelength is set above 0. Set it to maximum.

Add smaller platforms above the laser beams, one for each layer. The player must jump on these to get past the trap.

![](https://i.imgur.com/b2TVuIc.png)

### Disappearing pixel trap
Certain pixel objects disappears if the player walks or jumps over them (see trap example 3).

Objects used:
- Pixels
- ID field
- Mini transmitters
- Spikes (optional)

Attach a bunch of large **pixels** beside each other. Add platforms above the **pixels** as shown on the screenshot. Add two **ID fields** above two of the **pixels**, adjust the length and height so that the two **pixels** are covered. An **ID field** reports when a specific object is inside the field. To select the player robot as the target, click the crosshair button when an **ID field** is selected and then use it on the robot. Add two **mini transmitters** and click the configuration button to set the used frequency to a random number, 20 for example. Now open the configuration window for the two **pixels** under the ID fields and set the opacity to the same number as the frequency used for the **mini transmitters**.

Attach the **mini transmitters** to the **ID fields** and the trap should work.

If you want this to be a deadly trap you can put **spikes** under it (see screenshot).

![](https://i.imgur.com/edTFwdC.png)

### Shooting trap inactivated by laser beam
This trap shoot land mines until it's inactivated by a controlled laser beam. (see trap example 4)

Objects used:
- Servo Motor
- CT Servo
- Battery
- RC Micro
- Mini emitters
- Land Mine
- Laser
- Laser bouncer
- Laser sensor
- Inverter
- Cylinder
- Y-splitter (if you want to use two shooters)

Attach two **Mini emitters** to platforms and point them downwards. Click the **mini emitter**'s crosshair button to select a **land mine** as the used object. Adjust the interval a bit if you want it to shoot faster.

Attach the **laser** to a small sized **cylinder**, then attach the cylinder to a **Servo Motor**. Add a **CT Servo**, connect it to a **battery (3V)** and then connect the **Servo Motor** to the **CT Servo**.

Add the **RC Micro** somewhere that the player can use. Click the configuration button and drag out a round button. Connect the **RC micro** to the **CT Servo**.

Now place a **laser bouncer** and a **laser sensor** somewhere. The laser beam from the controlled laser should be pointed by the player toward the **laser bouncer** and then bonunced to the **laser sensor**, see screenshot for example. You might need to change the layer.

Now connect the **laser sensor** to an **inverter**. The **inverter** is then connected to the **mini emitters** so that they shoot by default and are inactivated when the **laser sensor** detects a laser beam, but since the **inverter** only have one output socket and we're using two **mini emitters** we will have to first connect it to a **Y-splitter**. An **y-splitter** is an object that forwards the value from its input port to both its output ports.

![](https://i.imgur.com/5y64iWY.png)

Note: when you click the Servo Motor make sure the little square is aligned together with the attached laser and the round button.

![](https://i.imgur.com/ODTpCwl.png)

### Conveyor trap
A simple trap that tries to move the player into a spikey wall (see trap example 5)

Objects used:
- Conveyor
- Jumper
- Spikes

Add the **conveyor** between platforms, rotate it a bit, adjust its size and adjust the speed so that it forces the player to move quickly. Build a wall of spikes as shown on the screenshot. Attach a jumper to the conveyor and it should work. A jumper is plugged into a signal socket to set the signal to a constant value. You can click the configuration button to change the value of a jumper (not needed for this example).

![](https://i.imgur.com/nRbSaXP.png)

### Fan/spike trap
This trap forces the player to use the builder tool to avoid getting thrown into the roof of spikes from when trying to get past the fan system (see trap example 6).

Objects used:
- Fans
- Boxes,
- Item (config: builder),
- Spikes,
- Power Supply,
- Platforms

Build a frame of platforms as shown on the screenshot. Add some boxes and a builder somewhere (configure an **Item** object). Add a **Power Supply**, adjust the voltage to maximum and connect it to a bunch of fans that points toward a roof with **Spikes**. The fans will fling the player into the air so he can get up on the next platform but it should be built so that it's impossible to get past without first attaching the boxes under the spikes using the builder tool.

![](https://i.imgur.com/5RQhWCh.png)

## Part 2
For more examples of contraptions that you can use in your adventure level, see part 2 of this tutorial:

[Adventure Contraptions, Part 2](Adventure_Contraptions_Part_2)