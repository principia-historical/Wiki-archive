# Condenser
Stores an internal value of the sum of all previous values read from IN0, minus all previous values read from IN1. The internal value is then divided by the maximum value and written to OUT0 as a fraction.

This object can be used as a "health meter". Use IN1 to decrement the health, and IN0 to increment. Wire OUT0 to a ceil device and whenever the result is 0.0, all health is gone.

## User Information
The Condenser is a critical component, with many uses, it stores an internal value between 0.0 and 20.0 and can be used to store and process signal numbers in it's buffer. Over time it adds signal values from In0 and subtracts signal values from In1 and then continuously outputs the result as a fraction of it's maximum value.

Useful for complex math which can change during gameplay it can be used as a caculator, a fuel tank and an object health meter among other things. It is important to understand that it will add and subtract it's input values 125 times per second. Knowledge of the [[Sparsifier]] is required to use the Condenser in most cases.

**Max Value Slider**

This determines the highest point the Condenser can add up to internally, a max value of 1.0 setting is the most common and simplest to work with as each increment of 0.01 added or subtracted represents 1% of the maximum. Here is a detailed example of a most useful Principia device... the health tracker. These may be used for anything you want to register damage that you can nail a sensor to.

First we set the Condenser for 1.0 or 100 increments of 0.01, this sets our Enemy, Hero or Vehicle at 100 "hit points". The Initial Fraction slider determines the initial % of the maximum value setting the condenser will output, if set at 25% the Enemy will begin the stage with only 25% of it's hitpoints. We set it at 100% 1.0 to begin.

Now we need to register damage, we want a weak shot to do 1 hit point of damage and a critical hit to do 10 points of damage. We have a small [[Impact sensor]] in the Enemy's eye and a several large ones on it's body. The sensors are each wired to a [[Sparsifier]] then the critical hit sensor is wired through a [[sub]](.90) and the body sensors are wired through [[sub]](.99) and all of the subs then get a [[Mini transmitter]] with the same frequency. The [[Receiver]] is placed on the Condenser In1. The sensors will now register damage.

A similar setup can be placed on the Increase In0 socket of the Condenser of you want a way to "heal" your creation, fill your fuel tank or just plain add a number. When the internal value passes the max value or 0.0, it stays there and any input numbers will be subtracted or added from the max value or 0.0 respectively.

Now we set the Condenser output to register when the Enemy is "enraged" and when it dies. Split the Out0 into two with a [[Y-splitter]] one side goes to a [[Ceil]]ing component and then through an [[Inverter]], this will send a continuous 0.0 signal until the Condenser output = 0.0 then it will switch to 1.0 and can be used to active your level complete sequence, explosions or just kill the power on the enemy. The other Condenser feed goes to a [[Cmp-le]] component with a 0.25 [[Jumper]] on In1, this will send a 1.0 to highlight or activate berzerker mode when the Enemy is below 25%.

For a fuel tank, try setting the Max Value to 20.0 or 2000 increments of 0.01, then remove the sparsifiers from the above example, when the decrease Sub(.99) is held down(gas pedal button) it will drain 125 increments per second, making a 16 second fuel tank.

See the object descriptions for the [[Wrap condenser]] and [[Memory module]] for more on storable information.

See the object description for the [[Signal Cable]] for the basics of signaling in Principia. -zardOz