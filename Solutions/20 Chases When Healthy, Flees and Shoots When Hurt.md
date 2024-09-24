# Robot 20: Chases When Healthy, Flees and Shoots When Hurt

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
    if health > 66:
        if nearest_player:
            go_towards(nearest_player)
        else:
            wander()
    elif health > 33:
        if nearest_player:
            enemy_x, enemy_y = nearest_player.position
            flee(enemy_x, enemy_y)
        else:
            wander()
    else:
        if nearest_item:
            go_towards(nearest_item)
        else:
            wander()
```