
## 博客介绍

- 前后台分离式开发（项目中也包含博客的后台管理系统），为了方便记录后端开发过程，笔者将后端也一起放在同个项目文件夹中。
- 博客样式几乎借助于 antd 这个优秀的 UI 框架，主打简约风格，是笔者借鉴了 antd 官方的风格所设计。
- 分出了几个分支便于学习和查看开发记录

### 实现功能

- [x] 主页 + 列表页 + 搜索页 + 后台增删改查文章等
- [x] 博客标签、分类
- [x] 评论与回复功能模块 评论回复的邮件通知
- [x] 用户登录注册，以及权限管理 (jwt + localStorage)
- [x] markdown 代码高亮
- [x] 锚点导航 回到顶部
- [x] 响应式开发
- [x] 个人账户信息的修改

### 技术栈

- 前端 （基于 `create-react-app eject` 后的配置）
  - react v16.8.1
  - redux redux-thunk
  - react-router4
  - axios
  - marked highlight.js
- 后端 （自构建后台项目）
  - koa2 + koa-router
  - sequelize + mysql
  - jwt + bcrypt
  - nodemailer


### 分支

为了方便查看开发记录笔者分了几个分支

1. [client-chore](https://github.com/gershonv/react-blog/tree/client-chore): 记录前端项目的构建过程
   1. 配置 react + antd + less + babel-plugins-import
   2. 配置 redux + redux-thunk + redux-logger (开发和生产环境)
   3. 配置 装饰器 + axios 封装 + 路由配置（主博客路由 和 admin 管理系统）
2. [server-chore](https://github.com/gershonv/react-blog/tree/server-chore): 记录后端项目的构建过程
   1. 配置 koa + koa-router + 中间件
   2. 项目结构划分（mvc 结构）
   3. 配置 sequelize 以及数据库的设计
   4. ...
3. [client-markdown](https://github.com/gershonv/react-blog/tree/client-markdown): 配置 markdown 语法高亮
4. [dev](https://github.com/gershonv/react-blog/tree/dev): 开发分支
5. [email-notice](https://github.com/gershonv/react-blog/tree/email-notice): 邮件推送服务

## 开启项目

### 前端

```bash
git clone https://github.com/dobeco/blog.git

cd blog

npm i --registry=https://registry.npm.taobao.org

npm start
```

### 后端

创建一个 blogdev 的 mysql 数据库，修改 `server/config/db.js` 去连接你的数据库。
运行 `server/config/blogdev.sql` 文件导入数据

```bash
cd server
npm i --registry=https://registry.npm.taobao.org
npm start
```

## 总结

- 前端
  - 如何组织项目架构。合适的项目架构可以提高开发效率和更好的后期维护。
  - 第二 router 4 如何封装才更好拓展，维护。这里部分借助了 [rekit](https://github.com/supnate/rekit) 目录结构
  - 如何利用 react 新特性去组织你的代码
  - 如何利用工具提高效率，装饰器，热加载，（redux、…）
  - 当然权限的管理 jwt， 对 antd 的使用
- 后端
  - koa 各类中间件使用
  - 登录注册权限，jwt 加密，处理权限的方式
  - sequelize 的使用 模型定义 多表~
  - 错误的统一处理，如何优雅的处理
  - 项目结构如何搭建等等
