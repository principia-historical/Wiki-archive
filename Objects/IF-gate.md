# IF gate
If binary value of **`IN1`** is 1.0, out the unmodified value of **`IN0`** to **`OUT0`**.

## User Information
If the binary value of In1 is 1.0 output the unmodified value of In0 to Out0. (See [[IF-else]] Gates)

The IF gate works in a similar way to the IF command in many programming languages, it can be helpful to think in terms of an equation when wiring If gates, [[IF-else]] gates and Cmp gates. We'll use the following simple If gate configuation for example.

We have a simple car with it's speed controlled from an RC Out0 power slider widget. Split the signal from RC Out0 through a[[Y-splitter]], one side goes to the power control the other is connected to an IF gate In1 socket and a 0.15 [[Jumper]] is placed on the In0 socket of the IF gate. Lastly, wire the IF gate Out0 to a [[Rocket]] on the car. Now when the vehicle's speed slider is above 50%, the afterburner rocket will activate with 15% power.

As an equation it would look like
`If (In1 = FALSE) then do this (Send 0.0 to Out0) otherwise (In1 = TRUE) do this (Send In0 to Out0)`

This [[LuaScript]] will function identically to the If Gate+Jumper but with the In1 above sent to the In0 of the Lua.

```lua
In0 = this:read(0)
if In0 &lt; .5 then this:write(0,0)
else this:write(0,.15) end
```

This will send a 0.15 signal to the Out1 of the Lua when the RC slider is greater than or equal to 0.50 TRUE.

See the object description for the [[Signal Cable]] for the basics of signaling in Principia.