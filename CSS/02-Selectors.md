# Selectors

## IDs
With ID selectors we can select any HTML element with that ID.

```css
#id-name {
  background-color: #67812F;
  color: #45F2C8;
  text-align: justify;
}
```

## Classes
With Class selectors we can select any HTML element with that Class.

```css
.class-name {
  font-size: 20px;
  font-weight: 600;
  font-family: Avenir;
}
```

## Grouping Selector
Selectors can be grouped by placing commas between them like this.

```css
h1, h2, h3, h4 {
  font-size: 20px;
  color: #6B90FA;
}
```

## Descendant Selector
We can also select elements inside some other elements. This next code snippet changes paragraph styles inside first part of an article.

```css
article .first-part p {
 	color: #AB80FF;
 	font-size: 10px;
}
```

## Advanced Selectors

### Child Selectors
It has the same functionality as descendant selectors but it's more specific. It selects the immediate child of the element specified.

```css
.dad > .child {
  background-color: #457879;
  font-size: 20px;
  margin: 10px 20px;
}
```

### Attributes Selector
Sometimes we want to select some elements with certain attributes.

```css
input[type="text"] {
  padding: 10px;
 	background-color: #A8B3CF;
}
```

### Sudo Selector
Sudo selectors allow us to select certain element when in some state.

```css
a:link, a:visited {
  color: #ABCDEF;
 	text-decoration: none;
}

a:hover, a:active {
 	color: #123456;
 	text-decoration: underline;
}
```

### Adjancent Sibling Selector
It selects an element that is a sibling (not child) and it comes directly after it.

```css
p + h2 {
  margin-top: 10px;
}
```

## General Sibling Selector
It works the same as adjancent selector as it selects element's siblings that follow after it. They doesn't have to come immediatley after it.

```css
.post h1 ~ p {
  font-size: 13px;
}
```