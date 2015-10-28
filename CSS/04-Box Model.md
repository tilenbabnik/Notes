# Box Model

## Box Styles

Margin and Padding can be defined in four different ways.

* One value affects every side.
* When two values are used, first one is for top and bottom and second for left and right.
* When there are three values, first is top, second is for left and right, third is for bottom.
* Four values account for each side. Use clockwise rule. First is top, second is right, third is bottom and fourth is left.

```css
nav {
 	margin: 10px;
 	margin: 20px 15px;
 	padding: 5px 10px 20px;
 	padding: 20px 10px 15px 5px;
}

header {
 	margin-top: 10px;
 	margin-bottom: 20px;
 	margin-left: 15px;
 	margin-right: 5px;
}
```

## Border Styles
Borders can be of type `solid`, `dotted`, `dashed` and `double`. We can set the width and the color of it. Each border side can be set individually. To specify only one side of the border use `top`, `bottom`, `left`, `right`.

```css
footer {
 	border-top-style: solid;
 	border-top-width: 4px;
 	border-top-color: #897AB1;
}

header {
  border: solid 1px #152763
}
```

### Border Radius
To round of the corners use `border-radius`.
To make a circle use `border-radius: 50%.