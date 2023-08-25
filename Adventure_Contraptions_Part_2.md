# Adventure Contraptions, Part 2: Elevators, moving platforms, laser puzzle and more
In this part of the adventure tutorial you will learn how to create an elevator, moving platforms, laser puzzle and more.

## [Example level with all contraptions included](https://archive.principia-web.se/level/6025)


![](https://i.imgur.com/wf8JAHv.png)

## Simple elevator 1
![](https://i.imgur.com/KsuovNs.png)

Objects used:
- Linear Servo
- CT Servo
- Power Supply
- Sparsifier
- Condenser
- Inverter
- RC Basic
- Plastic beams
- Platforms

Build a frame for the elevator using plastic beams. Attach it to one of the linear servos, then attach that linear servo to the other linear servo.

When the player uses one of the RC buttons a signal is sent through a sparsifier, then to a condenser, and finally to an inverter. A condenser stores an internal value of the sum of all previous values read from IN0, minus all previous values read from IN1.
The internal value is then divided by the maximum value and written to OUT0 as a fraction.

![](https://i.imgur.com/0bDvlo1.png)

## Simple elevator 2
![](https://i.imgur.com/1EDS7Zk.png)

This elevator uses thrusters instead of a motor. The thrusters are activated when a player enters the elevator and is seen by an object field on layer 2. If he switches layer the thrusters will stop and the elevator will go down. The stabilizer keeps the elevator from wobbling or falling too fast.

Objects used:
- Thrusters
- Object field
- Stabilizer
- Mini Transmitter
- Receivers
- Wheels
- Plastic beams

## Moving platforms
![](https://i.imgur.com/dErVzQs.png)

Objects used:
- Linear Servo
- CT Servo
- Power Supply
- Sine wave
- Plastic beams

Attach sine waves to each CT servos with different frequency, but make sure they sync properly so the player can jump between them.

## Ropeway
![](https://i.imgur.com/k9IoU6A.png)

Objects used:
- Ropes
- Cylinder
- Planks
- Platforms

Attach a bunch of ropes together, build a small "basket" for the player to sit in and make it able to roll by using a cylinder above the ropes.

Optional objects (for unlock button):
- Toggle Button
- Linear Motor
- CT Mini
- Power Supply

![](https://i.imgur.com/PnzCtut.png)

## Fading pixels
Objects used:
- Pixels
- Broadcaster
- Sine Wave

Use the configuration button for the pixels and change the "opacity" number. That is the frequency the broadcasters will use. You can set the two broadcasters to broadcast to every other pixel and use a sine wave for each broadcaster with different frequency to make the pixels pulse at different speed (see example level).

![](https://i.imgur.com/3ZoyOD9.png)