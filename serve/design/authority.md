随便建立菜单，但是不受vue路由的嵌套结构影响，然而前端的菜单渲染是通过路由来渲染的


- meun1
  - child1
    - grand child1


```js
if (grand child has no children item ) {
  let routerList = [];
  routerList.push(grandchild);
  // 动态添加路由
  this.$rotuer.addRoute(routerList);
}
```
1. 新建用户
2. 新建角色 - 绑定用户 - 分配菜单
3. 新建路由

用户管理
角色管理
菜单管理 
