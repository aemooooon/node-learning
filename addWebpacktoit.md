# Add webpack to existing project


## Install webpack

1. 

> npm i webpack-cli @webpack-cli/init

2. 

> npx webpack-cli init (set dist is public/javascripts)

3. create src/index.js
4. ./node_modules/.bin/webpack

5. 

```javascript
output: {
		filename: '[name].js',
		path: path.resolve(__dirname, 'public/javascripts')
	},
```

6.
Add this to the rules section of your webpack.config.js file:

```javascript
{
    test: /\.(js|jsx)$/,
    exclude: /node_modules/,
    loader: 'babel-loader',
    query:
    {
        presets:['@babel/react']
    }
}
```


7.

> npm install --save babel-loader

> npm install --save react react-dom

> npm install --save-dev @babel/preset-react

> npm install --save-dev @babel/core @babel/preset-env


8. As a test, add this code to your src/index.js file:

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

const title = 'My Minimal React Webpack Babel Setup';

ReactDOM.render(
<div>{title}</div>,
document.getElementById('app')
);
```

You will also have to add #app to your pug file. Now, if you run webpack, and then include main.js from your public folder, everything should just work!
