# Robot 18: Shoot at Long Range, Swing at Short Range

```python
def robot():
    if nearest_player:
        enemy_distance = distance(nearest_player.position, position)
        if enemy_distance >= reach_radius and enemy_distance <= detect_radius:
            print("Gun")
            gun.enable()
            sword.disable()
        elif enemy_distance < reach_radius:
            print("Sword")
            gun.disable()
            sword.enable()
        else:
            print("Defenses Disabled")
            gun.disable()
            sword.disable()
    else:
        wander()
```