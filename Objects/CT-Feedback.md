# CT Feedback
The CT Feedback is an extended version of CT Mini with 3 output feedback slots. CT Feedback supports any kind of motor.

Sockets:
- **`OUT0`**: Motor interface, blue cable
- **`OUT1`**: Speed feedback (optional)
- **`OUT2`**: Force/torque feedback (optional)
- **`OUT3`**: Error feedback (optional)
- **`IN1`**: Speed control (optional, default = 1)
- **`IN2`**: Reverse (optional, default = 0)
- **`IN3`**: Speed/force tradeoff control (optional, default = as defined by slider)
- **`IN0`**: Power

The current speed of the motor is reported through **`OUT1`**. The reported speed is a percentage of the maximum speed of the motor, where 0 means no movement and 1 means the motor is moving at its maximum speed.

The force or torque being applied by the motor is reported in a similar manner through **`OUT2`**. It is a value between 0 and 1 where 1 is the maximum force or torque attainable by the motor.

The error feedback (**`OUT3`**) outputs exactly 1 when an "error" is detected. Errors are due to external forces that prevent the motor from moving or causes the motor to move in the wrong direction. Note that this signal can be very noisy when the motor is stuck. It is a constant 1 if the motor is moving in the wrong direction.

## User Information