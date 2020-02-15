# Expressions for use in After Effects

## Bounce

**Inertial Bounce (moves settle into place after bouncing around a little)**

- Add to `Position`, `Scale` etc

```
n = 0;
if (numKeys > 0){
n = nearestKey(time).index;
if (key(n).time > time){
n--;
}
}
if (n == 0){
t = 0;
}else{
t = time - key(n).time;
}
if (n > 0){
v = velocityAtTime(key(n).time - thisComp.frameDuration/10);
amp = .06;
freq = 2.0;
decay = 5.0;
value + v*amp*Math.sin(freq*t*2*Math.PI)/Math.exp(decay*t);
}else{
value;
}
```

## Eye blink expression for AE

- Add the following to `Opacity`:

```
minSeg = 2.0;
maxSeg = 5.0;
blinkDur = .5

seedRandom(index,true)
segStartTime = -random(minSeg,maxSeg);
segEndTime = segStartTime;
i = 1;

while (time >= segEndTime){
i += 1;
seedRandom(i,true);
segStartTime = segEndTime;
segEndTime = segEndTime + random(minSeg,maxSeg);
}

if (time > segStartTime + blinkDur) 100 else 0
```

## Flickering light

- Add following expression to `Opacity`

```
// HIGHER values for probability make a random opacity LESS likely.
// A value of 1 will always create a random opacity, a value of 2 will
// create a random opacity 50% of the time, value of 4 will be 25%, etc.

probability = 6;
// "opacity_normal" is the value set for opacity when the a random opacity is NOT chosen.
opacity_normal = 100;
x = random(probability);
if (x <= 1) {
   opacity = random(100);
} else {
opacity = opacity_normal;
}
```

[Source](http://www.motion-graphics-exchange.com/after-effects/Flickering-Neon-Light/4b8944565425d)

## Hand rendered style

- Add `Turbulent Displace` effect as an `Adjustment Layer`
- Adjust the effect by playing with `Amount` and `Size` dialogues
- Find the `Random Seed` setting under `Evolution` options and add the following expression `time*10`
- Appearance of look can be changed with the `Displacement` dialogue

[Source](http://josiahgatlyn.com)

## Loop a set of Keyframes

- Make keyframes
- Add following expression:

`loopOut(type = "cycle", numKeyframes = 0)`

[Source](https://forums.creativecow.net/thread/227/1564)

## Increasing number count

- Add to a `Text layer`
- Tweak `countDur` to speed up or slow down etc

```
startCount = 0;
endCount = 999999999999999;
countDur = 4;
Math.round(linear(time,0,countDur,startCount,endCount))
```

## Random flicker (opacity)

- Set `Opacity` to 50%
- Add following expression:

```
on=100;
off=0;
x=wiggle(10,50)
if (x>50) on else off
```

[Source](https://forums.creativecow.net/thread/227/26572)

## Scroll something (up to a point)

- Add following expression to `position`

```
movementDuration = .5;
movementAmount = -200;

yValueChange = ease(time, 0, movementDuration, 0, movementAmount);

value + [0, yValueChange];
```

[Source](https://forums.creativecow.net/thread/227/32514)

## Spin/Rotate

- Add the following to `Rotation`:

```
rate = 270; // rotation rate (degrees per second)
time * rate
```

## Wiggle

The first number is the number of wiggles per second and the second number is the value of the wiggle. So, a position parameter with an expression of wiggle(2,30) will wiggle 2 times per second at up to 30 different expressions.

```
wiggle(1,15)
```

## Time

The time expression is perfect for objects with perpetual motion. For example if you wanted to have an object rotate indefinitely you can simply add the word time as the rotation parameter and your object will rotate 1 degree for ever second. The time parameter also works with basic math equations, so if you wanted to have the previous object rotate 30 times faster, you can simply have the expression time*30.

```
time*10
```

## loopOut()

The loopOut() expression creates an infinite loop that will last forever. However, unlike the wiggle and time expression the loopOut() expression requires keyframes to be present. So if you had an object that rotates in a full circle in the span of 1 second you could add the loopOut() expression and the motion will be repeated forever.

```
loopOut()
```

## seedRandom()

seedRandom() is just a hair more complicated than the previous keyframes, but it completely makes sense after you think about it for a few seconds.

Random numbers aren’t completely random in After Effects. Sure, it may be called ‘random’, but in reality true random values cannot be achieved in javascript and subsequently After Effects. It’s for this reason that “random” numbers need to begin with some sort of base number. When After Effects draws this base number it uses the layer number that can be found on the far left side of the layer in the timeline. Each different iteration of “random” is called a seed so a random seed of 1 is different from a random seed of 2, but if you had similar wiggle expressions (i.e. wiggle(3,2)) with say a random seed of 5, they would actually wiggle in the exact same way.

If you were to change a layer’s order in the timeline from slot 3 to slot 10 it’s random seed would change, thus your wiggle will now look completely different. This isn’t a huge problem, but sometimes a certain wiggle iteration looks absolutely perfect and you don’t want them to change if your project order changes. To fix this you can use the seedRandom() expression. This expression locks random seeds so that your expression doesn’t change if you add in new layers.

```
seedRandom(5)
```

## Math.round()

Math.round() is an expression that rounds up decimal numbers to the nearest whole number. This is perfect for doing countdowns or numbers in the source text. Simply add your normal expression into the Math.round() expression parenthesis in your source text expression box and all your numbers will be rounded up.

```
Math.round()
```

## Throw

**Move at a constant speed without keyframes**

- Add following to `position`

```
veloc = -10; //horizontal velocity (pixels per second)
x = position[0] + (time - inPoint) *veloc;
y = position[1];
[x,y]
```

## Undulating (fluid) movement

- Add the following to `Position`:

```
xAmp = 3; //height of undulations (pixels)
xFreq = .3; //undulations per second
xSpeed = 150; //speed of wave (pixels per second)

wl = xSpeed/xFreq; //wavelength (pixels)
phaseOffset = ((position[0]%wl)/wl)*2*Math.PI;
y = xAmp*Math.sin(2*Math.PI*xFreq*time + phaseOffset);
value + [0,y]
```

- Add the following to `Rotation`:

```
xFreq = .3; //undulations per second
xSpeed = 150; //speed of wave (pixels per second)
damping = 15; //undulation damping factor

wl = xSpeed/xFreq; //wavelength (pixels)
phaseOffset = ((position[0]%wl)/wl)*2*Math.PI;
theta = Math.atan(Math.cos(2*Math.PI*xFreq*time + phaseOffset));
radiansToDegrees(theta)/damping;
```

- Adjust `xAmp`, `xFreq`, `xSpeed`, and `damping` to control the speed and depth of the undulations.
- Note that the expressions take into account the original position of the objects, so that objects spread out in the x direction will react at different times as the wave passes by.

[Source](http://www.motionscript.com/expressions-lab-ae65/undulations.html)

## Random and jumpy wiggle

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
