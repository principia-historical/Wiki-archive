# cmp-le
Outputs 1 if the **`IN0`** input value is less than or equal to the **`IN1`** input value, otherwise output 0.

Advanced help:
- **`IN0`**: Value A
- **`IN1`**: Value B
- **`OUT0`**: IF (A <= B) THEN 1 ELSE 0

## User Information
The term cmp-le stands for compare-lesser/equal, it will compare the two input values and output 1.0 each bit In0 remains less than or equal to In1.

The cmp-le and it's brothers [[Cmp-e]](equal to) and [[Cmp-l]](less than), are very useful tools to begin making more complex responses to your signal inputs and RC controls. The following simple examples use a 0.40 [[Jumper]] on the In1 socket and a RC slider widget fed to the In0 of the Cmp gate.

* = 40%, ([[Cmp-e]]), when the slider power is exactly 0.40/40% output 1.0 each bit.
* < 40%, ([[Cmp-l]]), Output 1.0 each bit the slider remains under 40%
* <= 40%, (Cmp-le), Output 1.0 each bit the slider less than or equal to 40%
* \> 40%, (Cmp-le Inputs switched), Output 1.0 each bit the slider is above 40%
* \>= 40% ([[Cmp-l]] Inputs Switched), Output 1.0 each bit the slider is greater than or equal to 40%.
* =/= 40%, ([[Cmp-e]] output to [[Inverter]]), Output 1.0 if the slider is not exactly 40%/0.4000.

Here is an example of how to make a "shifting" slider with three outputs to control forward, neutral and reverse on a vehicle.

```
Output the slider widget to a [[Y-splitter]]
YOut0 to cmple 0.35?—Out to [[IF-else]] In1
YOut1 to IF else In0

Ifelse Out0 to Y-splitter
Ifelse Out1 to Reverse "On" Input

Y-Out0 to Ifelse#2 In0
Y-Out1 to cmple 0.65?—Out to Ifelse#2 In1

Ifelse#2 Out0 to Forward "On" control
Ifelse#2 Out1 to no power(neutral) or brakes etc.
```

Now the vehicle shifter slider will activate reverse on the left third, neutral in the middle and forward on the right. On a [[RC MONSTRO]] Out0 set a 0.50 [[Jumper]] on the In8 set-value slot, this will begin the slider at 50%/neutral.

The [[LuaScript]] equivalent of the 40% cmp Gates requires one input to the Lua In0, the signal you want to check. The double == is required for = after "if"

```
In0 = this:read(0)
if In0 == .4 then this:write(0,1)
else this:write(0,0) end
```

For the other operations replace the "==" sign on line two with the needed symbol, <=, >=, < , >, ~=(not equal)

Note: the slider control is not very effective with the [[Cmp-e]] unless you are looking for 1.0 or 0.0.

See the object description for the [[Signal Cable]] for the basics of signaling in Principia. -zardOz