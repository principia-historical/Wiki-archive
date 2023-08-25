# Broadcaster
Broadcast a signal over a range of frequencies.

If a value other than 0 is receiver through **`IN1`**, the frequency range is shifted by +**`IN1`***10 rounded to the nearest whole value.

If multiple broadcasters broadcast over the same frequencies, what value a receiver would pick up is undefined. A transmitter transmitting on a frequency in a broadcasters frequency range will override the broadcast value.

- **`IN0`**: The signal to broadcast.
- **`IN1`**: Frequency shift.

## User Information
Example level: https://archive.principia-web.se/level/3081