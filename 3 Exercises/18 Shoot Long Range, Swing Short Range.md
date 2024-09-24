# Robot 18: Shoot at Long Range, Swing at Short Range

## The Gun

Pew pew! The **gun** is a module that you can buy in the shop. This module, when attached, will automatically shoot at enemies from a longer range than your sword. You can upgrade it in various ways. It's expensive, though, so you need to save up coins first.

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/18%20Shoot%20Long%20Range%2C%20Swing%20Short%20Range/6d572e11-0c0e-41c1-a497-5520f8e79294.png)

## Modules

You're able to access the modules that are attached to your robot.

- `claw` will access a claw module if it is attached.
- `sword` will access a sword if it is attached.
- `gun` will access a gun if it is attached.
- `magnet` will access a magnet if it is attached.

## Enabling and Disabling

The mean reason you might need to use things like `claw` or `sword` is because you have the ability to enable and disable them. When a module is **enabled**, it will automatically perform its actions if the right object is within range. For example, the claw, when enabled, automatically grabs items that are close enough. When a module is **disabled**, it does not do anything.

```python
# behold, the most useless robot ever
def robot():
    claw.disable()
```

## Detect vs. Reach Radius

Your robot uses two circular zones around it to determine some behaviors.

- The **detect** radius (in green) detects items or players inside of it. This is how `nearest_item`, `nearest_heal`, and `nearest_player` work.
- The **reach** radius (in red) is used by close range modules like your sword and your claw. Your claw will only grab items if its within this red zone. Your sword will only swing at players if they are in this red zone.

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/18%20Shoot%20Long%20Range%2C%20Swing%20Short%20Range/eae440f5-5fa2-4574-9b32-43f8405cc0fe.png)

## Goal

For this robot, we want it to engage in different weapon behaviors depending on an enemy's distance to you.

- If an enemy is within your detection radius, but not your reach radius, then **disable** your sword, and **enable** your gun.
- If an enemy is within your reach radius, then **enable** your sword, and **disable** your gun.
- If no one is near you, **disable** both your sword and your gun.