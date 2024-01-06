# Grid

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

 