# CM Clash Code Documentation

## Utilities

### Variables

| Variables       | Type          | Description                                                                          |
|-----------------|---------------|--------------------------------------------------------------------------------------|
| `starting_time` | `float`       | The amount of time, in seconds, that a match started since an epoch.                 |
| `current_time`  | `float`       | The amount of time, in seconds, that a match has been going on for.                  |
| `arena_size`    | `int`         | The size of the play arena, in meters.                                               |
| `coins`         | `int`         | The current amount of coins the player has total (**including** outside of a match). |
| `players`       | `list[Robot]` | All of the robots active during a match.                                             |

### Functions

| Functions              | Return Type | Description                                                                                                                                                                                          |
|------------------------|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `distance(pos1, pos2)` | `float`     | Returns the distance in meters (units) between two positions. `pos1` and `pos2` are both two-element long lists, containing two floats [x, y], which represent the X and Y coordinates in the arena. |














## Arena Objects

Arena objects are any items present during arena play. This includes *both* robots and items.

### Variables

| Variables   | Type          | Description                                                                                                                |
|-------------|---------------|----------------------------------------------------------------------------------------------------------------------------|
| `position`  | `list[float]` | A two-element long list, containing two floats, [x, y], which represent the X and Y coordinates of an object in the arena. |
| `posX`      | `float`       | This object's X position in the arena.                                                                                     |
| `posY`      | `float`       | This object's Y position in the arena.                                                                                     |
| `value`     | `int`         | How much this item is worth. For example, a coin's value is `1`.                                                           |
| `item_type` | `str`         | Returns a string of what item type this object is, either `"Coin"`, `"Diamond"`, or `"Heal"`.                              |


















## Robots

Robots are specialized arena objects which represent yourself and other players.

### Variables

| Variables                | Type                    | Description                                                                                                                                                                             |
|--------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `position`               | `list[float]`           | A two-element long list, containing two floats, [x, y], which represent the X and Y coordinates of an object in the arena.                                                              |
| `posX`                   | `float`                 | This object's X position in the arena.                                                                                                                                                  |
| `posY`                   | `float`                 | This object's Y position in the arena.                                                                                                                                                  |
| `nearest_player`         | `Robot` or `None`       | Returns the nearest detected player within your detection radius, excluding yourself. Returns `None` if no robot is in your vicinity. **This can only be called on your own robot**.    |
| `nearest_item`           | `ArenaObject` or `None` | Returns the nearest detected item within your detection radius. Returns `None` if no item is in your vicinity. **This can only be called on your own robot.**                           |
| `nearest_coin`           | `ArenaObject` or `None` | Returns the nearest detected currency (coin or diamond) within your detection radius. Returns `None` if no currency is in your vicinity. **This can only be called on your own robot.** |
| `nearest_heal`           | `ArenaObject` or `None` | Returns the nearest detected battery within your detection radius. Returns `None` if no battery is in your vicinity. **This can only be called on your own robot.**                     |
| `nearest_players`        | `list[Robot]`           | Returns a list of all players within your detection radius, excluding yourself. **This can only be called on your own robot.**                                                          |
| `nearest_items`          | `list[ArenaObject]`     | Returns a list of all items within your detection radius. **This can only be called on your own robot.**                                                                                |
| `nearest_coins`          | `list[ArenaObject]`     | Returns a list of all currencies within your detection radius. **This can only be called on your own robot.**                                                                           |
| `nearest_heals`          | `list[ArenaObject]`     | Returns a list of all batteries within your detection radius. **This can only be called on your own robot.**                                                                            |
| `attached_modules`       | `list[Module]`          | Returns a list of all modules attached to a specific robot.                                                                                                                             |
| `attached_modules_types` | `list[str]`             | Returns a list of the types of modules attached to a specific robot.                                                                                                                    |
| `has_sword`              | `bool`                  | Whether or not a robot has a sword attached.                                                                                                                                            |
| `has_gun`                | `bool`                  | Whether or not a robot has a gun attached.                                                                                                                                              |
| `has_claw`               | `bool`                  | Whether or not a robot has a claw attached.                                                                                                                                             |
| `has_magnet`             | `bool`                  | Whether or not a robot has a magnet attached.                                                                                                                                           |
| `swords`                 | `list[Module]`          | Returns a list of all swords attached to a robot.                                                                                                                                       |
| `guns`                   | `list[Module]`          | Returns a list of all guns attached to a robot.                                                                                                                                         |
| `claws`                  | `list[Module]`          | Returns a list of all claws attached to a robot.                                                                                                                                        |
| `magnets`                | `list[Module]`          | Returns a list of all magnets attached to a robot.                                                                                                                                      |
| `sword`                  | `Module` or `None`      | Returns the first sword in your robot, if one is attached.                                                                                                                              |
| `gun`                    | `Module` or `None`      | Returns the first gun in your robot, if one is attached.                                                                                                                                |
| `claw`                   | `Module` or `None`      | Returns the first claw in your robot, if one is attached.                                                                                                                               |
| `magnet`                 | `Module` or `None`      | Returns the first magnet in your robot, if one is attached.                                                                                                                             |
| `max_battery`            | `int`                   | The maxmimum amount of battery (health) a robot can have.                                                                                                                               |
| `battery`                | `int`                   | The current amount of battery (health) a robot currently has.                                                                                                                           |
| `speed`                  | `float`                 | How many meters (units) a robot can move per second.                                                                                                                                    |
| `detect_radius`          | `float`                 | How close an `ArenaObject` needs to be to a robot for it to detect it.                                                                                                                  |
| `reach_radius`           | `float`                 | How close an `ArenaObject` needs to be to a module for it to perform an action. For example, a claw can detect an item from far away but must be very close to collect it.              |
| `id`                     | `int`                   | A unique integer ID assigned to a robot when it spawns in the arena. Use this to keep track of particular robots.                                                                       |
| `my_robot`               | `Robot`                 | Returns a reference to your own robot. There is usually no reason to use this, but we have it here anyway for fun.                                                                      |
| `movement_vector`        | `list[str]`             | A two-element long list, containing two floats, [x, y], which represent how much a robot will move horizontally and vertically in 1 second.                                             |
| `is_moving_left`         | `bool`                  | Whether or not a robot is traveling left.                                                                                                                                               |
| `is_moving_right`        | `bool`                  | Whether or not a robot is traveling right.                                                                                                                                              |
| `is_moving_up`           | `bool`                  | Whether or not a robot is traveling upwards.                                                                                                                                            |
| `is_moving_down`         | `bool`                  | Whether or not a robot is traveling downwards.                                                                                                                                          |
| `is_moving`              | `bool`                  | Whether or not a robot is traveling at all.                                                                                                                                             |

### Functions

| Functions                    | Return Type | Description                                                                                                                                                                                                                                                                                           |
|------------------------------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `move_up()`                  | `void`      | Moves your robot upward. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot.**                                                                                                                                                       |
| `move_down()`                | `void`      | Moves your robot downward. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot.**                                                                                                                                                     |
| `move_left()`                | `void`      | Moves your robot to the left. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot.**                                                                                                                                                  |
| `move_right()`               | `void`      | Moves your robot to the right. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot.**                                                                                                                                                 |
| `move_to(pos)`               | `void`      | Moves your robot to a specific coordinate in the arena. `pos` is a two-element long list, containing two floats, [x, y], which represent an X and Y coordinate in an arena. Any other movement function cancels this movement. **This can only be called on your own robot.**                         |
| `move_to(x, y)`              | `void`      | See `move_to(pos)`. This variation works the same, but accepts the X and Y coordinate individually instead of as a list.                                                                                                                                                                              |
| `set_move_vector(direction)` | `void`      | Moves your robot in a specific direction. `direction` is a two-element long list, containing two floats, [x, y], which how far horizontally and vertically you want the robot to travel per second. Any other movement function cancels this movement. **This can only be called on your own robot.** |
| `set_move_vector(x, y)`      | `void`      | See `set_move_vector(pos)`. This variation works the same, but accepts the X and Y values individually instead of as a list.                                                                                                                                                                          |
| `go_towards(object)`         | `void`      | A "chasing" function. Moves your robot to a specific `ArenaObject`'s position. `ArenaObject`s can be either items or robots. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot**.                                                   |
| `wander()`                   | `void`      | Makes your robot "wander" aimlessly around the arena by moving to random positions. Use `stop()`, `move_to()`, or `move_towards()` to cancel this movement. **This can only be called on your own robot.**                                                                                            |
| `stop()`                     | `void`      | Stops any movement from this robot.                                                                                                                                                                                                                                                                   |
| `get_module(index)`          | `Module`    | Returns a module specified by an `int` index. **Make sure the index is not out of bounds.**                                                                                                                                                                                                           |

















## Module

Each module attached to your robot can be accessed and modified using the following:

### Variables

| Variables  | Type    | Description                                                                                    |
|------------|---------|------------------------------------------------------------------------------------------------|
| `type`     | `str`   | What kind of module this is, which are currently `"Claw"`, `"Magnet"`, `"Sword"`, and `"Gun"`. |
| `index`    | `int`   | What position this module is placed in on your robot.                                          |
| `rotation` | `float` | What angle, in degrees, this module is pointing towards.                                       |

| Functions          | Return Type | Description                                                                                                                                                                                                                                                                                  |
|--------------------|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `target(object)`   | `void`      | Points this module towards a specific `ArenaObject`. Call `target_all()` to stop aiming in this direction.                                                                                                                                                                                   |
| `target(pos)`      | `void`      | Points this module towards a specific position. `pos` is a two-element long list, containing two floats, [x, y], which represent an X and Y coordinate in the arena. Call `target_all()` to stop aiming in this direction.                                                                   |
| `target(x, y)`     | `void`      | See `target(pos)`. This variation works the same, but accepts the X and Y coordinate individually instead of as a list.                                                                                                                                                                      |
| `target_all()`     | `void`      | Resets a module's targeting behavior to stop looking in a specific direction.                                                                                                                                                                                                                |
| `rotate(degrees)`  | `void`      | Rotates a module by a specific `float` degrees, where 0 degrees points directly upwards and works clockwise.                                                                                                                                                                                 |
| `disable()`        | `void`      | Disables all activities of a module, including targeting and functionality. Use this if a module is using too much energy during combat.                                                                                                                                                     |
| `enable()`         | `void`      | Reactivates all activities of a module, including targeting and functionality. Only works on already disabled modules.                                                                                                                                                                       |
| `force_activate()` | `void`      | Temporarily reactivates a module, forcing it to perform it's "main" action (for example, a sword swinging, or a gun shooting). Only works on already disabled modules. This does **not** permanently reenable a weapon, call `enable()` for that. Energy is used up whenever this is called. |