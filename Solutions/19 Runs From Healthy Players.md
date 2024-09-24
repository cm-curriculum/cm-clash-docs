# Robot 19: Runs From Healthy Players

```python
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
    if nearest_player:
        if nearest_player.health > health:
            enemy_x, enemy_y = nearest_player.position
            flee(enemy_x, enemy_y)
        else:
            go_towards(nearest_player)
    else:
        wander()
```