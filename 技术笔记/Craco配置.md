---
tags: [技术笔记]
categories: [技术笔记]
---


## 安装
- 参考 [craco/README](https://github.com/dilanx/craco/blob/master/packages/craco/README.md)



## craco配置antd
1. 安装antd 及carco插件

```
yarn add antd
yarn add craco-antd
```

```js
// craco.config.js
const CracoAntDesignPlugin = require('craco-antd');

module.exports = {
  plugins: [
    {
      plugin: CracoAntDesignPlugin,
      options: {
        customizeTheme: {
          '@primary-color': '#1DA57A',
        },
      },
    },
  ],
};

```
[在 TypeScript 中使用 - Ant Design](https://ant.design/docs/react/use-in-typescript-cn)


## craco配置less module

1. 在 `react-app-env.d.ts`文件中申明 module less文件
```ts
declare module '*.less' {  
  const resource: {[key: string]: string};  
  export = resource;  
}
```

2. 使用時
``` css
.background {  
  background-color: red;  
}
```


```ts
import style from './index.module.less'
const Hello:React.FC = () => {  
  return(  
    <div className={style.background}>  
  
      456  
    </div>  
  )  
}  
  
export default Hello

```
## craco配置alias

```js
// craco.config.js
const resolve = dir => require('path').resolve(__dirname, dir)  
  
  
module.exports = {  
  ...
  alias: {  
    '@': resolve('src')  
  }  
  ...
};

```


```json
// tsconfig.json
{  
  "compilerOptions": {  
	...
    "paths": {  
      "@/*": [  
        "src/*"  
      ]  
    },
    ... 

}
```