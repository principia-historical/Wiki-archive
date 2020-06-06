# Half pack
Pack two mutually exclusive values, for example a positive and a negative X value, or the output of a Tiltmeter, into a single value.

```lua
OUT0 = / IN1 > 0 : 0.5 + IN1*.5
       \ IN1 = 0 : IN0*.5
```

## User Information