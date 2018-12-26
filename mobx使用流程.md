# react下mobx使用流程

### 环境配置
- 安装
```
npm install mobx --save
npm install mobx-react --save
```
- 安装修饰器支持(react预置脚手架不支持decorators,需要eject后重新配置babel plugin)
```
npm i --save-dev babel-plugin-transform-decorators-legacy
```
package.json中修改babel配置对象：
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
- vscode开发环境语法报错问题解决
    根目录下新增jsconfig.json
```
{
    "compilerOptions": {
        "experimentalDecorators": true,
        "emitDecoratorMetadata": true
    }
}
```
### 使用
- 根目录下创建store文件夹，创建对应的js文件
定义类，并导出类的实例
  + import {observable,computed,action,runInAction} from 'mobx'
  + @observable 定义基准数据（作为变化的根源）
  + @computed 计算衍生值 随着引用observable值变化即计算
  + @action 定义调用方法 修改observable的值
  + runInAction 在异步请求到数据后修改observable的值，需要作为runInAction的回调
- 根部提供store入口
```
const stores={courseListStore}
<Provider {...stores}></Provider>
```
- 组件中使用
```
import { inject, observer } from 'mobx-react';
@inject('examplestore')
@observer
```
引用方式：this.props.examplestore
