# Building a hovercraft
In this tutorial you will learn how to build a basic hovercraft. If this is your first time using the sandbox editor we recommend that you check out the vehicle tutorials before this one.

For a finished example level of the hovercraft, see the bottom of this page.

For help for how to use the user interface, [click here](User_Interface).

## Hovercraft
First, create a new custom level.

Add a **plastic beam**, click the configuration button to choose whatever color you like. Then attach two **Servo Motors** at both ends of the **plastic beam**.

![](https://i.imgur.com/7xOcOmI.png)

Now add a **Thruster** attached to each motor and a **Tiltmeter** in the middle of the **plastic beam**. The **Tiltmeter** outputs the angular displacement relative to its standing position. This will be used together with a gyroscope to prevent the hovercraft from falling over to the sides. Add a cable from OUT1 to the left **thruster** and from OUT2 to the right one.

You can change to Orthographic Mode (under play button) to easier see where you place your objects.

![](https://i.imgur.com/KwB6vDQ.png)

When you click the motors its important that the purple line with a square is aligned together with the **thrusters**.

![](https://i.imgur.com/mydaF7c.png)

To keep the hovercraft above the ground we will add a **Proximity Sensor** and two **thrusters** below the **plastic beam**. The **proximity sensor** meassures the distance to the closest object and activates the **thrusters** when its near the ground. You can increase the Lenght slider a bit to make it hover higher above the ground.

Instead of cables we will use a wireless connection by adding a **mini transmitter** on the **proximity sensor** and two **receivers**, one on each **thruster**. You can leave the frequency as default.

![](https://i.imgur.com/95ynZKg.png)

Now add a **Power Supply**, two **CT servos** for the motors and a **RC basic** for buttons so we can control the hovercraft.

![](https://i.imgur.com/cUlmyso.png)

Click the configuration button for the **RC basic** and drag out a button for left, right and up.

![](https://i.imgur.com/fiH2pFx.png)

Now add two **thrusters** for the up button, one for left and one for right. Then add a **mini transmitter** with different frequency for each button on the RC basic. Add a **receiver** with the same frequency as the **mini transmitter** for that specific button and then attach them to the **thrusters**.

![](https://i.imgur.com/P4r5oKa.png)

Now it's time to add the **Gyroscope**. This object continuously signals the absolute angle of the gyroscope a value from 0 to 1 where the output value
is A/360 where A is the absolute angle in degrees. Together with an **inverter** object this will make the two **thrusters** on the motors always point down and keep the hovercraft balanced and stable.

Connect the **Gyroscope** to the **inverter** and then use a **Y-splitter** object to connect the **inverter** to both **CT servos**. Then connect the **Power Supply** to both **CT servos**, and finally connect the **CT servos** to the **Servo motors**.

![](https://i.imgur.com/wtdKCh5.png)

To stop the hovercraft from wobbling we can use a **stabilizer** object. This object is useful when you have a group of objects that need some sort of stabilization. You can adjust the sliders for how much stabilization is needed. No more than 0.05 should be needed for this hovercraft.

Now add a **RC activator** to the hovercraft so the RC is automatically activated at start. Click the **RC activator**, then the target button and select the **RC basic**.

![](https://i.imgur.com/LPyj3EV.png)

Now the last thing we need to do is increase the thrust of all the **thrusters**. I use maximum for mine, see what works best for your hovercraft. It depends on the weight and size of the hovercraft. If needed you can add more **thrusters** or even replace some of them with **rockets** which are much more powerful.

Congrats! You have now built a working hovercraft.

![](https://i.imgur.com/tLL8MSJ.png)

## Example level
https://archive.principia-web.se/level/6109