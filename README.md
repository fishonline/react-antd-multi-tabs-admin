<h1 align="center">Antd Multi Tabs Admin</h1>

<div align="center">🛠️Antd多标签页后台管理模板🛠️</div>

<div align="center">
由于业务上有多页签需求，网上找了一圈，都是基于antd pro的模板，太重了，不喜欢😒。<br/>
于是自己从以前的框架上改造，搭了这么一个精简版框架，用得也舒服，原创🤪。

[预览地址](https://www.hongshaoli.com/antd-admin)
![](https://github.com/hsl947/hsl947.github.io/raw/master/images/antd-admin-1.png)
![](https://github.com/hsl947/hsl947.github.io/raw/master/images/antd-admin-2.png)
![](https://github.com/hsl947/hsl947.github.io/raw/master/images/antd-admin-3.png)
![](https://github.com/hsl947/hsl947.github.io/raw/master/images/antd-admin-4.png)
![](https://github.com/hsl947/hsl947.github.io/raw/master/images/antd-admin-5.png)
</div>

## 特性

- 📐: **代码规模**：使用 TS，原创精简版脚手架，不臃肿
- 💎: **优雅美观**：基于 Ant Design 体系精心设计
- 🚀: **最新技术栈**：使用 React/Redux/Antd 等前端前沿技术开发
- 🎨: **主题**：使用流行的暗黑模式主题，支持深/浅色主题切换

## 特点

- 多 tab 页签➕右键菜单，提升效率
- Redux 状态管理➕持久化
- 封装实用 axios 请求
- 动态链式面包屑导航
- 菜单页面路由权限控制
- less➕css module 样式隔离
- 列表➕分页➕多选➕搜索联动组件
- 可自定义 webpack 配置➕优化打包

## 使用

### 使用命令行
```bash
$ npm install -g typescript
$ git clone https://github.com/hsl947/react-antd-multi-tabs-admin.git
$ yarn install
$ yarn start         # 访问 http://localhost:666
```

### 权限控制
<p>如果不需要权限控制，可自行注释去掉权限功能。</p>

```
# src/components/common/menu/index.tsx

// 创建可展开的第一级子菜单
const creatSubMenu = (data: any): JSX.Element => {
  // const menuItemList = []
  // data.routes.map((item: any) => {
  //   const arr = permission.filter((ele: any) => item.key === ele.code)
  //   if (arr.length > 0) {
  //     menuItemList.push(renderMenu(item))
  //   }
  //  return arr
  // })

  const menuItemList = data.routes.reduce(
    (prev: any, next: any) => [...prev, renderMenu(next)],
    []
  )

  return menuItemList.length > 0 ? (
    <SubMenu key={data.key} title={subMenuTitle(data)}>
      {menuItemList}
    </SubMenu>
  ) : null
}
```

```
# src/pages/container/index.tsx

// 检查权限
const checkAuth = (newPathname: string): boolean => {
  // 不需要检查权限的
  // if (noCheckAuth.includes(newPathname)) {
  //   return true
  // }
  // const { tabKey: currentKey } = getKeyName(newPathname)
  // return isAuthorized(currentKey)

  // 一定返回 true
  return !!newPathname
}

```


## 支持环境

现代浏览器及 IE11。

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Opera |
| --------- | --------- | --------- | --------- | --------- |
| IE11, Edge| last 2 versions| last 2 versions| last 2 versions| last 2 versions

## 参与贡献

我们非常欢迎你的贡献，你可以通过以下方式和我们一起共建 :smiley:：

- 通过 [Issue](https://github.com/hsl947/react-antd-multi-tabs-admin/issues) 报告 bug。
- 提交 [Pull Request](https://github.com/hsl947/react-antd-multi-tabs-admin/pulls) 一起改进。
