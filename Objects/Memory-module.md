# Memory module
Stores a value in its buffer which is output to **`OUT0`**. The value is read from **`IN1`**, and a signal from **`IN0`** sets the buffer value to the value read from **`IN0`**.

- **`OUT0`**: The buffer value
- **`IN0`**: Set, a signal above 0.5 sets the buffer value to the **`IN1`** value.
- **`IN1`**: Input, the value which will be stored in the buffer if **`IN0`** is true.

## User Information
The Memory Module is used to remember a signal value, it essentially works like an [[IF gate]] that remembers the last bit of information it passed through to it's Out. Much like the [[IF gate]] it will pass through the signal from IN1 continuously while (In0 = TRUE, In0 >= 0.50) but when In0 drops below 0.50 the Memory Module will continue to Output the signal strength of the final bit it received to In1 before the transition to FALSE.

They can be used for a wide variety of calculations and to sample a signal with a tick to In0. An example from Hmaiyda's handy [Decimal Tick for zardOz](https://archive.principia-web.se/level/1399)

The device takes a decimal number like .11 and turns it into a number of ticks, .11 = 11 ticks, the module Buffer begins at 0.0 and The Module Out sends to a [[Cmp-e]] (equals target value, .11) checker, then if the value stored in the memory module does not equal the target value, a tick is sent out to your machine and a SUM is taken of .01 and the current value of the Memory Module buffer, that sum is input to the Memory Module and another loop begins. After 11 loops the target value is reached and no more ticks are sent out.

See also level 2191 [Memory Module Basics](https://archive.principia-web.se/level/2191). For more on storable information see the object descriptions for the [[Condenser]] and [[Wrap condenser]]

See the object description of the [[Signal Cable]] for the basics of signaling in Principia. -zardOz