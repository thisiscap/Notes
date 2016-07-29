#Throw

**Move at a constant speed without keyframes**

- Add following to `position`

```
veloc = -10; //horizontal velocity (pixels per second)
x = position[0] + (time - inPoint) *veloc;
y = position[1];
[x,y]
```