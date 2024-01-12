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

# display: grid

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



#### grid-template-rows

defines the line names and track sizing functions of the [grid rows](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Row). values could be space separated combinations of following types:

- none
- [linename]
  - a id specifying a name for the line in that location. The ident may be any valid string other than the reserved words `span` and `auto`. Lines may have multiple names separated by a space inside the square brackets, for example `[line-name-a line-name-b]`.
- <length>
  - Is a non-negative length.
- <percentage>
  - Is a non-negative percentage.
- <flex>
  - Is a non-negative flex number with unit fr.
- max-content
  - Is a keyword representing the largest maximal content contribution of the grid items occupying the grid track.
- mi-content
  - Is a keyword representing the largest minimal content contribution of the grid items occupying the grid track.
- minmax(min, max)
  - Is a functional notation that defines a size range, greater than or equal to *min*, and less than or equal to *max*.
- auto
- fit-content
- repeat()
- masonry
- subgrid



```css
grid-template-rows: none;

/* <track-list> values */
grid-template-rows: 100px 1fr;
grid-template-rows: [linename] 100px;
grid-template-rows: [linename1] 100px [linename2 linename3];
grid-template-rows: minmax(100px, 1fr);
grid-template-rows: fit-content(40%);
grid-template-rows: repeat(3, 200px);
grid-template-rows: subgrid;
grid-template-rows: masonry;

/* <auto-track-list> values */
grid-template-rows: 200px repeat(auto-fill, 100px) 300px;
grid-template-rows:
  minmax(100px, max-content)
  repeat(auto-fill, 200px) 20%;
grid-template-rows:
  [linename1] 100px [linename2]
  repeat(auto-fit, [linename3 linename4] 300px)
  100px;
grid-template-rows:
  [linename1 linename2] 100px
  repeat(auto-fit, [linename1] 300px) [linename3];

/* Global values */
grid-template-rows: inherit;
grid-template-rows: initial;
grid-template-rows: revert;
grid-template-rows: revert-layer;
grid-template-rows: unset;
```







***

# display: grid (place-items)

if the property ((place-items)) set to ((center)) when the property ((display)) is set to ((grid)), will cause the content to be centered.



***

# display: multi-column layout

to have content of an element in multiple columns we can use this kind of layout. the columns count can be specified with 2 methods:

- by setting column count. in this way browser will divide the available space by the count we specified and assign the result to each column width.
  - column-count: 3;
- by setting column width. in this way browser will divide the available space by the width we specified and creates number of columns equal to the division result.
  - column-width: 150px;



**Caution:** to specify line between each column we should use property ((column-rule)), and for having margin in columns content with their surrounding we will use ((column-gap)), and to have margin to entire row we can use ((margin)):

following is an example:

```css
  .my-article {
    column-count: 3;
    column-rule: 2px solid #333333;
    column-gap: 42px;
    margin-top: 36px;
    margin-bottom: 36px;
  }

  .article-2 {
    column-width: 150px;
    column-rule: 2px solid #333333;
    column-gap: 42px;
    margin-top: 36px;
    margin-bottom: 36px;
  }
```



**Caution:** if there is an element in the content that you don't want to be in the columns, use the property ((column-span)) and set its value as ((all)). as follow:

```css
blockquote{
  column-span: all
}
```



**Caution:** sometimes images inside ((figure)) element will apart from its ((figcaption)) and split in 2 different columns in multiple-column layout. to prevent it from happening we can use ((break-inside)) property as follow:

```css
figure{
  break-inside: avoid;
}
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



***

# text alignment

to change default alignment of a text we have following properties:

- text-alignment
  - to control the alignment of the text. it has following values:
    -   right
    - center
    - left
    - end
    - start
    - justify
- text-justify
  - by this property we specify the method in which the process of justify occur.
- hyphens
  - it specify the behavior when a word break to the new line. by default nothing special happen, but if we set it to ((auto)) the a ((-)) sign will connect the broken word.



***

# float

this property will push the element to the right or left and cause text and inline elements wrap around it. it has following values:

- inline-end
- inline-start
- left
- right



***

# max-width

if an element has this property set, when the available space exceeds the amount of specified max width, the element width will not grow more than that. imagine you want to design your site for maximum of 1200px, and also don't want to support more than this width for clients that have wider monitor.



***

# container-type

Container queries enable you to apply styles to an element based on the size of the element's container. If, for example, a container has less space available in the surrounding context, you can hide certain elements or use smaller fonts. Container queries are an alternative to [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries), which apply styles to elements based on viewport size or other device characteristics.

To use container queries, you need to declare a **containment context** on an element so that the browser knows you might want to query the dimensions of this container later. To do this, use the [`container-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/container-type) property with a value of `size`, `inline-size`, or `normal`.

These values have the following effects:

- [`size`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries#size)

  The query will be based on the [inline and block](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values/Basic_concepts_of_logical_properties_and_values#block_and_inline_dimensions) dimensions of the container. Applies layout, style, and size containment to the container.

- [`inline-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries#inline-size)

  The query will be based on the [inline](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values/Basic_concepts_of_logical_properties_and_values#block_and_inline_dimensions) dimensions of the container. Applies layout, style, and inline-size containment to the element.

- [`normal`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries#normal)

  The element is not a query container for any container size queries, but remains a query container for container style queries.



Example

```css
body {
  container-type: inline-size;
}

@container (min-width: 955px) {
  ... some css styles
}
```

**Reference:** https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries



***

# set image as text background

to do this we can use property ((background-clip)) combined with ((text-fill-color)), ((background-size)), ((background)), and ((color)); following is and example that set background to the text inside ((h1)) element.

```css
h1 {
  background: url("bg-img.jpg");
  background-size: cover;
  -webkit-background-clip: text;
  background-clip: text;
  -moz-text-fill-color: transparent;
  -webkit-text-fill-color: transparent;
  color: white;
}
```



- background
  - sets the image as the background of element ((h1)).
- background-size
  - to ensure that the image fill entire space in element ((h1)), we set the value to ((cover)).
- background-clip
  - to specify which part of the ((h1)) element to clip the image as background.
  - this property is of type nonstandard properties, and should consider vendor prefix for it.
- text-fill-color
  - we set it as ((transparent)) to be able to see the image in its background.
  - this property is of type nonstandard properties, and should consider vendor prefix for it.
- color
  - we set it to show the text in some color (here white) for situation that background image fails to load.



***

# outline

this is like ((border)) property and its value is like that, but the border is outside of element.

```css
.test{
  outline: 1px solid red;
}
```



***

# outline-offset

this is used to set space between ((outline)) and element itself.

```css
.test{
  outline-offset: 3px;
}
```



***

# calc function

this function is to calculate the measurements that are not clear at design time. for example when we want to set 4px less than entire space.

```css
.test{
  height: calc(100% - 4px);
}
```



***

# not pseudo class

by the use of this class we can filter selectors. for example following selectors select all elements inside div element except ((h2)):

```css
div > *:not(h2){
   ...
}
```





