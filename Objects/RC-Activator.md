# RC Activator
Remotely activate an RC. Use the crosshair button to select the target RC.

- IN0: Activate RC
- OUT0: 1.0 if the RC is currently activated

## User Information
Binary Device, remotely activate an RC control, use the crosshairs icon to select a target RC you wish to be activated.

Attempting to use more than one RC activator can be problematic to your build if wired incorrectly. Each RC activator without a 0.0 signal plugged into In0 will attempt to activate continuously. Here is an example of a three RC build which requires seven RC activators,

We have three vehicles and want to be able to switch between the RC controls for each at any time.

Activator 1: Target = starting vehicle [[RC Basic]]. Two of the rc buttons are dedicated to the first vehicle controls and two are sent to [[Sparsifier]]s and sent to Activators # 2 & #3. The Activators only require a single tick.

Activators 2 & 3 each target the other two RC units, now when play is pressed the starting vehicle will have two RC buttons , one to switch to either of the two other RC boxes.

Now add two more Activators with [[Sparsifier]]s to each of the three RCs targeting the other two, now you can switch between any vehicle at any time.

See the object description for the [[Signal Cable]] for the basics of signaling in Principia. -zardOz