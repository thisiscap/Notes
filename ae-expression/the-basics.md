#Basic expressions for AE

- Wiggle `wiggle(1,15)`

The wiggle expression is by far the expression that I use the most in After Effects. Wiggle expressions do exactly what you might imagine, they wiggle an object across random values. This expression can be used to make your scene seem more organic and natural.

The first number is the number of wiggles per second and the second number is the value of the wiggle. So, a position parameter with an expression of wiggle(2,30) will wiggle 2 times per second at up to 30 different expressions.

- Time `time*10`

The time expression is perfect for objects with perpetual motion. For example if you wanted to have an object rotate indefinitely you can simply add the word time as the rotation parameter and your object will rotate 1 degree for ever second. The time parameter also works with basic math equations, so if you wanted to have the previous object rotate 30 times faster, you can simply have the expression time*30.


- loopOut() `loopOut()`

The loopOut() expression creates an infinite loop that will last forever. However, unlike the wiggle and time expression the loopOut() expression requires keyframes to be present. So if you had an object that rotates in a full circle in the span of 1 second you could add the loopOut() expression and the motion will be repeated forever.

- seedRandom() `seedRandom(5)`

seedRandom() is just a hair more complicated than the previous keyframes, but it completely makes sense after you think about it for a few seconds.

Random numbers aren’t completely random in After Effects. Sure, it may be called ‘random’, but in reality true random values cannot be achieved in javascript and subsequently After Effects. It’s for this reason that “random” numbers need to begin with some sort of base number. When After Effects draws this base number it uses the layer number that can be found on the far left side of the layer in the timeline. Each different iteration of “random” is called a seed so a random seed of 1 is different from a random seed of 2, but if you had similar wiggle expressions (i.e. wiggle(3,2)) with say a random seed of 5, they would actually wiggle in the exact same way.

If you were to change a layer’s order in the timeline from slot 3 to slot 10 it’s random seed would change, thus your wiggle will now look completely different. This isn’t a huge problem, but sometimes a certain wiggle iteration looks absolutely perfect and you don’t want them to change if your project order changes. To fix this you can use the seedRandom() expression. This expression locks random seeds so that your expression doesn’t change if you add in new layers.

- Math.round() `Math.round()`

Math.round() is an expression that rounds up decimal numbers to the nearest whole number. This is perfect for doing countdowns or numbers in the source text. Simply add your normal expression into the Math.round() expression parenthesis in your source text expression box and all your numbers will be rounded up.
