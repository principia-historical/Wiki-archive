# CT Servo
This controller allows you to control the state (translation or angle) of any kind of motor. The controller outputs feedback data through **`OUT1`** and **`OUT2`**.

Scroll down below to read how the CT Servo treats the difference between linear and rotary motors.

While the CT Servo is compatible with all kinds of motors, for best results you should connect it to a servo-designed motor. These include Linear Servo and Servo Motor.

The CT Servo outputs two kinds of feedback data through **`OUT1`** and **`OUT2`**.

Sockets:
- **`OUT0`**: Motor interface, blue cable
- **`OUT1`**: Angle/Translation feedback
- **`OUT2`**: Torque/force feedback
- **`IN1`**: Servo control
- **`IN0`**: Power

## FOR ROTARY MOTORS (DC Motor, Servo Motor):
The input servo control (**`IN1`**) is the target angle of the rotary motor. The target angle is 360 * **`IN1`**, which means that an input value of 0.5 corresponds to 180 degrees, for example. The CT Servo will always calculate the shortest path to the target angle.

The current angle of the motor will be reported through **`OUT1`**. The reported angle follows the same scheme as the input angle. When the motor has reached its target angle, **`IN1`** is equal to or almost equal to **`OUT1`**.

The amount of torque that the motor is applying to reach its target angle is reported through **`OUT2`**. This value is a percentage of the maximum possible torque that the motor is capable of applying. A value of 1 means that the motor is applying as much torque as possible. This value should be relatively low
unless the motor is stuck.

## FOR **`LINEAR`** MOTORS (Linear Motor, Linear Servo):
The input servo control (**`IN1`**) sets the target position of the linear motors pivot. A value of 0 is one end of the motor, and a value of 1 the other end.

The current position is reported through **`OUT1`**.

The amount of force being applied to move the pivot is reported through **`OUT2`**. A value of 1 means maximum force is being applied and may mean that the motor is stuck.

## User Information