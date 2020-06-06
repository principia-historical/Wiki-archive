# Tiltmeter
Output the angular displacement of the tiltmeter relative to its standing position.

- **`OUT0`**: Counter-clockwise rotation. 0.0 is no rotation, 1.0 is 360 degrees at sensitivity 1.
- **`OUT1`**: Clockwise rotation. 0.0 is no rotation, 1.0 is 360 degrees at sensitivity 1.

## User Information
Tiltmeter sensitivity is calculated by dividing the sensitivity setting by 360. At sensitivity 1, the tiltmeter will reach max 1.0 after a full revolution. Sensitvity 2 = half rotation, 4 = quarter rotation etc.

Importantly you need to understand that the tiltmeter remembers it's initial position and number of rotations, if you rotate a Tiltmeter (sens=1) 5 times around during building it will need to rotate back 5 full revolutions to actually function.