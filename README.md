# basicwebpackapp

Complete steps to create a Webpack and can use for any Anugular/React/VueJS app

npm init --yes  --> To create empty package.json file

npm install --save-dev webpack@4.17.2

Add file .gitignore and type text node_modules

npm install --save-dev webpack-cli@3.1.2 webpack-dev-server@3.1.7

npm install --save-dev @babel/core@7.0.0

Npm install --save-dev @babel/node@7.0.0 @babel/preset-env@7.0.0 @babel/preset-react@7.0.0 @babel/register@7.0.0

Add a new file .bablerc to define how .jsx and ES6 should be handled and add this content
{
    "presets": [
        ["@babel/preset-env", {
            "targets": {
                "node": "current"
            }
        }],
        "@babel/preset-react"
    ]
}

Add this in package.json inside script tag
    "start": "webpack",


Add a new file webpack.config.js to define how our app should be bundled and add this content

const path = require("path");
// export default {
module.exports = {
    mode: 'development',
    entry: path.resolve(__dirname, `src`,`app`),
    output: {
        path: path.resolve(__dirname,'dist'),
        filename: 'bundle.js',
        publicPath: '/',
    }


Add a new folder src / new folder app and a file index.js
Type 
console.log('Hello World!!!');


Add this later in webpack.config.js

,
    resolve: {
        extensions: ['.js','.jsx']
    },
    devServer: {
        historyApiFallback: true
    },
    module: {
        rules: [{
            test: /\.jsx?/,
            loader:'babel-loader'
        }]
    }
}


Add this in package.json file
    "dev": "webpack-dev-server --open"


npm install --save-dev babel-loader@8.0.2


Type npm run dev now![image](https://user-images.githubusercontent.com/10427100/114543006-3db0c100-9c76-11eb-951e-89e0c09a68e2.png)
