Setup React Development Environment using Yarn and Webpack.

This project is created from the following pages:
https://codeburst.io/yet-another-beginners-guide-to-setting-up-a-react-project-part-1-bdc8a29aea22

and

https://codeburst.io/yet-another-beginners-guide-to-setting-up-a-react-project-part-2-5d3151814333

```
install yarn
mkdir react-project && cd react-project
yarn init (setup project info)
yarn add react react-dom
yarn add -D webpack webpack-dev-server webpack-cli
```

create index.html and index.js
- Note: the webpack-web-server has bundle.js as main.js

Add the following into the package.json
```
  "scripts": {
    "start": "webpack-dev-server index.js"
  },
```
 
```
 yarn add -D @babel/core @babel/preset-react
```

Create webpack.config.js to control babel

```
const path = require('path');
const config = {
  entry: [
    './index.js',
  ],
  module: {
    rules: [
      {
        test: /\.js$/,
        loaders: [
          'babel-loader',
        ],
        exclude: /node_modules/,
      },
    ],
  },
};
module.exports = config;
```

```
yarn add -D babel-loader@8.0.0-beta.0
```

Create bable configuration.
```
{
  "presets": ["@babel/preset-react"]
}
```

modify index.js to contain JSX

```
import React from 'react';
import ReactDOM from 'react-dom';
ReactDOM.render(
  <h1>Hello World with JSX, Babel and Webapck</h1>,
  document.getElementById("root")
);
```

Note: to generate main.js for distribution, use the following command.
```
yarn webpack-cli -d
```
