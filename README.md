## supervisor-hot-reload

[supervisor](https://github.com/petruisfan/node-supervisor) + [hot-reload](https://github.com/nswbmw/proxy-hot-reload).

### Install

```sh
$ npm i supervisor-hot-reload -g
```

### Example

**app.js**

```js
'use strict';

const express = require('express');
const app = express();
const user = require('./user');

app.get('/', function (req, res) {
  res.send(user);
})

app.listen(3000);
```

**user.js**

```js
module.exports = {
  id: 1,
  age: 19
}
```

```sh
DEBUG=proxy-hot-reload supervisor-hot-reload app.js
```

If you modify user.js, it will hot reload user.js. If you change app.js, it will restart server.

### Options

see [supervisor](https://github.com/petruisfan/node-supervisor#node-supervisor--).

### License

MIT