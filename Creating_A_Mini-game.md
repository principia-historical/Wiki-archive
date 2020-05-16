# Creating a Mini-game
**New and detailed mini game tutorials with screenshots and example levels:**

* [Creating a Target Shooting Mini Game](Creating_A_Target_Shooting_Minigame)
* [Creating a Bee Smasher Mini Game](Creating_A_Bee_Smasher_Minigame)

This tutorial will help you create a simple mini-game.

First, make sure you create a new Custom level. A custom level is completed when any of the following conditions is met:

* The final score is reached (unless the final score is 0).
* A value greater than 0.5 is sent to a Game Manager's WIN-input socket.

To set up your own rules, all you need to do is connect your electronics to the WIN-input on a game manager and define when the game is won.

The final score of the level can be set in Level Properties. If you want the score to be displayed, check the Display Score option as well. A level can be completed based on the current score even when the score is hidden.

At any time, you can get the percentage completed using the score-output socket of the Game Manager. This socket will output a value between 0 and 1 where 1 means the player has reached the final score.

## Useful objects
* **Game Manager** for invoking WIN-state and points counting
* **RC Activator** to automatically enable an RC when the level is started
* **Cam Targeter** and **Cam Zoomer** to control the camera and let the player concentrate on the minigame
* **Timer** if you want time limits or timed actions
* **Event Listener** will output a signal of 1.0 when a specific event occurs
* **Cam Marker** for placing out screenshot markers. Also useful for targeting an arbitrary position using the Cam Targeter.

## Tips
* **Minimize manual camera movement** if moving the camera isn't a part of the mini-game. Use cam targeters to set the camera position. Disable camera movement and zooming completely in the level properties if necessary.