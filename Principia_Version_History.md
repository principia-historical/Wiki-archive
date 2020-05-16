# Principia version history

# Principia 1.4

Principia 1.4 "Adventure Update" was released on February 10th, 2014.

## Changes in 1.4.0.1 to 1.4.0.4
* First PC and iOS releases
* Various bug fixes
* Factory sliding fixed
* Fixed ugly factory rendering
* Conveyor did not work on bedrock

## Changes in 1.4 - February 10th, 2014
* Robot movement revised
* Added support for in-game adventure building
* Robot can now equip different weapons and tools on each arm
* 2 new main levels (1 medium, 1 hard)
* Textured pixels
* Terrain painting in sandbox
* Support for mining terrain
* New object: Oil Rig
* New object: Crane
* New object: Factory, for constructing objects in adventure mode
* New object: Artifical Gravity
* New object: Shape Extruder
* New object: Plastic Box
* New object: Fluid
* New object: Boundary (i1o1)
* Added gem stones
* Added various power-up oils and basic oil mixing
* Robot armour system
* New weapon: Shotgun
* New weapon: Railgun
* New tool: Builder tool
* New tool: Mining tool
* Added a smaller platform size
* Voltage system revised (does not affect old levels)
* Various issues with multi-part objects (damper, open pivot) fixed
* Servo Motor now has a speed cap option
* Bugfix: Fan applied forces across layers
* Bugfix: servo motor had mismatching CCW/CW speeds
* Bugfix: Robot could layermove through objects once
* Bugfix: Robot jump was weird sometimes
* Bugfix: Object/ID field improperly reported dummys and a few other object types
* New widgets: 3x1 slider, vertical sliders, 3x3 radial
* Conveyor can now be made dynamic
* Mini emitters and absorbers can now handle the smallest cylinder
* Emitters/absorbers can now handle all types of robots
* Digital Display renamed to Passive Display
* Added Active Display
* Robot can now box himself for protection
* Improved exlosion and rocket effects
* New physics stability options: prismatic and pivot error tolerance
* New Lua methods: world:raycast, world:query, entity:highlight, entity:get_layer, this:draw_line, this:listen_on_frequency, this:read_frequency, this:clear_texels, game:message, game:poll_event, game:get_cursor(), world:get_gravity(), entity:local_to_world(), entity:world_to_local()
* Lua set_sprite_tint and set_sprite_z renamed to set_draw_tint and set_draw_z
* Rubber objects can now specify custom restitution/friction values.

# Principia 1.3
Principia 1.3 "Christmas Update" was released on December 20th. It added support for Lua scripting, performance improments and much more.

## Changes in 1.3
* Huge performance improvements, up to 300% boost on big levels
* Performance improvements to all effects
* Triangle waveform added to synthesizer
* Almost all objects now have proper descriptions
* The camera now moves automatically when you drag an object against a screen border
* New level property: Do not require dragfields
* Power Supply max voltage doubled to 48V
* New object: Cursor Field, an invisible, resizable touch-detector. Alfajim, this is what you should use for your synth and piano. ;)
* Added object quickadd dialog (search by name)
* New sandbox menu category sorting
* Improvements to sandbox menu
* New object: Lua Script
* Jumper now has a precision-value dialog
* Damage slider added to Spikes
* Increased max zoom-out of Cam Marker
* Bugfix: Linear decay slider error
* Bugfix: Checkpoint only worked in layer 1
* Bugfix: disconnected sockets "remembered" their last value
* Improvements to adventure robot

# Principia 1.2

## Changes in 1.2.4
* Added a config dialog for the Jumper for high-precision needs.
* Experimental triangle wave added to the Synthesizer.
* Huge performance boost (up to 300%) to levels that are use static objects
* Added a slider to the spikes for Damage.
* Increased the maximum zoom for the Cam Marker
* A lot of object descriptions added or refined.
* Bugfixes:
**Linear decay slider
**Checkpoint only worked in layer 1
**Sockets didn't properly reset their value on pause
* Dragging an object in to the border of the screen now moves the camera with the object. This can be disabled in the settings dialog.
* The adventure robot should be less 'jumpy' when colliding with his body against objects.
* FX Emitter performance boost. (???)
* New level property: 'Do not require dragfield'
* Power supply max voltage doubled, have fun!
* New object: Cursor field. Use this object to track the players cursor/finger movement inside the specified field.

## Changes in 1.2.3
* Fixed a graphics issue on Galaxy Tab 3
* New objects: Linear Decay, Limit
* Rope much more stable

## Changes in 1.2.2
* New object: Sequencer
* Fixed a crash that occured when no internet connection was available
* Revised electronics solver (150% performance boost)
* New camera settings
* Portrait mode bugfixes
* Many other bugfixes

## Changes in 1.2.1
* Added a bunch of drum sounds to the SFX Emitter
* Added a lot more options to the Synthesizer
* New level property: Disable physics
* Bugfix: Snap can no longer output values above 1.0
* Various other bugfixes
* It's now possible to change the level type in the Level Properties dialog

## Changes in 1.2
* 10 New objects
** Var getter & setter, for storing level persistant values
** SFX Emitter, Wrap Condenser, IF-else, cmp-e, cmp-l, cmp-le, snap
** Synthesizer for generating sound (BETA)
* New sandbox menu
* New level property: Portrait mode, great for minigames like pinball
* New level property: Disable auto RC cam follow
* Many bugfixes

# Principia 1.1
Versions before 1.1.2 did not keep a proper record of the changes.

## Changes in 1.1.7.1
* Now allowing external storage installations
* It's now possible to delete levels by long-pressing them in the Open dialog
* Various bugfixes

## Changes in 1.1.7
* New object: Signal Graph
* Sensitivity slider for tiltmeter
* Bugfixes related to Time Ctrl object

## Changes in 1.1.6
* Touch input fine-tuning
* New object: Cam Zoomer
* New object: Time control
* New object: Prompt
* Bugfix: Glitch when jumping in adventure mode
* Bugfix: Too many sticky notes crashed the game
* Bugfix: Switch object did not reset properly after play/pause
* Various tiny object bugfixes
* Various object size/model fixes
* Help labels are now rendered above sockets
* RC override values now working properly
* Increased friction of wheel (does not affect old levels)

## Changes in 1.1.5.1
* Bugfix: The loader is now a lot more failsafe. In case of a crash, the settings file is reduced to lower graphics in an attempt to let the game load properly.

## Changes in 1.1.5
* Bugfix: Game progress was lost if phone went to sleep during loading screen
* Transmitted 0-values now have low priority
* Initial value of toggler can now be set
* Added a settings button in the main menu
* Implemented object snap movement/rotation. While moving or rotating an object, hold down another finger to enable snap
* Level 21 can now be completed

## Changes in 1.1.4
* Bombs can now be destroyed using lasers.
* Rope rendering bugfixes.
* Command pad could not aim left.
* Sparsifier bugfix.
* Main level bugfixes.
* Rocket/Thruster sublayer fixes.

## Changes in 1.1.3
* 2 new levels
* Fixed some text size issues on high-density devices
* Electronic device labels now fade out when zoomed out
* Smaller game size
* Various bugfixes

## Changes in 1.1.2
* Implemented Autosave in the sandbox
* Fixed some texture issues
* Improved handling of back button and pausing/resuming
* Adventure mode bugfixes