# react-ts-admin 后台管理系统

## VSCode 环境搭建
+ 参考: [react开发vscode插件推荐](https://www.cnblogs.com/xbzhu/p/10823300.html)

### 代码提示类插件
+ Reactjs code snippets
+ React Redux ES6 Snippets
+ React-Native/React/Redux snippets for es6/es7
+ JavaScript (ES6) code snippets(es6代码片段)
+ Typescript React code snippets(这是tsx的react组件片段)
+ ES7 React/Redux/GraphQL/React-Native snippets

### 美化类插件
+ One Dark Pro(atom风格主题)
+ vscode-icons(文件图标)

### 其他实用类插件
+ Beautify css/sass/scss/less(样式代码格式化, 可选)
+ Sass/Less/Scss/Typescript/Javascript/Jade/Pug Compile Hero Pro (推荐)
  - 支持保存时(`Ctrl + S`)自动编译以下文件：less, sass, scss, typescript, jade, pug and jsx
  - 支持自动格式化文件:  按快捷键 `Alt + Shift + F` 或者在文件列表右键菜单选择 `Format Document`
  - 更多功能,请查看[官方文档](https://github.com/Wscats/compile-hero/blob/master/README.CN.md)

+ npm Intellisense(对package.json内中的依赖包的名称提示)
+ Path Intellisense(文件路径补全)
+ cssrem(px转换为rem)
+ CSS Modules(对使用了css modules的jsx标签的类名补全和跳转到定义位置)

+ Settings Sync
有了它就不用每次换个开发环境又重新配置一遍vscode了。

## 需要额外安装几个库
```bash
yarn add @types/react-redux
yarn add @types/react-router-redux
yarn add react-redux
```

## 运行错误
### Unhandled Rejection (SecurityError): The operation is insecure.
```
unregister
src/serviceWorker.ts:140
```

```js
  137 | export function unregister() {
  138 |   if ('serviceWorker' in navigator) {
  139 |     // TODO: 这里不安全,需要处理
> 140 |     navigator.serviceWorker.ready.then(registration => {
  141 |       registration.unregister();
  142 |     });
  143 |   }
```

## 技术栈引用
最终选择了 **React hook + Typescript + Redux + Thunk + AntD**构建一个后台管理系统。

原因如下：


* react-hook，[官网已经说的很清楚引入hook的好处](https://react-1251415695.cos-website.ap-chengdu.myqcloud.com/docs/hooks-intro.html#motivation)。

   个人会选择是因为考虑到同事不会用react……

   组件复用、this的指向、较复杂的生命周期、class等等学习成本较高，为了让他们更快的开发，就选择了hook。

   当然用了一段时间，还是觉得hook蛮香的，简化了不少代码。所以还是蛮推荐大家试试看!

* typescript 
   
  增加了代码的可读性和可维护性，为了日后更好的维护，降低成维护成本。

  + 基础[在线可运行的基础实例](https://www.typescriptlang.org/zh/play?useJavaScript=trueq=134#example),有注释。

 （好了，我不装了，我摊牌了。）

  我受够后台变来变去的数据类型（前段时间后台在整改），一出错很难第一时间排查问题。

  我受够了一些前端开发的规范问题。在整个JS开发过程中，开发人员容易用隐式转换，或‘==‘等等，甚至有些模块引用又不用(代码风格和规范由Tslint和Eslint提供检查)，导致后期维护更难理解代码。

  Typescript和tslint的引用是为了把js“变成“强类型语言，在自己写的代码中要注意类型和规范，（**尽量别写any**！）若万不得已类型为**any**或者 **@ignore**，则要标注下原因。这样的话就简洁明了，后期维护更加迅速，更能减少不规范的代码写法。

  
*  redux-thunk
  
  thunk加上asyc/await的用法更为直观。

* 希望大家多多给意见，共同进步。如果可以的话，给个star！

  
### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.