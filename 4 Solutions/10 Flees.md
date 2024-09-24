# Robot 10: Flees

```python
def robot():
    if nearest_player:
        print("AAAAHH")
        enemy_x, enemy_y = nearest_player.position
        if enemy_x > posX:
            move_left()
        else:
            move_right()
        
        if enemy_y > posY:
            move_down()
        else:
            move_up()
    else:
        wander()
```