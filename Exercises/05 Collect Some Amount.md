# Robot 5: Collect Some Amount of Money

## Code Outside of Robot

It's possible for you to put code outside of the `robot()` function. For example, you might want starter variables that are modified as the game goes on. In this exercise, we will have you create a starter variable to keep track of how many coins you've earned in the arena.

This code, for example, demonstrates a variable outside of the `robot()` function using a variable named `counter`. In `robot()`, we have to define `global counter` to use it. The actual reason we need to do so is a bit overly complicated so it's better to just go with it. Overall, this robot code will print out how many times `robot()` was called while you were in the arena.

```python
counter = 0

def robot():
    global counter

    counter += 1
    print(counter)
```

## Coins

You're able to determine how many coins you have during a game session using `coins`. We mean the *entire* game session, though, not just for the time you're in the arena. If you earned 1160 coins so far, then that's what will print.

```python
def robot():
    print(coins)
```

## Goal

Grinding for money can take a while. Maybe you want to save up for something like a 1000 coin gun, but don't want to sit around all day. In that case, this robot is supposed to do just that, and notifies you when it's finished.

Your goal for this robot sounds straightforward, but you might have to think a little on this one. We want to have the robot collect some amount of money for us at the start, and once it's done, it will stop and say that it's done.

More specifically, we want you to be able to define a variable at the start, that represents the desired amount of coins you want to collect on this run. For example, 500. Your robot will wander around, collecting items, and once it has collected 500 coins, it stops and prints "I'm done".