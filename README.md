# node-learning

## start the first Hello World
1. Create a folder, open it with Visual Studio Code, type `npm init` in terminal.
2. Type 'npm install --save express' its will generate the dependency automatically.
3. put the code below to app.js or index.js.
```javascript
const express = require('express');
const app = express();
const port = 5000;
app.listen(port, () => {
  console.log(`Server started on port ${port}`);
});
```
4. run `` node app.js

## carete a route
```javascript
app.get('/', (req, res) => {
  res.send('INDEX');
});
```

## set up the server to demon user
```bash
npm install -g nodemon
npm root -g
nodemon # run command
```


## Handlebars
* Install `npm install express-handlebars --save`
