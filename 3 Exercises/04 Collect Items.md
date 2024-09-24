# Robot 4: Collect Items

## About Movement

One of the most important things you need to understand in CM Clash is that **you cannot directly control your robot**. You can't use your arrow keys to move your robot around the arena. If you want your robot to move intelligently, you need to code your robot to move intelligently. We cover more on how to achieve this as the exercises continue.

## Go Towards

So far, you've learned about the `wander()` function, which while a neat way to move around, is not necessarily the most ideal way to move around. It's just random.

The `go_towards(position)` function will command your robot to move to a particular point in the arena. One really convenient thing about `go_towards` is that if you pass a variable like `nearest_item` into it, your robot will actually move towards that nearest item! But remember, you need to check if there even is a nearest item first by using an if statement.

And that explains the default code that is given to you at the beginning of CM Clash. Here we check if an item is nearby, and then we go towards it. Otherwise, we wander around. Take note, however, that just going to an item won't collect it. You need a module like a claw or a magnet. If you don't have one of those equipped and you run this code, then you will go to the nearest item and will never leave until another player picks up that item.

If you do have a claw or a magnet equipped though, you will collect it automatically if you're close enough to the item. There is no such thing as a function like `grab` in CM Clash.

```python
def robot():
    if nearest_item:
        go_towards(nearest_item)
    else:
        wander()
```

## Modules, and the Claw

In CM Clash, you have a variety of tools to use. We call these tools **modules**. You can attach up to 8 modules onto your robot. By default, you already have the **claw module** attached.

The **claw** module will automatically grab items that are near your robot. Your robot will **not** be able to grab any collectibles lying around without a claw attached (try it yourself and watch as your robot fails to grab a single coin).

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/3%20Exercises/04%20Collect%20Items/5b711622-14cd-4f78-8d7b-fb35e8504427.png)

## Draining

One thing you need to watch out for when using modules is that they have what is called an **energy drain**. In other words, all modules train some amount of your health every second, some much more than others. With just the claw attached, it's not very noticeable. But keep this in mind for later exercises.