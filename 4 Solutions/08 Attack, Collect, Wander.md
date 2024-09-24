# Robot 8: Attack Collect Wander

```python
def robot():
    if nearest_player:
        go_towards(nearest_player)
    elif nearest_item:
        go_towards(nearest_item)
    else:
        wander()
```