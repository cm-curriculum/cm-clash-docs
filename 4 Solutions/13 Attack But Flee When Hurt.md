# Robot 13: Attack But Flee When Hurt

```python
def robot():
    if health < 50:
        if nearest_player:
            enemy_x, enemy_y = nearest_player.position
            flee(enemy_x, enemy_y)
        elif nearest_heal:
            go_towards(nearest_heal)
        else:
            wander()
    else:
        if nearest_player:
            go_towards(nearest_player)
        elif nearest_item:
            go_towards(nearest_item)
        else:
            wander()

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
```