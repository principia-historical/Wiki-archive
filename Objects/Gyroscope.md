# Gyroscope
Continuously signals the absolute angle of the gyroscope as a value from 0 to 1 where the output value is A/360 where A is the absolute angle in degrees.

Also see the [[Tiltmeter]] for measuring angular displacement.

## User Information
The Gyroscope will report the angle displacement of itself from a standing position as a Signal to OUT0, 125 times per second.

Angles in Principa are translated like this, beginning at the right most point on a circle at 0/360 degrees and 0.0/1.0 signal strength. Divide the angle you want by 360, the result will be the signal value of that angle.

A 90 degree angle(pointing up) is 90/360 = 1/4 = 0.25

A 45 degree angle(northeast) is   45/360 = 1/8 = 0.125

As the gyroscope turns in either direction from vertical it's signal output will change accordingly, clockwise cycles from 1.0 - 0.0 and counterclockwise from 0.0 to 1.0.

For calculating particular angle values see the [[Jumper]] object description.

See the [[Tiltmeter]], [[Velocity meter]], [[Servo Motor]] and [[Pointer]] object descriptions for more on reporting angles, displacement and angles in general.

See the object description of the [[Signal Cable]] for the basics of signaling in Principia. -zardOz