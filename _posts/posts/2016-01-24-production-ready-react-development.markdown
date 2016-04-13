---
layout: post
category: posts
title:  Production ready ReactJs development
date:   2016-01-24 11:16:25 +0530
tagline: "Setting up production ready ReactJs development environment"
permalink: /post/production-ready-reactjs-development/
---
[When I started writing React apps]({% post_url 2015-12-11-a-day-with-reactjs %}){:target="_blank"}, the first issue I realized that it was taking long steps to build my app for production. This article explains how I solved this basic problem. Before you start thinking React in production, the article expect that the latest version of nodejs and npm is already installed.

If these tools you have not installed and you are using Ubuntu, you can follow commands given below to install these tools-

    # installing nodejs
    $ sudo apt-get install nodejs
    $ sudo ln -s `which nodejs` /usr/bin/node

    # installing npm and serve
    $ sudo apt-get install npm
    $ sudo npm install -g serve


### Setting up project

Go to your project directory and create a package.json by issuing following command-

    $ npm init

Which will create a **package.json** file after asking few basic questions from you. This file keeps meta information about our project. This file is used to give information to npm that allows it to identify the project as well as handle the dependencies.

Before div-in into writing React component, we will setup our directory structure. Following is the directory structure, which I follow-

    /project/
        package.json
        components/

Here in **components** directory, we keep our React components definitions. We can divide our view into logical components where each logical components also can be sub-divided and so on. In the root of components directory, we will have a file with name App.jsx which will be the root component to be loaded in our app. Finally our directory structure will look like following-

    /project/
        app.css
        index.js
        index.html
        package.json
        components/
            App.jsx
            component1/
                Component1.jsx
            component2/
                Component2.jsx
                childComponent/
                    childComponent.jsx

My **index.js** file looks like below-

    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './components/App.jsx';

    ReactDOM.render(
        <App />,
        document.getElementById('app')
    );

Here we are loading our app into the element with id **app**. Which you can locate in **index.html** file. Below are the inital sources of **index.html** file.

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title>Codingdash</title>
        <link rel="stylesheet" href="app.css">
        <script type="text/javascript" src="app.js"></script>
    </head>
    <body>
        <div id="app"></div>
    </body>
    </html>

In the source of HTML file, you can find out that we are including **app.js** but still in our app structure we have not shown this file. In below section we will discuss how this **app.js** file will be generated.


### Setting up build process

In our build process, we will use babel to transform our jsx files into javascript and to bundle the source into one file app.js. Here it's not necessary to build or bundle source into single file but for small apps, it doesn't make sense to create multiple source files.

There are couple of tools which we can use to setup our process, such as [browserify](http://browserify.org/){:target="_blank"} and [webpack](https://webpack.github.io/){:target="_blank"}. These tools are very similar and in many case you can use anyone of them and will get the same result. But there are some feature which is offered by webpack but not by browserify. You can readup an interesting article about browserify and webpack differences [here](http://blog.namangoel.com/browserify-vs-webpack-js-drama){:target="_blank"}.

Here we will use webpack. Below is the quick overview of how we'll use webpack-

    $ webpack <inputfile> <outputfile>
    $ webpack ./index.js ./app.js

Webpack will look into the input file, and it will build a dependency graph based on the require or import statements. After the webpack has created complete dependency graph, it will run optionaly build process on the dependency graph. In our case we want it to pass our file's content to babel, so that it can trasform our ES2015 code and JSX file code into ES5 code. The webpack will bundle our transformed files into single output file, which will be stored in **app.js**.

Now we will install webpack by issuing following command-
    
    $ sudo npm install webpack -g

Earlier we have used command-line to tell webpack the input and output file. But generally we create a config file, which will be used by webpack to understand input and output file and any other transformation operation which you want webpack to do. The config file should be named as **webpack.config.js**, this file should export configuration object. Below is the sample configuration file-

    var webpack = require("webpack");
    module.exports = {
        entry: './index.js',
        output: {
            path: __dirname,
            filename: 'app.js' 
        },
        module: {
            loaders: [
                {
                    test: /\.jsx?$/,
                    loader: 'babel-loader',
                    exclude: /node_modules/
                }
            ]
        },
        plugins: [
            new webpack.optimize.UglifyJsPlugin({
                compress: {
                    warnings: false
                }
            })
        ]
    }

Here from the field names you can understand the meaning of the property. For more details on configuring webpack, you can follow [this documentation](https://webpack.github.io/docs/configuration.html){:target="_blank"}.

Here the point to note is that in configuration object, while adding loader we have specified test property to pick only **.jsx** files and pass it to babel, and in plugin property we are telling the webpack to compress the resulted javascript file.

Before we run webpack, we need to install babel-loader and other dev dependencies. By issuing below command we can install these dependencies-

    $ npm install react react-dom webpack babel-loader@5.3.3 --save-dev

Now we can run webpack command to build our jsx code production ready, and you can start writing components.