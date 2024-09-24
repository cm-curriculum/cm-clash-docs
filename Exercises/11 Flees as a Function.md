# Robot 11: Flees with Function

## Functions

The `robot()` function is not the only thing you can play with. Just like in regular Python, you can define your own functions in CM Clash outside of the `robot()` function, and call it as normal.

```python
def say_hi():
    print("Hiii!!!")

def robot():
    say_hi()
    wander()
```

## Goal

Let's practice writing a function for your robot by refactoring the code that you wrote last time. You will create a function named `flee(enemy_x, enemy_y)`, where `enemy_x` and `enemy_y` are parameters that represent an enemy player's x and y positions. Your `robot()` function will be shorter and call `flee` if you spot a nearby player.