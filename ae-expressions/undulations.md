#Undulating (fluid) movement

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