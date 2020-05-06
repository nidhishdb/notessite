# HTML and CSS

<style>a{color:#997;background-color:black;padding:4px;border-radius:3px;}
/* body{background-color:darkgray} */
</style>

<img src="https://i.udemycdn.com/course/750x422/792484_cc98_3.jpg" width=300 style="border-radius:4px">

>I think it is possible for ordinary people to choose to be extraordinary - *Elon Musk*
- - - -
## CSS
[30 CSS Selectors to Memorize](https://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048)

centering element: margin: 0px auto;

max-width: this property sets the maximum width of the element, if the content is larger than the maximum width, it will automatically change the height of the element.

#### backgroundimage:https://css-tricks.com/perfect-full-page-background-image/

#### [Animate.CSS - animation library to add quick animations](https://daneden.github.io/animate.css/)

#### CSS Grids: [cheatsheet](http://grid.malven.co/)
https://css-tricks.com/snippets/css/complete-guide-grid/

https://www.freecodecamp.org/news/the-ultimate-guide-to-css-flex/

creating grids:

`grid-template-columns: repeat(auto-fill,minmax(100px,1fr));`

`grid-auto-rows:100px;` this is done to implicitly set the rows

`grid-auto-flow:dense;` to place items wherever space is available and not leave whitespaces. By default the value is `row`

`justify-items` is used to justify items inside the container.   
`align-items` is used to align items inside the container.

`justify-self` is used to justify the individual item inside the container.  
` align-self` is used to align the individual item inside the container.

#### justify-content and align-content

`justify-content` property is used to align the whole grid inside the container.  
`align-content` property is used to vertically align the whole grid inside the container. Both above properties take values:
* center
* space-around
* space-evenly
* space-between
* start
* end




        
### Flexbox:
https://css-tricks.com/snippets/css/a-guide-to-flexbox/

[flexbox cheatsheet](https://darekkay.com/dev/flexbox-cheatsheet.html)        

[flexbox game](http://flexboxfroggy.com)

Flexbox Notes: 

#### Flex direction:
Defines the direction of the main axis.

It takes the values:
* row
* row-reverse
* column
* column-reverse

By default all element are set `flex-direction` property to row,which makes all elements to be displayed from left to right.

* we can change the `flex-direction` property to column which aligns items from top to bottom.
* When it is set to column the property `justify-content` acts like `align-items` property and vice versa.

#### justify-content:
`justify-content` property to justify elements horizontally (main axis). It takes values:
* flex-start
* flex-end
* center
* space-around
* space-between
* space-evenly 

#### align-items:
`align-items` property to align items to align items on vertically (cross axis)

It takes values: 
* flex-start
* flex-end
* center
  
#### align-self:
The `align-self` property aligns the flex item along the cross axis,overiding the `align-items` value.

It takes the values:
* flex-start
* flex-end
* center
* baseline
* stretch

side note: To make the container responsive vertically we set it's `height` to 100% as well as the html,body 's `height` to 100% as well.

#### align-content:

The `align-content` property modifies the behavior of the `flex-wrap` property. It is similar to `align-items`, but instead of aligning flex items, it aligns flex lines.

It takes values:
* flex-start
* flex-end
* center
* stretch
* space-between
* space-around
* space-evenly

Note: There must be multiple lines of items for this property to have any effect!

#### flex-wrap:
Specifies whether flex items are forced on a single line or can be wrapped on multiple lines.

If the container is smaller than the element's width, then by default flexbox will not push the items to the next row. It will rather try to fit the items in the space available in the container by shrinking the item's width.

We can change this behaviour with the `flex-wrap` property.
It takes the values:
* nowrap (default)
* wrap
* wrap-reverse

#### flex-flow:
 Shorthand property for `flex-direction` and `flex-wrap`

Usage: flex-direction flex-wrap

#### flex property:
flex property:
The `flex` property sets the flexible length on flexible items.

The `flex` property is a shorthand property for:

* flex-grow
* flex-shrink
* flex-basis

```css
flex: 1;
```
is a shorthand for writing
```CSS
flex-grow:1;
flex-shrink:1;
flex-basis:0;
```

The second and third parameters (flex-shrink and flex-basis) are optional.

Another Example:
```CSS
flex: 2 1 200px;
```
is same as doing,
```CSS
flex-grow: 2;
flex-shrink:1;
flex-basis:200px;
```

The `flex-grow` property specifies how much the item will grow relative to the rest of the flexible items inside the same container.

The `flex-shrink` property determines how much the flex item will shrink relative to the rest of the flex items in the flex container when there isn't enough space on the row.

The `flex-basis` property specifies the initial length of a flexible item.

#### order property:
Specifies the order of the flex item 

Flex items are displayed in the same order as they appear in the HTML document by default. The `order` property can be used to change this ordering.

default `order` value is 0. positive values move the element to the right and negative values move the element to the left.

#### media queries
https://css-tricks.com/snippets/css/media-queries-for-standard-devices/
