# Creating a Simple Walker
There are many ways to create a walker. In this tutorial you will learn how to create one using sine waves and linear servo motors for moving the legs. If this is your first time using the sandbox, we recommend that you take a look at the [Vehicle tutorials](Building_A_Vehicle_Part_1) first.

## Creating the Walker

First, create a new custom level.

We will begin by creating two legs made of a **plank** and **damper** attached to feets made of **rubber beams**. One leg should be on layer 1 and the other on layer 2. Click the configuration button for the **rubber beams** and set the restitution to 0 and friction to 10, this will make the foot grip better when walking.

![](https://i.imgur.com/ZfubrZ0.png)

Now move the legs beside each other and add two **Linear Servos**. Make them horizontal and attach them to each leg as shown on the screenshot. Add two more Linear Servos, make them vertical and a bit larger, then attach them above the other two motors. These four motors will be used to move the legs. Change to Orthographic View to easier place them in the right position.

![](https://i.imgur.com/pv1Y3Ua.png)

Now create a simple upper body frame using **planks** that connects the motors on the different layers and where we can place all the objects that will be use.

![](https://i.imgur.com/Gn8WUl5.png)

Now add **Power Supply** in the middle and four **CT servos**, one for each motor.

![](https://i.imgur.com/sxkgz1d.png)

Connect the **CT servos** to the **Linear Servos** and to the **Power Supply**. When working with different layers, change the layer visiblity for a better view. Also, you might have to increase the lenght of some of the **Interface cables**. Just detach them to adjust the slider.

![](https://i.imgur.com/OGMHGoT.png)

Now add a **Tiltmeter** in the middle above the **Power Supply** and connect it to two **Thrusters** on the sides. The **Tiltmeter** will output the angular displacement of the tiltmeter relative to its standing position and then activate the **Thruster** that's on the side where the walker tilts towards. This is to make sure the walker doesn't tip over. Leave the thrust as default now, we will fine tune everything later.

![](https://i.imgur.com/smUdR1Z.png)

To make the legs go up and down we will now add two **Sine Waves**. The **Sine wave** is an electronic device that outputs a smooth repetitive oscillation. The phase determines where in the sine wave it begins. Set the frequency Hz to 0.60 on both **sine waves** and set the phase to 0.25 on one of them for now, we can change these later when fine tuning.

Now add two **muladd** objects and connect them to the **sine waves**. Set the multiply slider to 2. This will multiply the sine wave so that when it reaches the end of the Linear Servo it makes a small pause. This will make the walking more stable by stopping the foot when it hits the ground while the other foot is in the air.

You can use a **grapher** to see a demonstration of what happens to the sine wave when multiplying it.

![](https://i.imgur.com/GMPATgu.png)

![](https://i.imgur.com/xNmHhn9.png)

Now we have an up and down motion for the legs. To be able to walk properly we need to add a side to side motion to the two vertical **Linear Servos** above the legs. Add two more **Sine waves** and two **Inverters**. Set the frequency Hz of the **Sine waves** to 0.60 and set the phase to 0.25 and 0.50 for now, then connect them to the **inverters**. That will invert the sine wave and make the walker move to the right.

![](https://i.imgur.com/9mIvPv4.png)

## Fine Tuning

The leg motion is now finished but before the walker can walk properly we need to do some fine tuning.

The values that will be used now depends on the size and weight of your walker. If you have made your walker slightly different than the one in this tutorial you can begin with these values, then test it and make any changes if necessary.

First, click the two vertical **Linear Servos** and change the Speed - Force to 0.40. If you use more force than that the speed will be set to 0 and the walker won't move.

![](https://i.imgur.com/GSgAutC.png)

Click the two horizontal **Linear servos** and increase the Force slightly (0.10).

Click the **Power Supply** and decrase the voltage to 5.00

Click the **Tiltmeter** and increase the sensitivity to 17.00. Set the thrust of the **Thrusters** to 14.00.

The walker should now walk properly and not tip over but to make it even more stable we can use a **Stabilizier** object. Add it somewhere in the middle and increase the angular damping just a bit (~0.20).

![](https://i.imgur.com/3rnRIBs.png)

If the walking still is unstable you can try changing the frequency hz and/or phase slider of the **Sine Waves**. See if something is out of sync. The legs should have a half-circle motion and not move too fast.

Feel free to make any additional upgrades to your walker. For example an upper body, a cannon or add two more legs to make it a four legged walker! If you're happy with it you can publish it and share it with the community!

## [Example Level](https://archive.principia-web.se/level/6585)