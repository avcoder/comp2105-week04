# todo

- Last week I said to use: transition: 2s; which means transition: all 2s ease
- This week we'll go into transition more in depth and see more properties
- So transition: all 2s ease really means transition-property: all; transition-duration: 2s; transition-timing-function: ease
- transforms (pose to pose) go with transitions (straight ahead)
- long hand vs short hand

# CSS Transitions

- read it

# (When to move)

- this is my way of thinking of it
- in order for an animation to do something, you have to define when to move it (if button is being hovered upon)
- what to change = transform
- how to move = transition

# same black slide

- so you need a trigger
- some kind of animatable property to change something
- some kind of transition to define how you're going to move it, without it, it'll be a jump-cut

# All equivalent

- So last week I immediately showed you the short-hand notation
- This week I'll show you the long-hand notation.
- just like other CSS props that have long hand vs short hand, transition is like that
- when you use transition, you have a choice between 5 to 6 different props
- only 1 of them is required, the rest are optional

# transition-property

- this is the thing that you want to change
- for example, here's a link to all the animatable props
- so you can animate background-color, transform, opacity, filter
- when you're using transition-property, you are associating with that, one of these values
- for example if you want to change background-color of a button, you'd say transition: background-color; (that's it)
- informing the browser what prop to look out for (performance)
- don't use implicit/explicit all, rather be more specific
- do codepen exercise

# transition-duration

- the value can be seconds or ms
- in actual production code use ms since it's more robust and used alot
- read it
- so I put a little chart/guide for how fast your animations should be
- through research, it's well known that if animation is 100ms or less, it feels instantaneous
- so if you have an animation 100ms or less, might as well put nothing at all, just as jerky
- 100ms ~ 1s = here's your sweetspot
- that's when the user feels connected, in particular, 250ms ~ 300ms is the magic number
- a lot of gaming programmers use that number (250ms - 300ms) alot
- 1s ~ 10s, feels disconnected. So if you have an animation that needs to take that long, perhaps you need a play button
- so the way to use this is: transition-duration: 3s;
- combined with the previous one where we had transition-property: background-color, you could get a nice effect on a button upon hover for example
- try previous codepen example with the different transition durations

# transition-timing-function

- default is set to ease
- read it
- we'll get more in depth with regards to timing later in class
- examples are: ease-in, ease-out, linear, make-your-own via cubic-bezier, steps
- click link to see more options

# transition-delay

- suppose for example you hover over the button, but you don't want the effect to play right away
- or perhaps you want to stagger 2 or more effects
- so you could say, "don't change the colour yet until 2 seconds after hover"
- read it
- do codepen example for menu stagger

# all 4 together

- so altogether, here are your 4 main properties for transition
- only 1 of them is required (transition-duration), others are optional due to defaults
- last year I said 2 are required
- However, if you were to combine all 4 of these into the shorthand notation it would look like...

# shorthand

- ...this
- So you just put transition: and place all your values in there
- Question: is the order important?
- Do codepen: Take a few minutes to determine the answer to that. Jumble things around.
