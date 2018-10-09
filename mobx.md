## mobx环境配置（react框架下）
    mobx-数据解决方案，实现响应式组件开发

- vscode开发环境中使用mobx定义修饰器@observer,动作处理@action等时，会出现语法报错（webpack可以编译）。可以在根目录下新增jsconfig.js，可以消除波浪线。
```javascript
  {
    "compilerOptions": {
        "experimentalDecorators": true,
        "emitDecoratorMetadata": true
    }
}
```

- react预置脚手架不支持decorators,需要eject后重新配置babel plugin。
 安装修饰器支持
```
npm i --save-dev babel-plugin-transform-decorators-legacy
```
package.json中修改babel配置对象
```
"babel": {
  "presets": [
    "react-app"
  ],
  "plugins": [
    "transform-decorators-legacy"
  ]
} 
```
