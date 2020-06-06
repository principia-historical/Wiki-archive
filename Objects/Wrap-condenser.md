# Wrap condenser
Same properties as a Condenser, but the value will wrap around.

## User Information
The Wrap Condenser stores signal values added to In0 or subtracted from In1 over time and will output the result as a fraction of the max value, 125 times per second. Unlike the [[Condenser]] when a Wrap condenser reaches it's max value it wraps the value back to 0.0 and continues adding, conversely when subtracting past zero the internal value is wrapped back to it's max value. (See [[Condenser]])

Example use,

A [[Digital display]] set to count numbers from 0 to 9, we want to be able to determine the current position of the display so that we can use the number it is showing for calculation.

A sparsified RC button Out0 is split with a [[Y-splitter]], one side is connected to the In1 on the [[Digital display]] to click up the number with each press. The other side is fed to a Wrap condenser In1, we set the Wrap condenser for a max value of 10. Now when ever the button is pressed the Wrap condenser adds 1 to it's internal value and outputs the total divided by 10. So now when the Wrap condenser output will read 0.6 the [[Digital display]] will read 6. You can then take the fraction number and pass it through Cmp type gates and [[IF gate]]s to manipulate the number you've chosen on the display.

See the object description for the [[Signal Cable]] for the basics on signaling in Principia.