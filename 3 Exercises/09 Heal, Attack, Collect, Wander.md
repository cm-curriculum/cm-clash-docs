# Robot 9: Heal, Attack, Collect, Wander

## Healing

In the arena you'll see these batteries laying around.

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/9%20Heal%2C%20Attack%2C%20Collect%2C%20Wander/f2f03db2-819d-40ad-8bf2-bf6451d2c1f6.png)

These are **healing** items that will heal you for 20 health. When collecting any item, you will collect coins, gems, and batteries. But, there might be times where it's more important to only get healing items. Therefore, you have access to a third detection variable, `nearest_heal`. This works identically to `nearest_item` and `nearest_player`, except it's for healing items in your detection zone.

## Goal

Using `nearest_heal`, `nearest_player`, and `nearest_item`, create a robot that can do all 3. As with last time, ensure that these actions are given priorities. What's the most important action that you think your robot should do?