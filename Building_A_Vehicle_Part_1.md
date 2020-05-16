# Building a Vehicle, Part 1: CT Mini for Forward and Reverse
In this tutorial you will learn how to build a simple vehicle using a CT mini for Forward and Reverse. An example level is added at the bottom of the page.

First, open Principia and create a new custom level.

## Building the vehicle
We will begin by adding a **DC motor** attached to a **plank**, which will be the base of our vehicle. You can drag the objects from the window on the right side of the screen (under the Basics and Robotics categories in this case), or you can use [quickadd](User_Interface#Quickadd_Button) and type in the object name.

![](http://i.imgur.com/DSZmXJr.png)

The **DC Motor** is powered by being connected to a controller (CT), so lets add that. Press quickadd and type in **CT Mini**.

This controller controls the speed and direction of a motor. You can attach it to the middle of the plank or wherever you like.

Now we will have to add an interface cable between the **DC Motor** and **CT Mini** so that they can communicate. To do that, simply double click the **CT mini**, drag the mouse to the motor and release.

![](http://i.imgur.com/xqMyxBM.png)

Now let's add two wheels to the vehicle. Press space and type in **wheel** or drag it from the Mechanics category. Before we can attach the wheels we need to move them to layer 2. To do that, click the layer button on the bottom of the screen or press the 'X' button on your keyboard if you're on a PC. Also, when you attach the wheel to the plank you need to make it able to rotate (see screenshot).

![](http://i.imgur.com/XGq0Ib0.png)

Now we need to add a power source to our vehicle. For this tutorial we will use a **Battery (3V)** but you can also use a **Power Supply (24V)** for greater speed or more advanced creations. Press space and type in **Battery** and attach it to the **plank**. Double click it and drag to add a power cable between the **CT Mini** and **Battery (3V)**.

![](http://i.imgur.com/W7zyept.png)

To control the vehicle we will need to add a control panel. Press space and type in **RC basic**. Place it above the CT mini or wherever you like and then click the configuration button.

![](http://i.imgur.com/K79aCsH.png)

![](http://i.imgur.com/7h8WuJq.png)

Here we can add widgets and buttons to control our vehicle which will appear on the screen later when we start the level and click on the RC. Each widget will be connected to an output socket, the first widget you place will be connected to OUT0, the second to OUT1, and so on. In this example we will use the buttons shown in the screenshot. The slider button will adjust the speed of the vehicle and the small button with an 'F' will put the motor in reverse. But first we need to add signal cables between the **CT Mini** and **RC Basic** connected to the correct output socket. Double click the **CT Mini**, drag it to the RC and then click OUT0 and then IN1 (this is for the speed adjustment button as you can see on the screenshot). Now a cable for reverse mode. Double click the CT again, drag it to the RC and click OUT1.

![](http://i.imgur.com/PNzhagg.png)

Congrats! You have now built a working vehicle. Click the play button (or 'P') to test it. Adjust the speed with the bar we added to the left and hold F to put it in reverse mode.

## Example level
http://principiagame.com/level/5356

## Part 2
In the next part of this tutorial you will learn how to add brakes to your vehicle using a Linear Motor

[Building A Vehicle, Part 2](Building_A_Vehicle_Part_2)

Ctjet99 (ctjet in principia) also has a level that showcases and explains both of these https://youtube.com/watch?v=45T1w04xsfU