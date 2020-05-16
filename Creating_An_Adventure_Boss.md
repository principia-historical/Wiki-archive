# Creating an Adventure Boss
**For new and detailed boss tutorials with example levels, check out these links:**
* [Creating a Simple Adventure Boss](Creating_A_Simple_Adventure_Boss)
* [Creating a Transforming Adventure Boss](Creating_A_Transforming_Adventure_Boss)

This page will give you some tips to create an Adventure Mode boss for others to fight. Make sure you create a new level and its type is set to Adventure.

## Essential Objects

### Condenser
The condenser can be used as HP for the boss. A condenser has two inputs, IN0 and IN1. IN0 will "fill" the condenser. Send 0.1 to it and it increments its internal value by 0.1, for example. IN1 decrements the condenser. The output, OUT0, is the percentage of how filled the condenser is. If you read 1.0 from OUT0, it means it is full, and 0.0 means it is empty.

The condenser has a user-defined max value that can be larger than the 1.0.

### Checkpoint
A checkpoint is where the player will respawn when he dies. You can set a checkpoint to be the active checkpoint by either stepping on it using robot or by sending a value of 1.0 to its input socket.

The checkpoint also has an output socket that will be written to when the player respawns at the checkpoint. So, for example, you could heal the adventure boss every time the player respawns.

### Game Manager
You can send a value of 1.0 to the WIN-port when the boss HP reaches 0 (which can be detected by wiring OUT0 of a condenser through a ceil component). Use transmitters and receives to communicate with the Game Manager without having wires across the level.

### FX Emitter
Emit effects like explosions or highlight the boss when he is hit.

The "Destroy Connections" effect will only affect connections that are destructible, you can make connections destructible by entering connection edit mode in the sandbox (hammer icon below the play button) and lowering their max force slightly. The FX emitter will only affect connections that are "reachable" from the FX emitter by following connections between objects it itself is attached to.

### Object finder and sincos
Object Finder can help the boss find the player. Wire the angle output to a sincos component and you will have 4 values - positive X, negative X, positive Y and negative Y.

## Other useful objects
* Impact sensor if you want impacts to decrement the boss HP.
* Object field can detect a specific kind of object that the boss is weak against.
* Magnetic socket and Magnetic plug can be used for some cool effects like connecting a small piece to a larger piece.
* Event listener there's the Player Die event that can be useful to recharge the boss HP or something

## Tips
* Interactive Objects can be fun. They can always be dragged when they are near the player. They can be used to build a path to a higher point to reach the bosses weak point, or be thrown at the boss, for example.
* Full action from start to end? Not many people appreciate that - mix calmness and action, or at least give the player a chance to relax before the action begins.
* Don't forget the surroundings! The level can be very helpful for the player - things to hide behind, or climbing to high places, luring the boss to a specific location, etc.
* if you want a start-story can you use a prompt.