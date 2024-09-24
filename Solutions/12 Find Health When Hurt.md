# Robot 12: Find Health When Hurt

```python
def robot():
    if health < 50:
        if nearest_heal:
            go_towards(nearest_heal)
        else:
            wander()
    else:
        wander()
```