# 0-Reset M. Avg
Identical to Moving Average, but resets itself if an input signal of exactly 0 is received:

```
I: = / x < 0 : xa + I(1-a)
     \ x = 0 : 0
```

Where `x` is the input signal, `I` is the internal value and `a` is a weight factor.

## User Information