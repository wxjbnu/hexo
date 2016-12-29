---
title: webpack
---

## webpack
[官方资料](http://webpack.github.io/)
[中文资料](http://webpackdoc.com/)


- webpack
- webpack-merge
- cross-env
- html-webpack-plugin
- extract-text-webpack-plugin

#### 服务端
- http-proxy-middleware
- webpack-dev-middleware
- webpack-hot-middleware
- webpack-dev-server(webpack dev server 是一個開發伺服器，內建 webpack 使用的 live reloading 功能)

#### 结构
- entry
- output
- plugins

#### loader
- css-loader
- style-loader
```javascript
//引入文件
var fs = require('fs');
var path = require('path');
var webpack = require('webpack');
var HtmlWebpackPlugin = require('html-webpack-plugin');
var ExtractTextPlugin = require('extract-text-webpack-plugin');
```

##### html-webpack-plugin
- http://www.cnblogs.com/haogj/p/5160821.html
> html-webpack-plugin-before-html-processing
html-webpack-plugin-after-html-processing
html-webpack-plugin-after-emit

##### webpack-dev-server 应用
> Webpack-dev-server十分小巧，这里的作用是用来伺服资源文件，不能替代后端的服务器，因此如果你还要进行后端开发，就要采用双服务器模式：一个后端服务器和一个资源服务器（即Webpack-dev-server)
> 参考 http://www.jianshu.com/p/8adf4c2bfa51


```javascript
module.exports={
    entry:{
        bundle:[ "./src/app.js"]
    },
    output:{
        path:__dirname,
        publicPath:"/",
        filename:"dist/[name].js"
    },
    module:{
        loaders:[
            {test: /\.html$/, loaders: ['html']},
            {test: /(\.js)$/, loader:["babel"] ,exclude:/node_modules/,
             query:{
                    presets:["es2015"]
             }
            }
        ]
    },
    resolve:{
    },
    plugins:[
         /*
         new webpack.optimize.UglifyJsPlugin({
            compress: {
                warnings: false
            }
        })
               */
    ]
}
```

```javascript
var path = require("path");
module.exports = {
  entry: {
    app: ["./app/main.js"]
  },
  output: {
    path: path.resolve(__dirname, "build"),
    publicPath: "/assets/",
    filename: "bundle.js"
  }
};

//入口
entry: [
    'webpack-dev-server/client?http://0.0.0.0:9090',//资源服务器地址
    'webpack/hot/only-dev-server',
    './static/js/entry.coffee'
]
//输出
output: {
    publicPath: "http://127.0.0.1:9090/static/dist/",
    path: './static/dist/',
    filename: "bundle.js"
}

//plugins
new webpack.DefinePlugin({
    'process.env.NODE_ENV': '"development"'
}),

"scripts": {
  "start": "webpack-dev-server --inline"//这里没有添加-hot
}
```



```javascript
module.exports = {
  entry: {
    app: './src/main.js'
  },
  output: {
    path: config.build.assetsRoot,
    publicPath: process.env.NODE_ENV === 'production' ? config.build.assetsPublicPath : config.dev.assetsPublicPath,
    filename: '[name].js'
  },
  resolve: {
    extensions: ['', '.js', '.vue'],
    fallback: [path.join(__dirname, '../node_modules')],
    alias: {
      'vue$': 'vue/dist/vue',
      'src': path.resolve(__dirname, '../src'),
      'assets': path.resolve(__dirname, '../src/assets'),
      'components': path.resolve(__dirname, '../src/components')
    }
  },
  resolveLoader: {
    fallback: [path.join(__dirname, '../node_modules')]
  },
  module: {
    loaders: [
      {
        test: /\.js$/,
        loader: 'babel',
        include: projectRoot,
        exclude: /node_modules/
      },
      {
        test: /\.json$/,
        loader: 'json'
      },
      {
        test: /\.(png|jpe?g|gif|svg)(\?.*)?$/,
        loader: 'url',
        query: {
          limit: 10000,
          name: utils.assetsPath('img/[name].[hash:7].[ext]')
        }
      },
      {
        test: /\.(woff2?|eot|ttf|otf)(\?.*)?$/,
        loader: 'url',
        query: {
          limit: 10000,
          name: utils.assetsPath('fonts/[name].[hash:7].[ext]')
        }
      }
    ]
  }
}
```

```
var rucksack = require('rucksack-css')
var webpack = require('webpack')
var path = require('path')

module.exports = {
  context: path.join(__dirname, './client'),
  entry: {
    jsx: './index.js',
    html: './index.html',
    vendor: [
      'react',
      'react-dom',
      'react-redux',
      'react-router',
      'react-router-redux',
      'redux'
    ]
  },
  output: {
    path: path.join(__dirname, './static'),
    filename: 'bundle.js',
  },
  module: {
    loaders: [
      {
        test: /\.html$/,
        loader: 'file?name=[name].[ext]'
      },
      {
        test: /\.css$/,
        include: /client/,
        loaders: [
          'style-loader',
          'css-loader?modules&sourceMap&importLoaders=1&localIdentName=[local]___[hash:base64:5]',
          'postcss-loader'
        ]
      },
      {
        test: /\.css$/,
        exclude: /client/,
        loader: 'style!css'
      },
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        loaders: [
          'react-hot',
          'babel-loader'
        ]
      },
    ],
  },
  resolve: {
    extensions: ['', '.js', '.jsx']
  },
  postcss: [
    rucksack({
      autoprefixer: true
    })
  ],
  plugins: [
    new webpack.optimize.CommonsChunkPlugin('vendor', 'vendor.bundle.js'),
    new webpack.DefinePlugin({
      'process.env': { NODE_ENV: JSON.stringify(process.env.NODE_ENV || 'development') }
    })
  ],
  devServer: {
    contentBase: './client',
    hot: true
  }
}

```


> 注:"__dirname"是node.js中的一个全局变量，它指向当前执行脚本所在的目录
