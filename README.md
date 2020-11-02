
``` bash
npm init --y
npm i -g babel-cli
npm i --save babel-preset-es2015 #安装Es6转换器
babel input.js --presets es2015
babel input.js -o output.js--presets es2015 # 单文件转换
babel src -d dist --presets es2015 # 按目录转换
```

.babelrc:
``` json
{
    "presets":["es2015"],
    "plugins":[]
}
```

``` bash
npm run build
```

env:
``` bash
npm i -d babel-preset-env #安装Es6及以上转换器
```

.babelrc:
``` json
{
    "presets":["env"],
    "plugins":[]
}
```


npm过慢，可选用cnpm:
``` bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

``` bash
npm install --save-dev @babel/core @babel/cli @babel/preset-env
npm install --save @babel/polyfill
```

babel-polyfill

Babel默认只转换新的javascript语法，但并不转换新的API，比如 Generator、Set、Symbol、promise等全局对象，以及一些定义在全局对象上的方法都不会转码。如果想让这些方法运行则必须使用babel-polyfill。

安装

$ npm install --save babel-polyfill

 安装：npm install -g browserify
 命令执行，编译文件:browserify ./自己路径 -o  ./bundle.js

 ``` bash
 browserify dist/index.js -o build/index.js
 ```


 babel module/js3.js -o dist/js3.js &  browserify dist/js3.js -o build/js3.js




 webpack配置
1)安装webpack
$  npm install webpack webpack-cli --save-dev

2)添加配置文件 webpack.config.js
const path=require('path');
module.exports={
    entry:'./index.js',
    output:{
        filename:'bundle.js',
         path:path.resolve(__dirname,'dist')
    },
    module:{
        rules:[{ 
               test:/\.js$/,
               use:'babel-loader'
           }]
    }
}
 

3) 修改package.json
 "scripts":{
                "build":"webpack"
            }

4)打包 
$ npm run bulid




webpack + polyfill + babel