# Synthesizer (BETA)
An electronic device which creates sounds based on its settings and electronic inputs. This is a BETA object which means it's still a work in progress, and any feedback is greatly appreciated.

Advanced help:
* Waveform - How the emitted sound will oscillate
	* Sine Wave
	* Sawtooth (great for string and brass sounds)
	* Square Wave (great for percussive instruments)
	* Pulse Wave (same as square wave, but with a customizable width)
	* Triangle Wave
* Base Frequency - The frequency at which the synthesizer will emit its sound.
* Peak Frequency - The highest frequency at which the synthesizer can emit its sound. This is only relevant when **`IN1`** is used.
* Bitcrushing - Produces a distortion effect by reducing the resolution of the sound.
* Frequency Vibrato Hz - Specifies at what speed the frequency vibrato should be applied.
* Frequency Vibrato Extent - To what extent the frequency should vibrate.  Assuming a base frequency of 220, a Frequency Vibrato Extent of 0.1 will make the sound vibrate between 220-(220*0.1) and 220+(220*0.1).
* Volume Vibrato Hz - Specifies at what speed the volume vibrato should be applied.
* Volume Vibrato Extent - How much the volume will shift.
* Pulse Width - Only used with the Pulse Wave. Specifies the width of the pulse. The width of a square wave is 0.5 (50%) for reference.

- **`IN0`**: Volume (1.0 by default)
- **`IN1`**: Frequency shift. (base frequency + (peak frequency - base frequency) * **`IN1`**)

## User Information