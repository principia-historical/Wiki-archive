# Time Ctrl (BETA)
Slow down time according to the input value. This is a BETA object and it can make the simulation buggy. Please report any issues related to object forces and timings.

Time can NOT be stopped completely since that would stop all electronics from running and prevent you from starting time again. An epsilon value of 0.01 is added as the minimum time speed.

IN0: Multiply time speed by (1.0-IN0) + EPS

## User Information