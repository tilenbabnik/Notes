# Basics

## Styling links
Links can be styled in four different states. Usually we style visited the same as a default state.

* link
* visited
* hover
* active

## Font Styles
To change the way font looks use `font-family`. Color of the font can be changed with `color`. Use `font-size`for sizing of the font.

````css
h1, h2, h3 {
	font-family: Helvetica;
	font-size: 16px;
	font-style: italic;
	font-weight: 400;
	letter-spacing: 1px;
	line-height: 1.3;
	word-spacing: 10px;
	color: #67FAB2;
	text-align: center;
	text-indent: 80px;
	text-decoration: line-through;
	text-tranform: capitalize;
}