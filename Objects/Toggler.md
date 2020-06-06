# Toggler
Whenever a bit of 1 is read from **`IN0`**, the output stream is toggled.

Example: `0001001000010` -> `0001110000011`

Use in combination with the sparsifier and the effect on control panel buttons is a "checkbox" that can be toggled on/off.

## User Information
Binary device, the Toggler is another of the more critical parts for every type of build, it essentially works like the common light switch. The Toggler will switch from an output of 0.0 to 1.0 each bit that a 1.0 is received to In0. For this reason a Sparsifier is usually required to accompany it. The examples below show two versions of an RC button and what will happen if pressed.

The RC button when pressed sends a stream of 125, 1.0 signals per second until it is let go. If this stream of 1's is fed to a Toggler which is currently Off,

`(0111111110tog —> 0101010100)`

The power will not switch on as desired. Wired to a [[Sparsifier]] it sends only a single 1, producing the desired result, turning the signal ON.

`(011111110spar —> 010000000tog —> 011111111)`

Now the switch will turn on and stay on regardless of how long the button is pressed and and second press will return it to OFF.

See the object description of the [[Signal Cable]] for the basics of signaling in Principia.

### Tutorials
"Toggler using Sparsifiers example"

http://principiagame.com/level/791 -Alfajim