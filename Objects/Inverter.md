# Inverter
Inverts **`IN0`** and writes it to **`OUT0`**. If the input signal is raw, `1-**IN0**` is written to **`OUT0`**.

## User Information
Easily one of the most important and useful components, the Inverter will take your signal input to In0 and then reverse it by subtracting it from 1.0...

```
1.0 signal sent to In0 becomes 0.0,
0.65 signal sent to In0 becomes 0.35
0.50 signal sent to In0 stays unchanged at 0.50
```

Another way to think of it is that it outputs the opposite of the signal distance from 0.50, it's always helpful to think of how things operate in multiple ways.

Most of the time you will be inverting a 0.0 signal to a 1.0 or inverting a 1.0 to 0.0, but they are useful for many, many situations...

Examples:

1. Send the RC power slider through an Inverter and then on to a motor and the slider will now register full power on the left and zero on the right, opposite of the normal configuration.

2. A [[Laser]] wired to a [[Button]] needs the [[Button]] to be pressed to turn on, if inverted it will start on and stay on until the [[Button]] is pressed.

See the object description of the [[Signal Cable]] for the basics of signaling in Principia.

### Tutorials
"Or, AND, XOR, NAND, Inverter"

http://principiagame.com/level/638 -mrsimb

"Basic Parts Tutorial #6: Inverter +(Y-split, L-Motor)"

http://principiagame.com/level/790

"Basic Parts Tutorial #7: Transmitter/Receiver"

http://principiagame.com/level/792