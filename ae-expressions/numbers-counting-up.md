#Bounce

**Counting up numbers**

- Add to a `Text layer`
- Tweak `countDur` to speed up or slow down etc

```
startCount = 0;
endCount = 999999999999999;
countDur = 4;
Math.round(linear(time,0,countDur,startCount,endCount))
```
