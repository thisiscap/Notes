#Eye blink expression for AE

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
