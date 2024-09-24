# Robot 14: Switch Up Every 10 Seconds

## Time

The variable `current_time` represents how many seconds your robot has been in the arena for.

```python
def robot():
    print(int(current_time))
```

## A Primer on Modulo

The modulo (%) operator is often confusing for students, so let's quickly go over it again.

The result of a division operation is called a **quotient**. In Python, the quotient of division between any 2 numbers is always a **float**, or a number with a decimal point. For example, `5 / 2` is 2.5, and `4 / 2` is 2.0 (not 2).

**Integer division** is a kind of division where the quotient is always an integer. In more technical terms, it is the quotient of regular division, but rounded down to the nearest whole number. For example, `5 // 2` is `2` (not 2.5), and `4 // 2` is 2 (not 2.0).

You'll notice that integer division does not necessarily produce a quotient that is "correct." For example, `5 // 2` is 2, but `2 * 2` doesn't make 5 again. It makes 4. Rounding down the quotient will sometimes result in us losing a value. We call this lost value the **remainder**.

The **modulo** operator, accessed using `%`, gives you the remainder of an integer division operation between two numbers. For example, `5 % 2` is 1, and `4 % 2` is 0 (0, because 2 fits neatly into 4).

Modulo operations are commonly used to detect if a number fits neatly into another number, in other words, we use it to determine if a number A is a **factor** of another number B. One very common application is to check for an even number. An even number modulo 2 will always yield a value 0. An odd number modulo 2 will always yield a value 1.

An important note about the remainder is that it will always be in a certain range. If you modulo any number by 2, the remainder is always either 0 or 1. If you modulo any number by 3, the remainder is always 0, 1, or 2. If you modulo any number by 10, the remainder is from 0 to 9. And if you modulo a number by 20 (hint hint), the remainder is from 0 to 19.

## Goal

For this robot, we want to have it switch between 2 behaviors every 10 seconds. To do this, you will check the current time. You will alternate beyween collecting items and attacking players every 10 seconds.

Bit of a hint for you -- imagine the current time is split into 20 second intervals. In other words, imagine counting 20 seconds, and then starting over again forever. We can do something when you count seconds 1 to 10, and then something else when you count seconds 11 to 20.