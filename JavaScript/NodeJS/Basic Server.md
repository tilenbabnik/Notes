First we have to require express package.

```js
var express = require('express');
```

Then we initialize the app as express object.

```js
var app = express();
```

We can then define routes with `get`, `post`, `put` and `delete` methods called on app.

```js
app.get('/', function(req, res) {
	res.send('Hello World!');
});
```

Finally we start the server and specify the port.

```js
app.listen(3000);
```