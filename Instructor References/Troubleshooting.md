# Troubleshooting Guide

At the time of writing (7/28/2024), CM Clash is in a closed alpha/early beta. As such, there may be numerous bugs of varying levels of severity. This document is to address currently documented gamebreaking bugs and a few other ones that may confuse players.

If **any** of these happen, record the instance and note the circumstances behind the bug so that we can later attempt to reproduce it.

## Code Not Saving

There may be times where the code written for a robot does not reflect its actions. This may happen more often if there is a substantial amount of traffic on the server. If this occurs, then reloading the page usually fixes it.

## Modules Being Disabled

The modules on a robot may not be acting correctly in the arena. If your student reports that a claw isn't grabbing anything near it, the sword isn't swinging, or the gun isn't shooting at anyone when it should, this may be the case. This also might occur more often if the student's prior code revolved around enabling and disabling modules. Re-enabling modules at the start of the `robot()` will fix it.

```python
def robot():
    claw.enable()
    sword.enable()
    gun.enable()
    magnet.enable()
```

## Odd Error Messages

Syntax errors in CM Clash are outputted in the arena as a printed message. However, the line being referenced in the syntax message may not reflect the line with the error in question (for example, "Error on line -1"). However, it does guarantee that a syntax error exists in the user's code somewhere.

## Other Bugs

There may be other bugs that you see as well, some are minor, whereas others may be more severe. Report any bugs that you find that aren't listed here by pinging Victor Phan on BaseCamp.