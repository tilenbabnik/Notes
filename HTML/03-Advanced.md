# Advanced

## Iframe
Iframe is an inline frame and it's used to display webpages as an embed. Link can also target specific iframe in target attribute.

```html
<iframe src="demo_iframe.htm" name="iframe_a"></iframe>
<a href="http://www.w3schools.com" target="iframe_a">W3Schools.com</a>
```

## Scripts
Scripts can be written within HTML document or can link to external Javascript file.

```html
<script>
  document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>

<script src="addons/prism/prism.js"></script>
```

## Search Engine Optimization
A few meta tags to help search engine index the site.

```html
<meta name="description" content="Description of the content on the website.">
<meta name="keywords" content="words,that,people,will,search,for">
<meta name="author" content="Urban Cvek">
```

## Video
To implement video on a webpage use video tag. Or you can use youtube to play videos on your site. Use iframe tag for this.

```html
<video>
  <source src="videos/harrypotter.mp4" type="video/mp4">
</video>

<iframe width="420" height="315" src="http://www.youtube.com/embed/XGSy3_Czz8k?autoplay=1"></iframe>
```

## Audio
To play audio use audio tag.

```html
<audio>
  <source src="music/50cent.mp3" type="audio/mpeg">
</audio>
```