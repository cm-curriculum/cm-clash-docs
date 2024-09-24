# Robot 3: Prints Nearest

Let's talk about another variable that you have access to in CM Clash.

## Items

There are several items that exist in the arena in CM Clash.

| Name    | Description            | Picture                                                                               |
|---------|------------------------|---------------------------------------------------------------------------------------|
| Coin    | Gives 10 points.       | ![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/3%20Print%20Nearest/2dee0d74-f188-4299-9469-a935d49d2c61.png) |
| Gem     | Gives 10 to 20 points. | ![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/3%20Print%20Nearest/df54f2d0-40b7-4eb0-b6e9-8391103781fe.png) |
| Battery | Heals for 20 points.   | ![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/3%20Print%20Nearest/09026def-e1e5-4b08-9700-4ebcf8098b32.png) |

## Detection Radius

Your robot has what is called a **detection radius** around it. It's a circular zone surrounding your robot, pictured in green below. This visualization is turned off by default.

![](https://storage.googleapis.com/cm-image-repository.appspot.com/cm_clash/Exercises/18%20Shoot%20Long%20Range%2C%20Swing%20Short%20Range/eae440f5-5fa2-4574-9b32-43f8405cc0fe.png)

## Nearest Items

Now that we know what items there are, and what our detection radius is, why did we mention them?

If any item crosses your detection radius, then it's considered a "nearby" item to your robot. You can access a nearby item using the variable `nearest_item`. `nearest_item` will only have a valid value if an item has crossed into your detection radius. Otherwise, it will have a value of `None`, which in Python means no data. `None` values are not safe to play around with and easily result in errors. That's why you need to check if `nearest_item` has a value first.

```python
def robot():
    wander()
    if nearest_item:
        print("Nearest item at:", nearest_item.position)
```

## Updating Values

You'll notice that `nearest_item` changes and updates its values regularly in the arena when you run the code above. But there's no loops in `robot()`. How is that value constantly changing?

The answer is a concept that is **very** important in CM Clash. **The `robot()` function runs every second when you're in the arena.**