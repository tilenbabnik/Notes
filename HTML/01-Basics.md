# Basics

## Basic Structure of HTML
Every HTML page needs a few things.

* doctype declaration
* html, head and body tag
* title
* a few meta tags
* link to CSS styles document
* language declaration

And this is how it should look like in code.

```html
<!DOCTYPE HTML>
<html lang="en">
  <head>
    <title>Sample Web Page</title>
    
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
    
    <link rel="stylesheet" href="styles.css">
  </head>
  
  <body>
    
  </body>
</html>
```

## Text Tags

### Headings
Headings go from Heading 1 to 6. Heading 1 being the most important should be used only once on the page. Others should be used meaningfully. For example Heading 3 should be a subheading of Heading 2.

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 2</h3>
<h4>Heading 2</h4>
<h5>Heading 2</h5>
<h6>Heading 2</h6>
```

### Paragraphs
Paragraph should be used for any text on the page. For semantics emphasis and strong tags can be used. Line break is used to start a new line.

```html
<p>Nullam id dolor id nibh <em>ultricies vehicula ut id elit.</em> Morbi leo risus, porta ac consectetur ac, vestibulum at eros. 
<br>
Etiam <strong>porta sem malesuada magna</strong> mollis euismod. Donec sed odio dui. Aenean lacinia bibendum nulla sed consectetur.</p>
```

### Preformatted Text
Sometimes we want to format text with spaces and line breaks. Like a poem. We have to put everything inside pre tag like this.

```html
<pre>
  <p>
    My Bonnie lies over the ocean.

    My Bonnie lies over the sea.

    My Bonnie lies over the ocean.
  </p>
</pre>
```

To write code inline in HTML document use code tag.

```html
<pre>
  <code>
    var oseba:String = "Urban"
    
    func legendiziraj(ime:String) -> String {
      return "\(ime) je legenda"
    }
    
    legendiziraj(oseba)
  </code>
</pre>
```

### Special Formatted Text
Text can be formatted to strong or italic without special meaning, we can also style it as marked, deleted, inserted or even as a subscript or superscript.

```html
<b>Strong text</b>
<i>Italic text</i>
<mark>Marked or highlighted text</mark>
<del>Deleted text</del>
<ins>Inserted text</ins>
<sub>Subsripted text</sub>
<sup>Superscripted text</sup>
```

## Hyperlinks
Hyperlinks are basicly shortcuts to somewhere. It can be on the page, some other page are any website there is. The link destination is specified in the href attribute.

```html
<a href="http://www.google.com">Google</a>
```

## Lists

### Ordered Lists
Numbered lists starting from 1.

```html
<ol>
  <li>Urban</li>
  <li>Klemen</li>
  <li>Rok</li>
  <li>Miha</li>
  <li>Gaja</li>
</ol>
```

### Unordered Lists
Not numbered. Commonly used for navigation.

```html
<ul>
  <li>Mleko</li>
  <li>Kruh</li>
  <li>Sir</li>
  <li>Marmelada</li>
  <li>Meso</li>
</ul>
```

## Images
Source property gives the location of an image. Alt attribute is a description for screen readers.
Images can be nested inside figure element along with figcaption for further explanation.

```html
<img src="img/background.jpg" alt="Rocky Mountains from a plane">

<figure>
  <img src="pic_mountain.jpg" alt="The Pulpit Rock">
  <figcaption>The Pulpit Rock, Norway</figcaption>
</figure>
```

## Tables
Table has rows. Top row should be represented with Table heading tag. Other cells are represented with Table data tags.
Use colspan attribute for cells that span multiple columns or rowspan for cells that span multiple rows.

```html
<table>
  <tr>
    <th>Name</th>
    <th>City</th>
    <th colspan="3">Age</th>
  </tr>
  
  <tr>
    <td>John</td>
    <td rowspan="2">Vancouver</td>
    <td>30</td>
  </tr>

  <tr>
    <td>Tiffany</td>
    <td>Toronto</td>
    <td>25</td>
  </tr>
</table>
```

## Forms
Forms are used to collect data.

```html
<form action="action-page.php" method="post">
  <fieldset>
    <legend>Information about form</legend>
    
    <label for="name">Name</label>
    <input type="text" placeholder="Enter your name">
    
    <label for="email">Email</label>
    <input type="email" placeholder="Enter your email">
    
    <label for="password">Password</label>
    <input type="password" placeholder="Your password">
    
    <label for="gender">Gender</label>
    <input type="radio" name="gender"> Male
    <inputtype="radio" name="gender"> Female
    
    <label for="computer">Type of computer</label>
    <input type="checkbox"> Laptop
    <input type="checkbox"> Desktop
    
    <label for="age">Age</label>
    <select>
      <option>10-18</option>
      <option>19-29</option>
      <option>30+</option>
    </select>
    
    <label for="biography">Biography</label>
    <textarea></textarea>
    
    <input type="submit" value="Save my info">
    <input type="reset" value="Reset">
  </fieldset>
</form>
```

## Semantical Tags
There are some tags that have a meaning for a computer. Usually are good for SEO.

* address
* time
* quote
* blockquote
* abbreviation

```html
<address>
Jon Doe<br> 
Box 564, Disneyland<br>
USA
</address>

<time datetime="2015-08-30 13:41">Trideseti avgust 2015, devetnajst do dveh.</time>

<p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>

<blockquote cite="http://www.worldwildlife.org/who/index.html">
For 50 years, WWF has been protecting the future of nature.
The world's leading conservation organization,
WWF works in 100 countries and is supported by
1.2 million members in the United States and
close to 5 million globally.
</blockquote>

<p><abbr title="National Basketball Association">NBA</abbr> is the best basketball league.</p>
```