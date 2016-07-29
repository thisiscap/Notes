#Random and jumpy wiggle

**Jumpy Wiggle 1 makes wiggle skip and hold rather than move fluidly.**

```
// Jumpy Wiggle 1 (moves at a random FPS)
v=wiggle(5,50);
if(v < 50)v=0;
if(v > 50)v=100;
v
```
**Jumpy Wiggle 1 makes wiggle skip and hold rather than move fluidly.**

```
// Jumpy Wiggle 2 (moves at a defined FPS)
fps=5; //frequency
amount=50; //amplitude
wiggle(fps,amount,octaves = 1, amp_mult = 0.5,(Math.round(time*fps))/fps);
```

**Random Wiggle**

```
wiggle(random(1,2),random(20,100));
```