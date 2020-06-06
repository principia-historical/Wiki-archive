# AND gate
Binary device. If both **`IN0`** and **`IN1`** is 1, output 1. Otherwise output 0.

## User Information
And gates are binary devices which will output 1.0 if both In0 and In1 receive a TRUE binary signal,>=0.50.

To create an And gate series with three or more required inputs see the object description for the **Y-splitter**

Wired with **Signal Cable**s, the AND Gate will send a signal through the Output if a signal is received from BOTH Inputs

Example:

```
Button--(IN1)--AND Gate--(IN0)--Pressure sensor
                  /
                 /
               motor---Battery
```

Both the **Button** and the **Pressure sensor** need to be triggered for the motor to receive the signal.

The following **LuaScript** will turn the Lua into an And Gate,

```lua
In0 = this:read(0)
In1 = this:read(1)
if In0 &lt; .5 and In1 &lt;.5 then this:write(0,0)
else this:write(0,1) end
```

See the object description for the **Signal Cable** for the basics of signaling in Principia.

### Tutorials
"Basic Parts Tutorial #1: AND/OR Gates"

http://principiagame.com/level/715 -zardOz

"AND, NAND examples"

http://principiagame.com/level/798 -Alfajim