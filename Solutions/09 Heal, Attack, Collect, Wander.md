# Robot 9: Heal, Attack, Collect, Wander

```python
def robot():
    if nearest_heal:
        print("heal")
        go_towards(nearest_heal)
    elif nearest_player:
        print("player")
        go_towards(nearest_player)
    elif nearest_item:
        print("item")
        go_towards(nearest_item)
    else:
        wander()
```