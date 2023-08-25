# LuaScript
Lua Script object, create your own objects by scripting them.
To learn more about Lua scripting, just search Google for Lua.

WARNING: This object is experimental!
More stuff will be added soon.

The standard Lua math library is available through the global 'math'. For example, math.floor(x), math.sin(a).

For a full list of mathematical functions available, check out [the official Lua math documentation](http://www.lua.org/manual/5.2/manual.html#6.6).

Below is a list of Principia-specific stuff.

## this
"this" is a reference to the script object itself. "this" is a **global** object.

### this:write()
Added in **1.3**

Writes the value to the given OUT-socket. Values will be clamped between 0.0 and 1.0.

**NOTE:** This should only be called once per step.

```lua
this:write(socket_id, value)
```

### this:read()
Added in **1.3**

Reads the value from the given IN-socket.

```lua
local value = this:read(socket_id)
```

### this:has_plug()
Added in **1.5**

Returns true if the given IN-socket has a plug attached to it.

```lua
local b = this:has_plug(socket_id)
```

### this:write_frequency()
Added in **1.3.0.2**

Writes the value to the given frequency. Values will be clamped between 0.0 and 1.0.

**NOTE:** This should only be called once per step.

```lua
this:write_frequency(frequency, value)
```

### this:listen_on_frequency()
Added in **1.4**

Starts listening on the given frequency.**NOTE:** Must be called in the init-function.

```lua
this:listen_on_frequency(frequency)
```

### this:read_frequency()
Added in **1.4**

Reads the value from the given frequency.

**NOTE:** this:listen_on_frequency() must have been called for the frequency before this is used.

```lua
local value = this:read_frequency(frequency)
```

### this:first_run()
Added in **1.3.0.2**, deprecated since **1.5**

Returns true if the current step is called in the first run.

```lua
if this:first_run() then
	-- do something
end
```

### this:get_position()
Added in **1.3.0.2**

Returns the position of the LuaScript object.

```lua
local wx, wy = this:get_position()
```

### this:get_id()
Added in **1.4**

Returns the unique ID of the LuaScript object.

```lua
local id = this:get_id()
```

### this:get_resolution()
Added in **1.4**

Returns the resolution Principia is currently running at.

```lua
local width, height = this:get_resolution()
```

### this:get_ratio()
Added in **1.4**

Returns the current screen ratio (window_width/window_height).

```lua
local ratio = this:get_ratio()
```

### this:set_sprite_blending()
Added in **1.3.0.2**

Sets the current blending mode used for drawing sprites.

Blend modes:
- 0 = 0ff
- 1 = Mode A
- 2 = Mode B

```lua
this:set_sprite_blending(blend_mode)
```

### this:set_sprite_filtering()
Added in **1.3.0.2**

Sets the current filter mode used for drawing sprites.

Filter modes:
- 0 = Nearest
- 1 = Linear

```lua
this:set_sprite_filtering(filter_mode)
```

### this:set_sprite_texel()
Added in **1.3.0.2**

Sets the color of a sprite texel.

```lua
this:set_sprite_texel(x, y, r, g, b, a)
```

### this:clear_texels()
Added in **1.4**, latest update **1.5**

Clears all texels. From 1.5 it can now take a clear value. (0-255)

```lua
this:clear_texels(clear_value)
```

### this:set_draw_tint()
Added in **1.4**

Sets the color for future sprite draws. (this:set_sprite_tint in 1.3.0.2)

```lua
this:set_draw_tint(r, g, b, a)
```

### this:set_draw_z()
Added in **1.4**

Sets the Z-value for future sprite draws. (this:set_sprite_z in 1.3.0.2)

```lua
this:set_draw_z(z_value)
```

### this:set_draw_coordinates()
Added in **1.5**

Sets the coordinate mode any future sprite draws will use.
- 0 = World-based coordinates
- 1 = Screen-based coordinates (0,0 to 100,100)
- 2 = Local-based coordinates (Local to LuaScript-object by default, can be changed with the optional parameter local_id)

```lua
this:set_draw_coordinates(coordinate_mode, local_id)
```

### this:draw_sprite()
Added in **1.3.0.2**

Draws a sprite with the given parameters.

```lua
this:draw_sprite(x, y, rotation, width, height, texel_from_x, texel_from_y, texel_to_x, texel_to_y)
```

### this:draw_line()
Added in **1.4**

Draws a line with the given parameters.

```lua
this:draw_line(x1, y1, x2, y2, width)
```

### this:draw_gradient_line()
Added in **1.5**

Draws a gradient line with the given parameters. The color of the first point will be the one set in this:set_draw_tint(), and the second point will be the values given in the function parameters

```lua
this:draw_gradient_line(x1, y1, x2, y2, width, r, g, b, a)
```

### this:draw_line_3d()
Added in **1.5**

Draws a 3d line with the given parameters.

```lua
this:draw_line_3d(x1, y1, z1, x2, y2, z2, width)
```

### this:draw_gradient_line_3d()
Added in **1.5**

Draws a 3d gradient line with the given parameters.The color of the first point will be the one set in this:set_draw_tint(), and the second point will be the values given in the function parameters

```lua
this:draw_gradient_line_3d(x1, y1, z1, x2, y2, z2, width, r, g, b, a)
```

### this:get_sprite_texel()
Added in **1.5**

Returns the color for the given sprite texel.

```lua
local r, g, b, a = this:get_sprite_texel(x, y)
```

### this:init_draw()
Added in **1.5**

Initialized the drawing functionality for the current LuaScript object with the width and height specified.
- Minimum width or height: 1
- Maximum width or height: 1024
- Width and height MUST be power-of-two.

```lua
this:init_draw(width, height)
```

### this:set_static_sprite_texel()
Added in **1.5**

Sets the color of a static sprite texel. X and Y must be within 0 and the (width/height)-1 specified in this:init_draw()

```lua
this:set_static_sprite_texel(x, y, r, g, b, a)
```

### this:clear_static_texels()
Added in **1.5**

Clears all static texels to the given color. If no colors are specified, 0x7F will be set for all channels.

```lua
this:clear_static_texels(r, g, b, a)
```

### this:add_static_sprite()
Added in **1.5**

Adds a sprite to be rendered with the given paramters. This only needs to be called once per sprite, because it will persist until this:clear_static_sprites() is called.

```lua
this:add_static_sprite(x, y, rotation, width, height, texel_from_x, texel_from_y, texel_to_x, texel_to_y)
```

### this:clear_static_sprites()
Added in **1.5**

Removes all sprites that have been previously added with this:add_static_sprite()

```lua
this:clear_static_sprites()
```

## game
a broad global object containing various *game*-stuff. game is a **global** object.

### game:show_numfeed()
Added in **1.3**, Latest update **1.3.0.3**

Shows the given number on the screen for debugging.

From **1.3.0.3** and onward, it can take the num_decimals argument which specifies with what precision the number should be printed.

```lua
local x, y = game:show_numfeed(number, num_decimals)
```

### game:finish()
Added in **1.3.0.2**

Finish the game with the desired win state.

- 1 = win
- 0 = lose.

```lua
game:finish(win_state)
```

### game:add_score()
Added in **1.3.0.2**

Modifies the current score. Use a negative number to decrease the score.

```lua
game:add_score(score_mod)
```

### game:set_score()
Added in **1.3.0.2**

Sets the current score.

```lua
game:set_score(new_score)
```

### game:get_score()
Added in **1.3.0.2**

Returns the current score.

```lua
local score = game:get_score()
```

### game:activate_rc()
Added in **1.3.0.2**

Activate RC Control of an entity using its object fetched with world:get_entity().

```lua
game:activate_rc(world:get_entity(entity_id))
```

### game:activate_rc_by_id()
Added in **1.3.0.2**

Activate RC Control of an entity using its ID.

```lua
game:activate_rc_by_id(entity_id)
```

### game:message()
Added in **1.4**

Outputs a message on the screen. Duration:
- 0 = Short
- 1 = Long.

```lua
game:message(message, duration)
```

### game:get_cursor()
Added in **1.4**

Gets the world coordinates for the cursor in the given layer.

```lua
local wx, wy = game:get_cursor(layer)
```

### game:poll_event()
Added in **1.4**

Returns true if the given event just occured. [List of events](../World_Events)

**NOTE:** This function should not be used any longer, and will be deprecated soon. Instead, use the on_event function.

```lua
game:poll_event(event_id)
```

### game:get_screen_cursor()
Added in **1.5**

Get the cursor position on the screen. (Screen-based coordinates, based on the users screen resolution)

```lua
local x, y = game:get_screen_cursor()
```

### game:restart()
Added in **1.5**

Restart the level

```lua
game:restart()
```

### game:submit_score()
Added in **1.5**

Submits the player last saved score.

**NOTE**: If the score is submitted before the level has been finished (by game over of level completed), the current score will not be saved yet.

```lua
game:submit_score()
```

### game:set_variable()
Added in **1.5**

Sets the value of the given variable.

**NOTE**: Variables from Lua can contain values outside the normal 0.0-1.0 scope.

```lua
game:set_variable(varname, value)
```

### game:get_variable()
Added in **1.5**

Gets the value of a variable.

**NOTE**: Variables from Lua can contain values outside the normal 0.0-1.0 scope.

```lua
local value = game:set_variable(varname)
```

### game:get_fps()
Added in **1.5**

Returns the mean fps.

```lua
local fps = game:get_fps()
```

### game:prompt()
Added in **1.5.1**

Opens a prompt with the given parameters.

Returns the ID of the prompt dialog that was created, which can be used for verification purposes. Returns nil if no prompt was created.To get the response, implement the following function:

```lua
function on_response(response, prompt_id)
	game:message('The response I got from prompt ' .. prompt_id .. ' was ' .. response)
end
```

The response function will only be called once, store the value if you wish.

Valid responses:
- 1 = First button.
- 2 = Second button.
- 3 = Third button.

```lua
local prompt_id = game:prompt("Do you want to do something?", "Yes", "No", "Maybe!")
```

## cam
controls the players camera. cam is a **global** object.

### cam:get_position()
Added in **1.3**

Returns the X, Y and Z coordinates of the camera.

```lua
local x, y, z = cam:get_position()
```

### cam:get_velocity()
Added in **1.3**

Returns the X, Y and Z velocity of the camera.

```lua
local x, y, z = cam:get_velocity()
```

### cam:set_position()
Added in **1.3**

Sets the position of the camera.

```lua
cam:set_position(x, y, z)
```

### cam:set_velocity()
Added in **1.3**

Sets the velocity of the camera.

```lua
cam:set_velocity(x, y, z)
```

### cam:follow_entity()
Added in **1.3**

Tells the game to follow the entity using the given properties.

```lua
cam:follow_entity(world:get_entity(entity_id), do_snap, preserve_position)
```

### cam:follow_entity_by_id()
Added in **1.3**

Tells the game to follow the entity using the given properties.

```lua
cam:follow_entity_by_id(entity_id, do_snap, preserve_position)
```

### cam:get_zoom_ratio()
Added in **1.5**

Returns the fraction of the players current zoom. 0.0 being fully zoomed in, and 1.0 being fully zoomed out.

```lua
local frac = cam:get_zoom_ratio()
```

## world
world functions.world is a **global** object.

### world:get_entity()
Added in **1.3**, Latest update **1.5**.

Returns an entity (object) reference or nil if the object does not exist.

Renamed from world:get_entity_by_id() in 1.5.

```lua
local my_entity = world:get_entity(entity_id)
```

### world:raycast()
Added in **1.4**

Raycasts from start to end. Returns nil if nothing was hit, otherwise returns the entity, ptx, pty, norx, nory.

```lua
local entity, ptx, pty, norx, nory = world:raycast(startx, starty, endx, endy, layer)
```

### world:query()
Added in **1.4**

Returns a table of entities located within the given coordinates. Layers and sublayers are optional arguments.

```lua
local entities = world:query(min_x, min_y, max_x, max_y, layer, sublayers)
```

### world:get_gravity()
Added in **1.4**

Returns the current X and Y gravity of the world.

```lua
local x, y = world:get_gravity()
```

### world:get_adventure_id()
Added in **1.5**

Returns the ID that belongs to the Adventure robot.

```lua
local id = world:get_adventure_id()
```

### world:get_borders()
Added in **1.5**

Returns the border sizes of the world.

```lua
local bup, bdown, bleft, bright = world:get_borders()
```

### world:get_world_point()
Added in **1.5**

Converts a global screen point to a world point.

```lua
local wx, wy = world:get_world_point(gsx, gsy)
```

### world:set_bg_color()
Added in **1.5**

Sets the BG color to the given values.

**NOTE:** Only works if you're using a colored background in the first place.

```lua
world:set_bg_color(r, g, b)
```

### world:set_ambient_light()
Added in **1.5**

Sets the ambient light of the world to the given value.

```lua
world:set_ambient_light(intensity)
```

### world:set_diffuse_light()
Added in **1.5**

Sets the diffuse light of the world to the given value.

```lua
world:set_diffuse_light(intensity)
```

## Entity
A reference to a Principia object.

### entity:get_id()
Added in **1.3**

Returns the unique ID of the current entity.

```lua
entity:get_id()
```

### entity:get_g_id()
Added in **1.3**

Returns the type ID of the current entity.

```lua
entity:get_g_id()
```

### entity:get_position()
Added in **1.3**

Returns the position of the current entity.

```lua
local x, y = entity:get_position()
```

### entity:get_angle()
Added in **1.3**

Returns the angle of the current entity.

```lua
local angle = entity:get_angle()
```

### entity:get_velocity()
Added in **1.3**

Returns the linear velocity of the current entity.

```lua
local xvel, yvel = entity:get_velocity()
```

### entity:get_angular_velocity()
Added in **1.3**

Returns the angular velocity of the current entity.

```lua
local avel = entity:get_angular_velocity()
```

### entity:get_bbox()
Added in **1.3**

Returns the approximate width and height of the object.

```lua
local width, height = entity:get_bbox()
```

### entity:get_layer()
Added in **1.4**

Returns the layer of the current entity.

```lua
local layer = entity:get_layer()
```

### entity:local_to_world()
Added in **1.4**

Returns the world coordinates converted from the given local coordinates from the current entity.

```lua
local wx, wy = entity:local_to_world(lx, ly)
```

### entity:world_to_local()
Added in **1.4**

Returns the local coordinates converted from the given world coordinates in relation to the current entity.

```lua
local lx, ly = entity:world_to_local(wx, wy)
```

### entity:highlight()
Added in **1.4**

Highlight the entity.

```lua
entity:highlight()
```

### entity:damage()
Added in **1.5**

Only works on destructible objects or creatures.

**NOTE:** Entering a negative amount will heal the object or creature.

```lua
entity:damage(amount)
```

### entity:is_static()
Added in **1.5**

Returns true if the entity is a static object (unable to move), otherwise false.

```lua
if entity:is_static() then
    game:message('This entity is static!')
end
```

### entity:absorb()
Added in **1.5**

Absorbs the entity if possible. The value returns indicates whether the absorb was completed successfully.

```lua
local success = entity:absorb(follow_connections)
```

### entity:apply_torque()
Added in **1.5**

Apply torque to the entity.

```lua
entity:apply_torque(torque)
```

### entity:set_velocity()
Added in **1.5**

Sets the linear velocity of the given entity.

```lua
entity:set_velocity(x, y)
```

### entity:warp()
Added in **1.5**

Warps the entity to the given x/y world coordinates and layer. If the third argument is unset(layer), the layer will not be changed.

```lua
entity:warp(wx, wy, layer = -1)
```

### entity:show()
Added in **1.5**

Shows the entity if it was previously hidden.

```lua
entity:show()
```

### entity:hide()
Added in **1.5**

Hides the entity if it was previously visible. It will still interact with the world even though it's hidden.

```lua
entity:hide()
```

### entity:get_name()
Added in **1.5**

Returns the name of the given entity.

```lua
local name = entity:get_name()
```

### entity:is_creature()
Added in **1.5**

Returns true if the given entity is a creature.

```lua
if entity:is_creature() then
    game:message(entity:get_name() .. ' is a creature!')
end
```

### entity:is_robot()
Added in **1.5**

Returns true if the given entity is any kind of robot.

```lua
if entity:is_robot() then
    game:message(entity:get_name() .. ' is a robot!')
end
```

### entity:is_player()
Added in **1.5**

Returns true if the given entity is the current player.

```lua
if entity:is_player() then
    game:message(entity:get_name() .. ' is the current player!')
end
```

### entity:get_mass()
Added in **1.5**

Returns the mass of the entity.

```lua
local mass = entity:get_mass()
```

### entity:get_density()
Added in **1.5**

Returns the average density of all fixtures of the given entity.

```lua
local density = entity:get_density()
```

### entity:get_friction()
Added in **1.5**

Returns the average friction of all fixtures of the given entity.

```lua
local friction = entity:get_friction()
```

### entity:get_restitution()
Added in **1.5**

Returns the average restitution of all fixtures of the given entity.

```lua
local restitution = entity:get_restitution()
```

### entity:set_color()
Added in **1.5**

Sets the color of the given entity, if possible. Does not work will all entities.

**NOTE:** This function should be used sparingly due to its performance cost, especially when used on pixels.

```lua
entity:set_color(r, g, b)
```

### entity:disconnect_all()
Added in **1.5**

Detach all connections from the entity.

```lua
entity:disconnect_all()
```

### entity:set_target_id()
Added in **1.5**

Sets the target ID of the given entity. Currently only usable with the robot manager.

```lua
entity:set_target_id(target_id)
```

### entity:call()
Added in **1.5**

If the entity is a luascript object, call one of its functions.Example level: https://archive.principia-web.se/level/10140

```lua
local x, y = entity:call("my_ultracool_function", a, b, c)
```

## Creature
A reference to a Principia creature. NOTE: Most entity-functions also work on creature, see creature as an extension to entity.

### creature:get_hp()
Added in **1.5**

Returns the HP and max HP of the creature.

```lua
local hp, max_hp = creature:get_hp()
```

### creature:get_armor()
Added in **1.5**

Returns the armor and max armor of the creature.

```lua
local armor, max_armor = creature:get_armor()
```

### creature:get_aim()
Added in **1.5**

Returns the aim of the current creature, assuming it can aim!

```lua
local aim = creature:get_aim()
```

### creature:set_aim()
Added in **1.5**

Sets the weapon arm angle for the creature, if applicable.

```lua
creature:set_aim(new_aim)
```

### creature:stop()
Added in **1.5**

Stop the creature from walking in the given direction. If no direction is given, the creature stops moving in all directions.left = -1, right = 1, down = 0, up = 2

```lua
creature:stop(direction = all)
```

### creature:move()
Added in **1.5**

Tell the creature to start moving in the given direction.left = -1, right = 1, down = 0, up = 2

```lua
creature:move(direction)
```

### creature:is_action_active()
Added in **1.5**

Returns true if the creature has their special action activated.

```lua
if creature:is_action_active() then
    game:message(creature:get_name() .. ' has their action activated!!')
end
```

### creature:action_on()
Added in **1.5**

Toggles the creatures special action on.

```lua
creature:action_on()
```

### creature:action_off()
Added in **1.5**

Toggles the creatures special action off.

```lua
creature:action_off()
```
