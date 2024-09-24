# Robot 15: Chase Closest Player

## A List of Players

You can access an entire list of players in the arena using `players`. Each player in the player list can be manipulated like you did previously for `nearby_player`. In other words, you can check things like each player's position if you iterate through the `players` list. Every player also has an `id` that you can use to check who's who.

```python
def robot():
    for p in players:
        print(p.id)
```

## Distance

The `distance(pos1, pos2)` function will calculate how far two Cartesian coordinates are from one another. In CM Clash terms, you can use this to determine how far someone is from you. `pos1` and `pos2` are 2-element lists representing Cartesian coordinates.

```python
def robot():
    if nearest_player:
        print(distance(position, nearest_player.position))
```

## Goal

Let's put these two concepts together. You've so far been able to easily determine who's "nearby" you using `nearest_player`. This will check if anyone crossed your detection zone. But if you're in the middle of nowhere, and no one's in your detection zone, you can't move anywhere. So, let's make a robot to find the "closest" player. This is a player who has the shortest distance from you, but may not necessarily be in your detection zone.

This robot will iterate through the list of players in the arena and determine who is the closest to the player. Once the closest is determined, your robot will chase after them.