# Robot 17: Chase Lowest Health Player, Dodge Everyone Else

```python
import random

def get_lowest_hp_player():
    lowest_hp_player = players[0]
    lowest_health = lowest_hp_player.health
    for p in players:
        if p.health < lowest_health:
            lowest_health = p.health
            lowest_hp_player = p
    return lowest_hp_player

def flee(enemy_x, enemy_y):
    print("AAAAAAHHH")
    if enemy_x > posX:
        move_left()
    else:
        move_right()
    
    if enemy_y > posY:
        move_down()
    else:
        move_up()

def robot():
    target = get_lowest_hp_player()
    go_towards(target)

    if nearest_player and nearest_player.id != target.id:
        enemy_x, enemy_y = nearest_player.position
        flee(enemy_x, enemy_y)
```