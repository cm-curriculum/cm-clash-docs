# Robot 1: Hello World

## The `robot` Function

How do you actually code your robot? To understand how, you need to know what the `robot()` function is.

The **robot** function is the brains of your robot. It's what controls the robot's behavior and tells it what to do. As we go deeper into these exercises, you'll be able to play around more with the robot function as well as use complex Python behaviors to influence how your robot acts. 

Do you not know what a function is? To put it simply, in Python, a **function** is a bundle of code that can be run in just one line, instead of several. We often put code into functions to make things more organized, and more readable. 

**If your robot doesn't have a robot function, it won't run!**

```python
def robot():
    if nearest_item:
        go_towards(nearest_item)
    else:
        wander()
```

## Printing

Let's start from square one, even if you're a Python expert already. Let's clear out the current code in the robot function.

The **print** statement in Python works as you would here, although a little differently. This works identically to the usual print statement, however the output will be shown on your screen in a text bubble rather than a console output.

```python
def robot():
    print("Hello World")
```

You can still do the same sort of things, such as concatentation. Also note however that only the latest thing being printed will be shown.

```python
def robot():
    print("Hello " + "World")
```

```python
def robot():
    print("Hello", "World")
```

Is your robot moving when you do this? No, not at all. But remember, baby steps!