# IF-else
If binary value of **`IN1`** is 1.0, out the unmodified value of **`IN0`** to **`OUT0`**, else out it to **`OUT1`**.

Advanced help:

The input IN1 is binary, its value is rounded so any value above 0.5 is equal to 1.
- **`IN0`**: Value
- **`IN1`**: Condition
- **`OUT0`**: IF IN1 THEN IN0 ELSE 0
- **`OUT1`**: IF NOT IN1 THEN IN0 ELSE 0

## User Information
If the binary value of In1 is 1.0, output the unmodified value of In0 to Out1, otherwise output the unmodified value of In0 to Out0. (See [[IF gate]])

Example from http://principiagame.com/level/1331,

We have a simple car and want a button which will override the forward wheel power slider and send it to the rear wheel reverse,

RCOut0 is the power slider control, sent to the In0 on an IF-else gate, RCOut1 is a button which is wired to the In1 on the IF-else gate. Now send Out1 to the rear wheel counter-clockwise [[Simple Motor]] and Out0 to the front wheel clockwise [[Simple Motor]].

Now you have a car with a RC speed slider and an RC button which will kill the speed to the forward wheel and send it to the rear while still maintaining speed control on the slider.

As an equation it would read like this, If (In1 = FALSE) then do this (Send In0 to Out0) otherwise (In1 = TRUE) do this (Send In0 to Out1)

The [[LuaScript]] for the If-else Gate looks like this, all InOut sockets the same on both.

```lua
In0 = this:read(0)
In1 = this:read(1)
if In1 < .5 then this:write(0,In0)
else this:write(1,In0) end
```

Now the Lua is identical to an IF-else gate.

See the object description for the [[Signal Cable]] for the basics of signaling in Principia. -zardOz


Example level: http://principiagame.com/level/2589 -Rasmusollie