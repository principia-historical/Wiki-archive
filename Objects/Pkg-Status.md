# Pkg Status
Get the status details for a level in the current package. Use the configuration button to specify which level to query info about. The level index of a level is position of the level in the list of levels in the package, level index 0 being the first level.

To check absolute completion status, please wire **`OUT0`** to a floor component.

- **`OUT0`**: Percent completed. 1.0 if the level has been completed, otherwise top_score/final_score or 0.0.
- **`OUT1`**: Unlock status. Returns 1.0 if the level is unlocked according to the package unlock count.
- **`OUT2`**: 1.0 if this level was the last played level before the current one.

## User Information