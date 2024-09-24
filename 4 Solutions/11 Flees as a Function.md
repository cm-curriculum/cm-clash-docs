# Robot 11: Flees with Function

```python
def robot():
    if nearest_player:
        enemy_x, enemy_y = nearest_player.position
        flee(enemy_x, enemy_y)
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