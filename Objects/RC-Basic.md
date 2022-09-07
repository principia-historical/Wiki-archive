# RC Basic
Basic control panel with support for 4 output signals.

The RC family of objects allows you to construct control interfaces with buttons, sliders and rotary widgets. These widgets send signals (through red wires), that you can process and forward to your own electronics.

Click the configuration button to open up the control panel configuration screen. Drag widgets to place them on the screen. Each widget will be connected to an output socket, the first widget you place will be connected to **`OUT0`**, the second to **`OUT1`**, and so on.

TIP: Connect your control panel to a set of Debugger objects to visualize how the widgets work.

When the game is played, the control panel can be activated. When any of the widgets are touched or modified, it responds by outputing a value through its output socket.

There are three kinds of widgets.

### Buttons
A constant value of 0 is reported by default, when the button is pressed a value of 1 is reported and continue being reported until the button is released again.

### Sliders
The left end of the slider is 0, the right end 1. Any intermediary position is a raw value between 0 and 1. The default value of the slider can be set by moving its handle in the control panel configuration screen.

### Rotary widgets
Reports a value from 0 to 1 depending on the angular position of the knob. The right-most position (0 degrees) is 0, if the knob is facing UP the reported value is 0.25. If the knob is facing down the reported value is 0.75. The default output value (initial position) of the rotary widget can be set by moving the knob in the control panel
configuration screen.

## User Information
Example: http://archive.principiagame.com/level/3357