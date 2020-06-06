# Y-splitter
Forward the incoming signal **`IN0`** to the two outputs **`OUT0`**, **`OUT1`** without modifying it.

## User Information
The Y-splitter forwards the unmodified value of it's input socket signal to both output sockets.

* In0: Input signal to be split
* Out0: Outputs the value of In0, unmodified.
* Out1: Outputs the value of In0, unmodified.

To split a signal into three or more outputs use a Y-splitter series...

Example,

  We want four [[Fan]]s controled by one RC slider, take the RC output into a Y-splitter, output one [[Signal Cable]] to the first [[Fan]] and the other
  to another Y-splitter. On the second Y-splitter, again send one output to [[Fan]] #2 and the other output to a third Y-splitter, the last outputing both to [[Fan]]s #3 and #4.

See the object description of the [[Signal Cable]] for the basics of signaling in Principia.

### Tutorials
"Y splitter tutorial"

http://principiagame.com/level/589 -ffjake

"Basic Parts Tutorial #4: Power Supply/Y-splitter"

http://principiagame.com/level/759 -zardOz

"Basic Parts Tutorial #6: Inverter +(Y-split, L-Motor)"

http://principiagame.com/level/790