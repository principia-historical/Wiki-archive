# CT Mini
This controller controls the speed and direction of a motor.

- **`OUT0`**: Motor interface, blue cable
- **`IN1`**: Speed control (optional)
- **`IN2`**: Reverse (optional)
- **`IN0`**: Power

To drive a motor you will need 3 objects in total: The motor, a controller (CT), and a power source. Connect **`IN0`** of the CT Mini to a power source (battery or power supply), and connect **`OUT0`** of the CT to any kind of motor.

**`IN1`** allows you to control the speed of the connected motor. The resulting motor speed is proportional to the input voltage. Leaving **`IN1`** disconnected will result in constant maximum speed.

**`IN2`** Reverses the motor as long as a rounded value of 1 is read from the input

## User Information

### Tutorials
"Motor test"

http://principiagame.com/level/313 -Pajleda

"Basic Parts Tutorial #3: Linear Motor/CT Mini

http://principiagame.com/level/753 -zardOz