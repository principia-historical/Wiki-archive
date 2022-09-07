# Building a Vehicle, Part 2: Adding brakes using a Linear Motor
In this tutorial we will upgrade our vehicle to add a brake using a Linear Motor.

Lets begin by opening up our vehicle from Part 1 of this tutorial. If you didn't save yours, you can use [this](http://archive.principiagame.com/level/5356) example level. You can also find the finished example level for this part of the tutorial at the bottom of the page.

## Adding brakes to the vehicle
First lets increase the length of our vehicle a bit so we have more room for new objects. We can do this by adding another **plank** to the base of the vehicle. First detach the left **wheel** and **DC motor**. Then use quickadd ('space' button on the PC version) to add a new **plank** and attach it beside the other plank. Reduce the size of it a bit using the slider (see screenshot).

![](https://i.imgur.com/JCmSCBF.png)

Now attach the **DC motor** on the plank again, and then the **wheel**.

*Tip: If you hold shift (PC) while rotating or moving an object it will snap itself to a grid.*

For this new upgrade we will need a stronger power source so lets switch out the **Battery (3V)** for a **Power Supply (24V)** instead. Click on the battery and delete, then add a **Power Supply** in its place. With the **Power Supply** you can increase the maximum speed of the vehicle by clicking on it and adjusting the voltage slider.

![](https://i.imgur.com/4UjwSp9.png)

Now we're ready to add a brake. For this tutorial we're going to use a **Linear Motor** with a **Rubber Beam** attached to it as our brake. The **Linear Motor** is connected to a controller (CT) and when it's used it will move its pivot (where the **Rubber Beam** is attached) to the target end of the motor, in this case towards the back wheel. The **Rubber Beam** will then bump into the **wheel** and cause the vehicle to stop.

So add a **Linear Motor** and **Rubber Beam** to the level and then reduce the size of them both to smallest so the brake don't take up too much space.
Also, we're going to switch over the Motor so it stands up like this:

![](https://i.imgur.com/trJmFrL.png)

Now we'll add a small plank on layer 2 of the vehicle to put the brake on. It's best if you rotate the plank a little bit before you attach it so that the Rubber Beam points directly toward the wheel, like on the screenshot. Switch the layer of the **Linear Motor** and then attach it to the small plank.

![](https://i.imgur.com/GNEku6n.png)

You can increase the force of the brake by clicking the **Linear Motor** and adjusting the slider, but be careful that you don't set it to maximum force or it won't move when used (0 speed).

![](https://i.imgur.com/YYUMVQU.png)

Now we need a controller for the brake to work so lets add another **CT Mini** to the vehicle. Double click the **CT Mini** to drag an interface cable to the **Linear Motor**. Then double click the **Power Supply** to add a power cable to the **CT Mini**.

![](https://i.imgur.com/59Q31uh.png)

Now there's only one thing left to do: Add a button to control the brake. To do that, click the configuration button of the **RC Basic** to open up the same window as in the previous tutorial. Then drag out a button for the break as shown in the screenshot.

![](https://i.imgur.com/gsxsNvU.png)

Then double click the **RC Basic** to drag a signal cable to the **CT Mini**, choose IN2 (~reverse) as the input socket and OUT2 as the output socket. This will put the motor's pivot in its activated state by default when not used, so that the brake (Rubber Beam) is automatically reversed after being used.

![](https://i.imgur.com/QyUz784.png)

The part 2 of this vehicle is now finished! Click play and then activate the RC to try it out.

## [Example Level](http://archive.principiagame.com/level/5383)

## Part 3
In part 3 of this tutorial you will learn how to build a cannon for your vehicle.

[Building a Vehicle, Part 3](Building_A_Vehicle_Part_3)