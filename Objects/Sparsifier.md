# Sparsifier
One of the most important devices to understand!

Outputs 1 if **`IN0`** is 1 and the preceding value of **`IN0`** was not 1.

Example) `000011110000` -> `000010000000`

Use this gate to, for example, convert control panel button presses to button "clicks".

## User Information
The Sparsifier is a critical component to many builds and is important to understand.

The Sparsifier outputs a single 1.0 tick every time there is a change in the signal stream from 0 to 1. Any stream of ones is reduced to a single tick by relaying only the first bit in the stream to the Sparifier's OUT0.

The most useful example is the "click on" RC button widget, when you press the button on your screen a stream of 125 1's per second is sent from the corresponding RC OUT, the sparsifier waits and relays the first 1 in a stream  and eliminates any that follow.

This is an example of the output stream from the RC

```
OUT(Start0000000000button pressed1111111111button released0000000000)
```

If wired through a Sparsifier the result will be

```
(S0000000000bp1000000000br000000000)
```

This will prevent certain things like the [[Toggler]] from turning on and off 125 times per second until you let go. Allowing you to click once to turn the [[Toggler]] on and once to turn it off.

Other example streams

```
(00110011001100) becomes
(00100010001000)

(10101010101010) becomes
(10101010101010)

(01101110101110) becomes
(01001000101000)

(00000000000000) stays unchanged

(11111111111111) becomes
(10000000000000)
```

See the object description of the [[Signal Cable]] for the basics of signaling in Principia. -zardOz

### Tutorials
"Toggler using Sparsifiers example"

https://archive.principia-web.se/level/791 -Alfajim