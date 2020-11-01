
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