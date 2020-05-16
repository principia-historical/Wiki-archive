# Building a Vehicle, Part 3: Angled Cannon using the Servo Motor
In this tutorial we will continue to build on our vehicle from the previous tutorials and this time add an angled cannon using a Servo Motor.

First, let's open up the vehicle from part 2. If you didn't save yours, use [this](http://principiagame.com/level/5383) example level. You can also find the finished example level for this part of the tutorial at the bottom of the page.

## Adding a cannon on the Vehicle
We will begin by creating a small "turret" with two planks where the cannon can be placed, then attach a **Servo Motor** to it. A **Servo Motor** has low maxium speed, high torque and is good for precis angle control or abrupt speed control.

![](http://i.imgur.com/Br5vo26.png)

For the cannon we will use a **Mini emitter** that shoots stuff. Add an object that you want to use as ammo, for example **bomb** or **land mine**, then tell the **Mini emitter** to emit that object by clicking the button shown on the screenshot below. After that you can delete the object that was used. Adjust the **Emit Velocity** slider for a more powerful cannon and the **Emit Interval** slider if you want it to shoot faster.

![](http://i.imgur.com/8UTv0On.png)

Now create a simple cannon or a "pipe" with the **Mini Emitter** attached to it. All parts of the cannon, including the emitter, must be added to **layer 2** so it can be attached to the **Servo Motor**.

![](http://i.imgur.com/VBZj1e9.png)

Now attach it to the motor and then add a plank under it that stops the cannon from pointing down towards the vehicle.

![](http://i.imgur.com/osXNaL6.png)

To control the cannon we must connect it to a **CT Servo**. The **CT Servo** is compatible with all kinds of motors but works best when connected to a servo-designed motor. It adjusts the motor's precise angle instead of speed. We will also add another **RC Basic** to the vehicle for extra buttons. So lets add those two objects where there is space, for example behind the brake. You can change the Layer Visibility Mode under the Play button to easier see behind the top layers.

![](http://i.imgur.com/zMxrG7L.png)

Open up the configuration window of the **RC basic** and drag out the two buttons shown in the screenshot. The 'F' button will fire and the large round button will be used to adjust the cannon's position.

![](http://i.imgur.com/z1YVd3Y.png)

Close the configuration window, double click the **RC basic** and connect it to the **CT Servo** from OUT0.

Instead of having a cable hanging from the emitter we can use a **mini transmitter** and a **receiver** for a wireless connection. Add those two objects. If you click the configuration button you can change the used frequency. That is useful when using many different wireless connections on the same level. But we'll just leave them as default for this. Attach the **mini transmitter** to OUT1 of the **RC basic** and the **receiver** to the **mini emitter**. And finally, a power cable from the **Power Supply** must be attached to the **CT Servo**.

Now we have a fully functional cannon!
If you think the cannon moves too slowly you can change it by clicking the **Servo Motor** and then adjust the sliders.

![](http://i.imgur.com/mLUaOAF.png)

Now we'll add a button for switching between the **RC basics**. To do that, we will add two **RC activators** and connect one to each **RC basic** with a cable, then open up the configuration window and drag out a button. For example the down ('S') button placed at the bottom left side. Now click the target button for each **RC Activator** and connect them to the opposite **RC basic**. E.g. the one that has a cable attached to RC 1 should be set so it activates RC 2 when used.

You can also add a **Cam Targeter** to set a fixed camera position, this will prevent the camera from moving every time you switch the controllers. Just click the target button and select an object in the middle of the vehicle.

![](http://i.imgur.com/FdDTD8r.png)

Your vehicle is now finished!

## Example Level
http://principiagame.com/level/5523