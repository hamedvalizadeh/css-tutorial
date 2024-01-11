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



### grid

it is one of display property to layout the desired area of the web page inside squares or rectangles between network of lines cross each others.

say we have a tag of type ((main)) in our page, and want it to has been divided to 3 columns that the third column is 250px wide and 2 first columns are equally divided in the remaining width of the page.

also there is a 20px gap between cells, and we want to assign our header to the top section, footer to the bottom section, author info bellow the header and to the most right side of the page, content of the page bellow the header and to the most left of the page, aside info bellow the author info and to the most right side of the page, play info under content section and to the most left of the page, a free cell between paly info and aside info respectively.

for this purpose the css would be as follow: 

```css
main {
  display: grid;
  grid-template-columns: repeat(2, minmax(auto, 1fr)) 250px;
  gap: 20px;
  grid-template-areas:
    "header1  header1  header1"
    "content1 content1 author1"
    "content1 content1 aside1"
    "plays1   .        aside1"
    "footer1  footer1  footer1";
}
```



#### grid-template-columns

this property divide the page horizontally to columns defined for it as value,;examples:

- grid-template-columns: repeat(2, minmax(auto, 1fr)) 250px
  - 3 columns that the third column is 250px wide and 2 first columns are equally divided in the remaining width of the page.
- grid-template-columns: 2fr 1fr
  - 2 columns total, first column occupy 2 parts from 3 parts of the page and the second one occupy 1 part.

if it is not set explicitly, the browser will specify by its own decision.     



#### grid-template-areas

to place elements on grid cells explicitly we use this property. by this property we name grid cells, and then use these names and grid property of the desired elements. like bellow:

```html
<header style="grid-area: header1;">...</header>
<article style="grid-area: content1;">...</article>
<aside style="grid-area: aside1;">...</header>
<section class="author-details" style="grid-area: author1;">...</section>
<section class="plays" style="grid-area: plays1;">...</section>
<footer style="grid-area: footer1;">...</footer>
```

 



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

  

***

# list-style

with this property in hand we can change the symbol before ((li)) element of ((ul)) element. there are some pre-defined values such as ((circle)), ((lower-alpha)), and some others, but if we need our custom we can use at-rule ((counter-style)). this at-rule has following properties:

- symbols
- system
- suffix



following is an example that will use hot coffee emoji as symbol with an space prefix before ((li)) that repeats for all items:

```css
@counter-style my-coffre-list-style {
  symbols: "\2615";
  system: cyclic;
  suffix: " ";
}

article ul {
  list-style: my-coffre-list-style;
}
```



***

# list-style-image

instead of using at-rule ((counter-style)) to customize our list style, we can use and image instead instead. but we have not the same control over our style in comparison with ((counter-style)). 



***

# filter

this property is used to apply filter on images like what is common in programs like photoshop or Instagram. there are following functions as a value for this property:

- contrast
- graystyle
- invert
-  saturate
- sepia
- hue-rotate
- drop-shadow
- blur
- big
- brightness
- opacity



following are example for some of functions above:

```css
.contrast{
  filter: contrast(200%);
}

.grayscale{
  /*Full greyscale*/
  filter: grayscale(100%);
}

.invert{
  filter: invert(100%)
}

.saturate{
  /*200% saturation*/
  filter: saturate(200%)
}

.sepia{
  filter: sepia(100%)
}

.hue-rotate{
  filter: hue-rotate(90deg)  
}

.drop-shadow{
  filter: drop-shadow(4px 5px 4px #444);
}
```



**Caution:** this functions could be used together with a space as separator to form combination of filters. as follow:

 

```css
.test{
  filter: contrast(175%) brightness(103%);
}
```



**Caution:** applying filters has negative impact on webpage performance. so if there are a lot of image in the webpage that all need a kind of filter, it is suggested to pre-process them and not to use filter property for all of them.  
