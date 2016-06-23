#Random flickering opacity expression for AE

- Set `Opacity` to 50%
- Add following expression:

`on=100;
off=0;
x=wiggle(10,50)
if (x>50) on else off`

[Source](https://forums.creativecow.net/thread/227/26572)
