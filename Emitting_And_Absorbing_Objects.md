# Emitting and absorbing objects
![](https://i.imgur.com/KgG0ecw.png)

In this tutorial you will learn how different emitters and absorbers work and how they can be used.

## Example levels
http://principiagame.com/level/6308

[Basic Parts Tutorial #5: Emitters/Absorbers by zardOz](http://principiagame.com/level/776)

## Emitter
The emitter will emit copies of a selected object. Use the slider to configure the minimum interval between two consecutive emits. Alternatively, you can wire IN0 to a Timer object for better control. If you use a timer, it is recommended to set the emitters own interval to as low as possible to avoid missing ticks from the timer.

Use the crosshair button to select which object will be emitted. It is safe to remove the object after you have selected it.

The emitter emits the selected object as long as 1.0 is received through IN0, or if IN0 is unplugged. Every time an object is emitted, 1.0 is written to OUT0.

Objects that can be emitted:

Ball, metal ball, cylinder, interactive cylinder, interactive box, interactive ball, any type of robot, corner, dummy, land mine, bomb, wooden box, weight.

## Absorber
This object absorb absorbable objets.

Use the crosshair button to select what object can be absorbed. The object cannot have any connections, or it will not be absorbed.

If no object is selected, any of the follow objects can be absorbed:

Ball, metal ball, cylinder, interactive cylinder, interactive box, interactive ball, any type of robot, corner, dummy, land mine, bomb, wooden box, weight.

## Multi-emitter
This emitter let you to emit objects that you have exported with multi-select mode in the editor. The multi-select mode allows you to make copies of objects that are connected together, for example a vehicle.

Use the configuration button to select which exported object will be emitted.

## Mini emitter
The mini emitter is a smaller type of emitter that can be atteched to objects.

Use the crosshair button to select which object that will be emitted.

Objects that can be emitted:

Ball, metal ball, corner, land mine, bomb, interactive ball.

The mini emitter can also emit Interactive Box and the wooden Box, but only if the box's size is set to the smallest.

## Mini absorber
The mini absorber is a smaller type of absorber that can be attached to objects.

Objects that can be absorbed:

Ball, metal ball, corner, land mine, bomb, interactive ball.

The mini absorber can also absorb Interactive Box and the wooden box, but only if the box's size is set to the smallest.

## Auto Absorber
The auto absorber will follow all connections it can find and absorb everything reachable. This is useful for absorbing big complex objects in one go.

IN0 activates the absorber.