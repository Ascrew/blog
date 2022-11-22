1. 表结构
2. 角色的路由权限怎么存 数组 or 树
3. 修改应该怎么存数据



- 构造路由表-mysql树形表
- 构造角色表和用户表 建立关系 - 角色一对多表
- 前端查询角色对应的路由表查询树结构数据返回给前端
- 前端动态添加路由

操作上：
1. 创建用户和角色，为用户分配角色
2. 在管理员页面  添加菜单 包括：路由地址，菜单名称
3. 为角色分配菜单
over

qus:
- 细化到按钮权限？
- 后端怎么做某个按钮的后端api权限校验








# Tree Sql Design
学习一下使用mysql做树结构的表设计

- 一般比较普遍的就是四种方法：（具体见 SQL Anti-patterns这本书）
  - Adjacency List：每一条记录存
  - parent_idPath Enumerations：每一条记录存整个
  - tree path经过的node枚举
  - Nested **Sets**：每一条记录存 nleft 和 **nrightClosure** Table：维护一个表，所有的tree path作为记录进行保存。


- 各种方法的常用操作代价见下图  
<img src="https://pic1.zhimg.com/50/fcf1ab401ae938be41f4a20b01fc38d0_720w.jpg?source=1940ef5c" data-rawwidth="526" data-rawheight="136" class="origin_image zh-lightbox-thumb" width="526" data-original="https://pica.zhimg.com/fcf1ab401ae938be41f4a20b01fc38d0_r.jpg?source=1940ef5c"/>

推荐一本书 SQL Anti-patterns，其中对于树形结构在关系型数据库中的存储做了分析。一共有4种方式。各有优劣，主要是跟据业务需求来决定的。
> 链接：  http://www.ppurl.com/2010/06/sql-antipatterns-avoiding-the-pitfalls-of-database-programming.html

