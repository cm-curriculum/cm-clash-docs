# Robot 5: Collect Some Amount of Money

```python
starting_coins = coins
desired_increase = 500

def robot():
    global starting_coins
    print(coins - starting_coins)

    if coins - starting_coins >= desired_increase:
        print("I'm done")
    else:
        if nearest_item:
            go_towards(nearest_item)
        else:
            wander()
```