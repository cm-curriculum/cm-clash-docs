# Robot 16: Chase Lowest Health Player

```python
def robot():
    lowest_hp_player = players[0]
    lowest_health = lowest_hp_player.health
    for p in players:
        if p.health < lowest_health:
            lowest_health = p.health
            lowest_hp_player = p
    
    print("Target has", lowest_health, "HP")
    go_towards(lowest_hp_player)
```