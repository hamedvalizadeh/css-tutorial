# SVG

Scalar vector graphic.

#### viewport

is a part of SVG image that is visible to the user.

 

following html code is an example of SVG without viewport 

```html
<svg style="border: 1px solid black;">
  <rect width="600" height="200" x="50" y="50" style="color: red;" />
</svg>
```



<svg style="border: 1px solid black;">
  <rect width="600" height="200" x="50" y="50" style="color: red;" />
</svg>



following html code is an example of SVG with viewport 

```html
<svg width="100" height="100" style="border: 1px solid black;">
  <rect width="600" height="200" x="50" y="50" style="color: red;" />
</svg>
```



<svg width="100" height="100" style="border: 1px solid black;">
  <rect width="600" height="200" x="50" y="50" style="color: red;" />
</svg>



#### viewbox

it sets the position, height and with of graphic inside viewport. it is specified by attribute ((viewbox)). this attribute has four parameter that are x, y, width, and height respectively. x and y are user coordinates of the upper left corner, and last 2 parameters are lower right corner of the user coordinates.



in the following example the SVG has view port of 50 pixel width and 50 pixel height, that just a picture of size 20 pixel width and 30 pixel of height starting from x = 0 and y = 0 are visible to the user.  

```html
<svg width="50" height="50" viewbox="0 0 20 30">
...
</svg>
```







***

# Shapes in SVG

- rect
- circle
- ellipse
- line
- polyline
- polygon
- path
  - to draw irregular shape.

