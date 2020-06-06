# Signal Cable
Cable used for signaling. Signals can be any value between 0 and 1. Many signals are either 0 (off) or 1 (on), and are then called binary signals. When a signal is any other fraction between 0 and 1, such as 0.5, then the signal is referred to as a "raw" signal.

Some devices only care for binary signals, these devices are called binary devices. Examples of binary devices include the [[XOR gate]], [[AND gate]] and [[Sparsifier]]. When a raw signal is sent to a binary device, the signal is rounded to the nearest binary number. For example, a value of 0.75 would be rounded to 1, and a value of 0.123 would be rounded to 0.

All devices operate at a frequency of 125 Hz, which means 125 signals can be sent through your whole circuitry each second.

## User Information
**The Signal Cable and Understanding Signal Binary**, by zardOz

The Signal Cable is the primary method of sending information between Components, all connections except robotic motor controls and power require the red Signal Cable, though you may decide to use the [[Transmitter]]/[[Receiver]] method to provide the same function. The signal is "Clamped" between 1.0 and 0.0, no components can send or receive a signal of greater than 1.0 or less than 0.0.

### Binary Signaling 101
1.0 = TRUE, On, Yes, Positive, Maximum, Full or Greater than or equal to 0.50*

0.0 = FALSE, Off, No, Negative, Minimum, Empty or Less than 0.50*

It will be very helpful to you to remember the terms above when thinking about how to configure your connections. For example the [[IF gate]] uses "True" and an [[Emitter]] uses "On".

*BINARY DEVICE: Any device or component such as the [[Button]], [[Emitter]], [[Sequencer]], [[Toggler]] or [[Digital display]] which only recognises two signals, 1.0 or 0.0, On or Off, True or False, Yes or No, Positive or Negative.

The Binary Devices must be able to communicate and work with non-binary devices which can also send "Raw" or "Fraction" signals between 0.0 and 1.0. When a binary device is sent a raw signal it will see all signals less than 0.50 as FALSE=0.0 and all signals greater than or equal to 0.50 as TRUE=1.0.

"Hertz" means the number of times per second or "frequency" All devices in the game send a maximum of 125 individual signals called "Bits" per second, on a [[Grapher]] it will appear as a pure unbroken signal, some devices can act that fast but most devices which receive or send the unbroken signal treat it as a continuous signal, some like the [[Condenser]] and [[Gyroscope]] will accept and/or send the signal each bit.

A "tick" refers to a single non-zero bit which is followed and preceeded by 0.0 bits, a signal of one tick per second would be a  non-0.0 signal followed by 124 zeros "100000..."

When building things you dont understand you can always plug your signal into a [[Grapher]] or [[Debugger]] to see exactly how it is behaving at any part of the chain of connections.

(Note: this was derived and expanded from Pajlada's original description above, sorry for the repetition.)

### Principia Glossary (In progress)
* SIGNAL: Any value carried by a red Signal Cable, will always be "Clamped" between 0.0 and 1.0
* BINARY SIGNAL: Either 1.0 or 0.0
* BINARY VALUE: &gt;or= to 0.5 returns 1.0, &lt;0.50 returns 0.0
* RAW SIGNAL: Any signal between 0.0 and 1.0
* FRACTION: Same as raw signal, derived from dividing a smaller signal value from a larger one.
* CONTINUOUS SIGNAL: A pure unbroken 125 hertz signal stream of any value above 0.0
* INTERNAL VALUE: Value stored inside a component prior to being modified and output as a Signal 0.0-1.0
* BUFFER: Internal value used for processing
* SPARSIFIED: Generally refers to a continuous signal turned to a single tick.(see [[Sparsifier]])
* TICK: A single non-zero bit signal proceded and followed by a 0.0 bit
* SIGNAL i1o1: Refers to components with one IN socket and one OUT socket.
* SIGNAL i2o1: Refers to components which take two input signals and combines, compares or modifies them in some way and outputs a single value.
* HERTZ: Frequency or number of times per second. Principia operates at 125 "bits" per second.
* FREQUENCY: Fumber of instances something occurs over a period of time.
* *FREQUENCY*: For [[Transmitter]]s, [[Broadcaster]]s and [[Receiver]]s the identification # of the device so it can be tied exclusively to others.
* SIGNAL STRENGTH: The value of the signal 0.0 - 1.0 at any given time.
* INVERT: 1.0 minus the signal strength
* FLOOR: take a non-1.0 raw signal and make it 0.0
* CEILING: Take a non-0.0 raw signal and make it 1.0
* SQUARE: Multiply a raw signal by itself, will lower value, cannot = 0.0
* SqROOT: Divide a raw signal by itself, will raise value, cannot = 1.0
* RC: Reference to the control box objects , [[RC Micro]], [[RC Basic]], [[RC IO-3]] and [[RC MONSTRO]].
* RC BUTTON: Reference to a widget.
* WIDGET: Term for the graphic buttons, sliders and dials created on the screen for interacting with the game.
* READ: Term for when a component takes in information from one of it's IN sockets.
* WRITE: Term for when a component sends information from one of it's OUT sockets.