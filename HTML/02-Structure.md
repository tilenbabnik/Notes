# Structure

## Spans
Span are used to wrap something that is an inline element.

```html
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. <span class="green-text">Laudantium eos iste laborum assumenda ea</span> sed, quo doloremque non neque inventore quod ipsa, magnam at blanditiis facilis possimus repellendus error debitis!</p>
```

## Divs
Divs are containers for other content. Used for CSS styling.

```html
<div class="main-container">
  <div class="left-column">
    <h1>Naslov 1</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
  </div>
    
  <div class="left-column">
    <h2>Naslov 2</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
  </div>
</div>
```

## IDs
Can be used only once per page

```html
<p id="fancy">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laudantium eos iste.</p>
```

## Classes
Can be used on multiple elements

```html
<p class="bossy">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laudantium eos iste laborum assumenda ea sed, quo doloremque non neque inventore quod ipsa, magnam at blanditiis facilis possimus repellendus error debitis!</p>
```

## Display Types
Any element can have certain display type applied by styles. There are others display types like none, table, grid and flex.

### Block
Block level elements start a new line and they divide content. It can contain other block or inline elements. The example is the paragraph, any heading and any div.

### Inline
Inline elements don't start a new line. It can only contain other inline elements. They cannot take margin, padding, width and height styles. An example is an anchor tag that wraps some word and turns them into a link.

### Inline-Block
Inline-block elements are displayed and behave just like inline elements but can also take width, height, margin and padding styles. By default only images and buttons are styled as inline-block elements.

## Special Tags
More tags that have some meaning but are a meant for coder's understanding.

* header
* footer
* nav
* main
* section
* article
* aside
* figure