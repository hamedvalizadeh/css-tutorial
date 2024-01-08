# Animation

CSS animation module allows us to animate properties. there are some properties to control aspects of animation as follow:

- animation-delay
- animation-direction
- animation-duration
- animation-fill-mode
- animation-iteration-count
- animation-name
- animation-play-state
- animation-timing-function



***

# Keyframe

represents the most important changes in your animation. it is from ((at-rules)) category. to define one we should use ((@)) symbol. to define css style for each frame we can use ((%)) to indicate in which progress percentage of the animation the  the desired style to be applied. also instead of ((0%)) we can use ((from)) and instead of ((100%)) we can use ((to)).

in the following example we define a keyframe named ((testFrame)) and use it in a ((div)) element:

```css

@keyframes testFrame{
    0% { css-styles ... }
    50% { css-styles ... }
    100% { css-styles ... }
}

div{
    animation-name: testFrame,
    animation-duration: 3s,
    animation-iteration-count: 10
}
```



***

# transform-origin

it sets the origin of transformation. the value could be one of following types:

- percentage
- length
- keyword
  - top
  - right
  - left
  - bottom
  - center 



