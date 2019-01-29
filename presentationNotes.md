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

# same blue slide

- so you need a trigger
- some kind of animatable property to change something
- some kind of transition to define how you're going to move it, without it, it'll be a jump-cut

# All equivalent

- So last week I immediately showed you the short-hand notation
- This week I'll show you the long-hand notation.
- just like other CSS props that have long hand vs short hand, transition is like that
- when you use transition, you have a choice between 5 to 6 different props
- only 1 of them is required, the rest are optional

# transition: all 1s

- transition: all - yes you can say this, which forces the browser to watch for any property change at all
- good or bad? It's bad in terms of production (learning purposes okay)

# transition: all 1s codepen

- it's bad because #1 - read it
- do codepen example
- uncomment the border statement - let's say another programmer comes along, or you some future time later and you forgot what you did previously, and you wanted to add another property so there should be a black border by the time it finishes
- do you see what happened?
- so the border itself is also being animated, but that wasn't your intention, yet it's being controlled by transition all
- so that's one use-case scenario of why you don't want transition: all

# Nabors quote

- #2 use-case scenario
- read it
- everyone here has probably seen jank where the animation is so jerky as if processing power is not fast enough
- that's what may be happening when you use transition: all

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

# easing

- as you remembered from 12 principles of animation
- this diagram should remind you of ease-in / ease-out
- read it
- ease-out = slow-out, or on out it'll slow down

# transition-timing-function Values

- here are some of the preset values
- linear - makes things look mechanical, nothing moves linear in the real world; that's why people use other functions
- ease-in = acceleration
- ease-out = deceleration
- ease-in-out = the fast part is in the middle
- steps = we'll get into that later
- cubic bezier - this is where you make your custom functions
- I'll introduce you to 3 websites here
- easings.net - if you hover over any one of these, it gives you a red indicator that shows how fast it moves
- which of these looks like that rocket ship from treefrog.ca where it started off really slow then exploded
- for easeinElastic see how it went below the line - compare rocket ship when it lands (you know cubic bezier used)
- css transitions chart - shows a nice race of all the preset values
- so all start and end at same time, difference is the curve, and that's what makes your animations look more life-like
- notice awesome is using anticipation as it tilts first then goes
- cubic-bezier.com - you can experiment with your own curves; make your own curve, press go, pink is yours, blue is a default, and if you like it, copy/paste value to your code

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

# Simple transition

- Do codepen example for button

# Multiple transition - red

- if you have 2 transitions, here's one way (the bad way = highlighted in red) to write it
- you can actually list all the different props separated by commas
- however, every single prop below that (in terms of column), make sure this duration refers to colour, this duration refers to transform etc.
- and for transition-delay, you have to substitute a 0 if there isn't a delay for color for example

# Multiple transition - green

- the better way is to separate by commas, each prop along with its values together on one line
- so this is equivalent of our previous slide
- that is how you do multiple transitions

# CSS Transitions are good...

- read it

# Submit in-class 4

# transition-timing-function Values

- so here again are the different preset timing functions, but now we'll focus on steps which is a whole different category. In the past I taught this in one class...
- steps belongs in the same category as these other timing functions
- read it

# transition-timing-function: steps

- read it

# Why sprites?

- think back to the days of flipbook, maybe you've created one yourself, that's what we're talking about
- back to the traditional frame-by-frame animation drawn by hand
- so instead the browser to easily interpolate / tween between the from state and to-state, rather steps can take your png file (for example) and it's going to move frame by frame very fast
- which principle of animation does this remind you of?

# straight ahead pose

- It is this one

# val quote

- read it

# exporting images

- I won't be going how to make sprite images (in Adobe Illustrator for example) but I'll be showing what you do with them once created
- here are just a few tips if you happen to be exporting images from your software
- read it
- 1. so basically you'll end up with a large image (click example sprites link to show class where each row is something you can transition frame by frame)
- 4. if you want to make your animation smooth, then create more frames, but at the cost of larger file size; it's a balancing game

# steps(x)

- here is a visual, just like a flipbook
- this steps function, you insert a number, which represents the number of frames in your png file for example.
- read it
- in the past where we used a traditional ease, you'd start on from state, and the browser automatically gradually interpolates everything to the final to-state.
- steps jump cuts
- read bottom sentence
