# Robot 6: Attack Players

Let's not kid ourselves. The main reason you played this game was so that you could kill other robots. We know.

## The Nearest Player

The variable `nearest_player` is available to you to use. It functions similarly to `nearest_item`, but for players instead. **nearest_player** represents the nearest player within your robot's detection radius, pictured in green below (this radius is turned off by default).

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/18%20Shoot%20Long%20Range%2C%20Swing%20Short%20Range/eae440f5-5fa2-4574-9b32-43f8405cc0fe.png)

`nearest_player` will only have a valid value if a player has crossed into your detection radius. Otherwise, it will have a value of `None`, which in Python means no data. `None` values are not safe to play around with and easily result in errors. That's why you need to check if `nearest_player` has a value first.

## The Sword

The **sword** is the most basic offensive weapon. If a player gets close enough to you (the red zone pictured above), then your sword will automatically swing at them. If you want to attack someone, you just need to get close to them.

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/3%20Exercises/06%20Attack%20Players/029b4b8e-e54d-43b9-b614-feeb7c88800f.png)

**NOTE** that the sword drains twice as much energy per use as the claw does! So be careful with stacking too many swords.

## The Goal

The goal for this robot is to, instead of collecting nearby items, chase nearby players. Otherwise, we'll just wander around until we find one.

```python
def robot():
    if nearest_player:
        go_towards(nearest_player)
    else:
        wander()
```

You'll see that this works and looks nearly identically to our previous item-collecting code.

We gave you the freebie code for this one, but from now on we **won't** be giving out the answers for these anymore.