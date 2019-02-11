### 创建自定义云函数步骤
1.  npm install -g mincloud
2.  mincloud login 0d9d3c5f827919118c2a 9eb94dc68cefb27cf4187b4c39231df7b6dacaff
3.  mincloud new func_test
4.  cd func_test
5.  npm init
6.  新建 src 文件夹，用来存放源码。 接下来会使用 webpack 将 src 里的代码，打包并保存到 func_test 目录下的 index.js
7.  新建 webpack.config.js 文件
8.  npm install -D webpack webpack-cli
9.  webpack.config.js和package.json script 配置
```
module.exports = {
  output: {
    path: __dirname,
    filename: 'index.js',
    library: 'exports.main',
    libraryTarget: 'assign',
  },
  target: 'node',
}
```
```
  "scripts": {
    "build": "webpack --mode production",
    "deploy": "mincloud deploy xxxxx ../"
  },
```
10.  src/index.js
```
// 可以在这里引入其他模块
module.exports = function (event, callback) {

}
```
11.  npm run build
12.  npm run deploy
13.  cd ..
14.  mincloud deploy func_test