# Robot 14: Switch Up Every 10 Seconds

```python
def robot():
    time = int(current_time)
    if time % 20 < 10:
        print("ITEM")
        if nearest_item:
            go_towards(nearest_item)
        else:
            wander()
    else:
        print("ATTACK")
        if nearest_player:
            go_towards(nearest_player)
        else:
            wander()
```