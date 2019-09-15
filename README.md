# 快速开始
<br>

## 使用前准备

在使用之前，推荐学习 `Vue` 和 `ES2015` ，并正确配置 `Node.js` v6.x 或以上版本
<br>

## 引入mzui
支持整个引入mzui，或按需要引入部分组件。

### 完整引入  
在项目main.js中写入以下内容：

```js
import mzui from '@framework/mzui' // 引入组件库
import '@framework/zui/lib/styles/index.css' // 引入样式库
Vue.use(mzui)
```

### 按需引入
借助 [babel-plugin-component](https://www.npmjs.com/package/babel-plugin-component)，我们可以只引入需要的组件，以达到减小项目体积的目的。
1. vue-cli3脚手架
```bash
npm install babel-plugin-component -D
```
babel.config.js修改
```js
plugins: [
    [
      'component',
      {
        libraryName: '@framework/mzui',
        styleLibrary: {
          name: 'styles',
          base: false
        },
        style: true
      }
    ]
  ]
```

vue-cli2

```js
```


