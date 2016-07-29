#Scroll something up to a point

- Add following expression to `position`

```
movementDuration = .5;
movementAmount = -200;

yValueChange = ease(time, 0, movementDuration, 0, movementAmount);

value + [0, yValueChange];
```

[Source](https://forums.creativecow.net/thread/227/32514)
