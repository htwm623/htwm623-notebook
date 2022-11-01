---
tags: [react]
categories: [技术笔记]
---

## 参考资料
- [Home v6.4.2 | React Router](https://reactrouter.com/en/main)


## V5

1. v5不提供路由的集中管理

### 基本使用
1. 导入
```jsx
import { Link, BrowserRouter, Route } from 'react-router-dom'

// 跳转路由
<Link className="list-group-item" to="/about">About</Link>

// 注册路由

<Route path="/about" component={About}></Route>
<Route path="/home" component={Home}></Route>
```
2. link 和route 需要在一个路由管理下才能进行页面跳转 所以需要在外层包裹 `BrowserRouter`
```js
// index.js
<BrowserRouter>
	< App />
</BrowserRouter>
```
