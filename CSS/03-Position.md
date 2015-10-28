# Positioning

## Type of position
Elements can be positioned relatively, absolutely or fixed. Default positioning is static and does nothing.

* `relative` position moves element based on it's inital position.
* `absolute` position moves element based on it's parent that has position set as relative.
* `fixed` position places element based on the viewport.

Absolute position and fixed position also remove them from the DOM concerning the flow of elements. That means browser renders everything like they don't exist.

Once type of positioning is set we use properties: `top`, `bottom`, `left`, `right`.

```css
.container {
 	position: relative;
}

.container .box-1 {
 	position: absolute
 	top: 10px
 	left: 50px;
}

.container .box-2 {
 	position: relative
 	bottom: 30px
 	right: 40px;
}
```

## Z-Index
Z-index directs what is in front when two elements overlap. For it to work position type must be specified otherwise it defaults to `z-index: 0`.

## Floats
By default elements are placed beneath the one before. To change that behaviour use floats.

* `float: left` floats it to left side 
* `float: right` floats it to right side

Elements after floated ones are than placed in between. Usually we don't want that and to prevent it use `clear: both`.

```css
.box-1 {
  float: left;
}

.box-2 {
  float: right;
}

.box-3 {
  clear: both;
}
```