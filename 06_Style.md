# font-family

we can import our font from a CDN or from a font file located in our local host.

```css
@import url("https://fonts.googleapis.com/css2?family=Oswald:wght@400;700&family=PT+Serif&display=swap");

or

@font-face {
  font-family: KalamehWeb;
  font-style: normal;
  font-weight: 300;
  src: url("../fonts/woff2/KalamehWeb-Light.woff2") format("woff2"),
    url("../fonts/woff/KalamehWeb-Light.woff") format("woff");
}
```

 

the value for this property is the name of our font; for example it could be (( 'KalamehWeb' )) or (( 'PT serif' )). also we can use multiple comma-separated font names for when loading the first font is failed.

```css
css-selector {
  font-family: 'KalamehWeb', 'B Nazanin'
}
```



**Caution:** in comma-separated list the other fonts except the first one usually are from web-safe category of fonts. these are fonts that are available in most client devices.



***

# font-weight

it specify the thickness of the font and its value could be between 100 to 900 and also some pre-defined keys as follow:

- normal
  -  it is equivalent to 400
- bold
  - it is equivalent to 700
- bolder
  - change the font weight of the element based on the parents font weight.
- lighter 
  - change the font weight of the element based on the parents font weight.



**Caution:** if we did not load the weight that match the one specified in font-weight property, the browser will choose the closest it has access to.



***

# font-size

the unit could be some of the following:

- px
- em
  - this unit is setting the element font size relative to parent element. if parent font size is 12px and the child element font size is 0.5em, the actual font size of the child element is calculated as 6px by browser.
- rem
  - this is like em but instead of being relative to its parent, the base value comes from root element.



***

# font

we can summarize all properties related to different specifications of the font in one line as the value of font property. the value could be as bellow:

font: [font weight value] [font size value]/[line height value] [font family value]



```css
css-selector {
  font: 700 2rem/1 'KalamehWeb', 'B Nazanin';
}
```

***

# display

this property is used to change default behavior of the element. there are at-least 2 kinds of elements. inline-level and block-level. an inline element will take up exact amount of space that is needed by its content. by contrast the block-level elements like ((div)), ((p)), and ((ul)) fill the entire line it resides in unless a given a set width. there are following types of value for display property:

- inline
- inline-block
- block
- inline-flex
- flex
- grid    



***

# content

we can use this property in pseudo-element to content before and after an element. for example to set quote before and after a ((blockquote)) element, we can use it as follow:

```css
blockquote::before {
  content: open-quote;
}

blockquote::after {
  content: close-quote;
}
```

  



