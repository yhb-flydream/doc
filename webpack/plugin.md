
### clean-webpack-plugin

 用于清空 dist 目录。

1.安装

npm i -D clean-webpack-plugin


2.使用
//webpack.config.js 中使用
```

const CleanWebpackPlugin = require('clean-webpack-plugin');


plugins: [

	    new CleanWebpackPlugin(['./dist']),
]
```


###  copy-webpack-plugin

 用于复制 src 文件到 dist

1.安装
npm i -D copy-webpack-plugin

2.使用
//webpack.config.js 中使用

```

const CopyWebpackPlugin = require('copy-webpack-plugin');


plugins: [

	    new CopyWebpackPlugin([
          {from:path.resolve(__dirname,'./src/components/vendor'),to:path.resolve(__dirname,'../www/static/pc/vendor')},
          {from:path.resolve(__dirname,'./src/css'),to:path.resolve(__dirname,'../www/static/pc/css')},
          {from:path.resolve(__dirname,'./src/images'),to:path.resolve(__dirname,'../www/static/pc/images')},
        ]),
]
```


### html-webpack-plugin
 用于生成 html 文件

1.安装
npm i -D html-webpack-plugin

2.使用
//webpack.config.js 中使用

```

var HtmlWebpackPlugin = require('html-webpack-plugin');


plugins: [

		// 每一个页面一个配置
        new HtmlWebpackPlugin({
            title: 'title',  // 生成 HTML 文档的标题
            filename: 'index.html', // 写入 HTML 文件的文件名，默认 `index.html`, 生成的html存放路径，相对于path
            favicon: './src/img/favicon.ico', // favicon路径，通过webpack引入同时可以生成hash值
            template: './src/method1/test.html', // html模板路径
            inject: true, // js插入的位置，true/'head'/'body'/false
            hash: true, // 为静态资源生成hash值
            chunks: ['index'], // 需要引入的chunk，不配置就会引入所有页面的资源js
            minify: { // 压缩HTML文件
                removeComments: false, // 移除HTML中的注释
                collapseWhitespace: false // 删除空白符与换行符
            }
        }),
]
```


### extract-text-webpack-plugin
把css分离成单独的文件






