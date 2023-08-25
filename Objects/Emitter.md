# Emitter
The emitter will emit copies of a selected object. Copies will be emitted as long as 1.0 is received through IN0, or if IN0 is unplugged. For every time an object is emitted, 1.0 is written to OUT0.

Use the crosshair button to select which object will be emitted. Not all objects can be emitted. The emitted objects will have the exact same properties as the selected object. It is safe to remove the object you selected for the emitter to copy.

Use the slider to configure the minimum interval between two consecutive emits. Alternatively, you can wire IN0 to a Timer object for better control. If you use a timer, it is recommended to set the emitters own interval to as low as possible to avoid missing ticks from the timer.

If something is obstructing the emitter, the emitter will fail to emit.

Objects that can be emitted: Ball, metal ball, cylinder, interactive cylinder, interactive box, interactive ball, any type of robot, corner, dummy, land mine, bomb, wooden box, weight.

- IN0: Emit signal
- OUT0: 1.0 when an object was emitted.

## User Information

### Tutorials
"Basic Parts Tutorial #5: Emitters/Absorbers"

https://archive.principia-web.se/level/776