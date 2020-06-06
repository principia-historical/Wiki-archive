# Half-unpack
Invert a half pack.

```lua
if IN0 > 0.5:
  OUT0: 0
  OUT1: (IN0-0.5) * 2
else
  OUT0: (IN0) * 2
  OUT1: 0
```

## User Information