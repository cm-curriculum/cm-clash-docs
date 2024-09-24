# Robot 10: Flees

## Moving

So far, we only know of two functions that can move your robot. `wander` will make your robot move around aimlessly. `go_towards` will make your robot move towards a specific target.

## Cardinal Movement

If you don't know, **cardinal directions** are north, south, west, and east. In CM Clash, you can make your robot move in one of the cardinal directions using

- `move_left()`
- `move_right()`
- `move_down()`
- `move_up()`

## Positions

Every robot and item in the arena has what is called a **Cartesian coordinate**. Think of the arena as two number lines. One is horizontal, called the **x axis**, and one is vertical, called the **y axis**. Everything inside the arena lies somewhere along the x axis, and somewhere along the y axis. A cartesian coordinate is two numbers, it's x position and its y position, in that order. The green dot, for example, is 2 units along the x, and 3 units along the y, so its coordinate is (2,3).

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/10%20Flees/5c62f0f2-41b3-4224-be09-01fe2451294f.png)

Algebra-related math aside, the reason we're talking about Cartesian coordinates is because it's useful for us to determine some behaviors. You can, for example, use coordinates to determine where an enemy player is in relation to your position.

You can get your x and y position in CM Clash by using the `posX` and `posY` variables.

```python
def robot():
    wander()
    print(posX, posY)
```

Other players in CM Clash have a **position** variable. This is a 2 element list, that represents a Cartesian coordinate. You can get their x and y position by doing a line like so:

```python
def robot():
    wander()
    if nearest_player:
        enemy_x, enemy_y = nearest_player.position
        print(enemy_x, enemy_y)
```

## Goal

Let's put all of the concepts we just learned together. The goal of this robot is a little more complex then normal. We want to create a robot that will run away from every player that gets near it. If a player gets near you, you have to determine where it is in relation to you. If it's to your right, you move left, and vice-versa. If it's above you, you move down, and vice-versa.