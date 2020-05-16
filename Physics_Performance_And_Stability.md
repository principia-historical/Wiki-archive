# Physics Performance and Stability
The default behavior of the physics engine is not always optimal. That's why there are several options available to fine-tune the physics simulation. This page will give you an overview of how each option affects the performance and stability of the simulation.

The options can be found under the World tab in the Level Properties dialog. These settings are level-specific.

First, let us see some definitions:
* Joint - A connection/fastening of two objects
* Object/Entity - Anything in the simulation, like a ball or a robot
* Tick - When the simulation runs one time and solves physics for 8 milliseconds. Every second the simulation does 125 ticks.
* Prismatic Joint - A joint that restricts two objects along a line, like a Linear Servo, or a damper.
* Pivot Joint - A joint that allows two objects to rotate around a single point, like a DC Motor, wall pivot, or seesaw base.

## Basic Tuning
When you build something mechanically advanced and notice instability/wobbliness, begin tuning by increasing Prismatic and Pivot Error Tolerance very slightly (not too much). From there, proceed with increasing Velocity Iterations to 20, 40, 60 or even higher if needed.

Think of the Error Tolerance options as "helping the simulation STAY at rest" and Velocity Iterations as "helping the simulation COME to rest". The simulation will not come to rest if it can't stay at rest, and vice versa.

Read more about the options below.

## Position/Velocity iterations
The number of iterations is how precise the physics engine is when solving collisions and joints. In rough terms, low number of iterations let the physics engine consider itself "done" with the current tick even though there might still be "errors" such as objects overlapping or joints that are out of place. When you increase the number of iterations, the physics engine will spend more time to solve the simulation more precisely.

Iterations can severely affect performance but give amazingly stable results.

Position Iterations affect object overlap. If you have a pit of 100 balls, a low amount of position iterations can result in the balls sinking slightly inside each other. Increase position iterations and they will interact more properly. You almost never need to modify the number of position iterations, it can be kept at the default value of 10, unless you notice that objects are sinking in to each other due to heavy forces.

Velocity iterations affect the stability of the simulation, and most importantly how precise joints are solved. If you have a very advanced system of joints, such as a robot with many servo motors and linear motors, increasing the number of velocity iterations will make the joints much more stable, and can turn one wobbly mess into an extremely stable construction.

Be careful when tuning the number of iterations, always try to keep both of them as low as is possible for your specific construction. A high number of iterations severely impacts performance.

## Prismatic/Pivot Error Tolerance
These options were added in 1.4 and allows tuning of joints **without impacting performance**, these options can even improve performance!

When you have a system of many joints, like an advanced big robot or a vehicle, there's a big risk that joints will "fight" with each other and as a result the system becomes very unstable and wobbly. Fighting joints are joints that counter-act each other, making the system unstable.

The Error Tolerance options "slackens" the joints by allowing them to be displaced slightly. If you add too much error tolerance, there will be some obvious visual error, but it is not noticeable in an advanced build.

Since Principia 1.4, a slight error tolerance for both prismatic and pivot joints is enabled by default. You can tune it further or disable it in the dialog.