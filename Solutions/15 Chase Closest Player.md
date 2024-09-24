# Robot 15: Chase Closest Player

```python
def robot():
    closest_player = players[0]
    closest_distance = distance(position, closest_player.position)
    for p in players:
        this_distance = distance(position, p.position)
        if this_distance < closest_distance:
            closest_distance = this_distance
            closest_player = p
    
    go_towards(closest_player)
```