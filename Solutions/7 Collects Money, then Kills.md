# Robot 7: Collects Money, then Kills

```python
starting_coins = coins
desired_increase = 500

def robot():
    global starting_coins
    print(coins - starting_coins)

    if coins - starting_coins >= desired_increase:
        if nearest_player:
            go_towards(nearest_player)
        else:
            wander()
    else:
        if nearest_item:
            go_towards(nearest_item)
        else:
            wander()
```