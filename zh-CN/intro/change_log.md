---
name: 变更日志
sort: 1
---

# 变更日志

### V0.4.0(2014-5-31)

#### Bug 修复

- 使用 PostgreSQL 时无法迁移仓库 [#141](https://github.com/gogits/gogs/issues/141)
- 在公开活动列表显示私有仓库活动 [#148](https://github.com/gogits/gogs/issues/148)
- 安装页面管理员用户名未进行验证 [#149](https://github.com/gogits/gogs/issues/149)
- 修改用户名未完全更新权限表 [#150](https://github.com/gogits/gogs/issues/150)
- 没有 master 分支时发生 panic
- 删除分支时发生 panic [#155](https://github.com/gogits/gogs/issues/155)
- 当评论者不是仓库拥有者时，会跳转至 404 页面 [#159](https://github.com/gogits/gogs/issues/159)

#### 功能改进

- 允许通过设置环境变量 `GOGS_CONFIG` 来加载全局配置文件，该加载操作发生在加载 `custom/conf/app.ini` 之前 [#145](https://github.com/gogits/gogs/issues/145)

#### 新增特性

- 支持用户名包含点 `.` [#91](https://github.com/gogits/gogs/issues/91)
- 支持 添加/删除 仓库协作者
- 增加 `server -> ROUTER_LOG` 配置选项来控制路由访问日志
- 增加 `picture -> DISABLE_GRAVATAR` 配置选项来禁止 Gravatar
- 增加 `gogs dump` 命令用于打包文件和数据库

#### 其它变更

- 官方网站上线（[gogs.io](http://gogs.io)）
- 支持通过 Vagrant 安装（[备注](https://github.com/geerlingguy/ansible-vagrant-examples/tree/master/gogs)）

### V0.3.1(2014-4-28)

#### Bug 修复

- 当 tag 没有作者时会导致 Panic [#92](https://github.com/gogits/gogs/issues/92)
- Docker 启动脚本的相关问题 [#124](https://github.com/gogits/gogs/pull/124) [#129](https://github.com/gogits/gogs/pull/129)
- 单个文件浏览时图片体积过大而导致样式溢出

#### 功能改进

- 在安装页面记住数据库选项

#### 新增特性

- 对 LDAP/Microsoft Active Directory 的基本支持 [#112](https://github.com/gogits/gogs/pull/112)
- 增加离线模式来禁止从 CDN 获取资源
- 支持使用 e-mail 登录

#### 其它变更

- 修正许多语法和拼写错误
- 提供 MySQL 引擎初始化错误的解决方案（[备注](https://github.com/gogits/gogs/wiki/Troubleshooting#error-1071-specified-key-was-too-long-max-key-length-is-1000-bytes)）
- 当激活 SQLite3 选项时将其作为默认数据库

### V0.3.0(2014-4-23)

#### Bug 修复

- 单击复制克隆链接按钮无效（[备注](https://github.com/gogits/gogs/wiki/Known-Issues#repository-viewerurl-usernamereponame)）
- 删除用户时未清理相应的权限表和关注表的数据
- 服务器日志未记录到正确位置

#### 功能改进

- 在提醒邮件中增加相应的 Issue 链接
- 为每个用户增加单独的盐
- 使用 PBKDF2 和用户单独的盐来加密密码（[备注](https://github.com/gogits/gogs/wiki/Troubleshooting#upgrade-from-v020)）
- 大幅缩短在获取仓库文件时的时间、CPU 和内存占用
- 按页面显示仓库 Commits 列表
- 使用构建 tags 来激活 SQLite3 选项（[备注](https://github.com/gogits/gogs/wiki/Install-from-source#install)）

#### 新增特性

- 支持重命名 仓库/用户
- 支持转移仓库所有权
- 支持重置用户密码
- 支持在 Markdown 渲染中捕捉 `@someone`、`#issueNum`、SHA1 字符串和 Issue 链接
- 支持在创建 Issue 时对 @ 到的用户进行邮件提醒
- 支持 `go get` 的 `meta` 标签
- 支持设置默认分支
- 支持 HTTP(S) 推送
- 支持在指定分支根据关键字搜索 commit
- 支持私有仓库
- 支持迁移和镜像 公开/私有 仓库
- 支持采用社交帐号登录（GitHub、Google、QQ、微博）
- 支持查看和新增 release（使用已有 tag 或直接新建）
- 支持下载指定 commit 的 zip 文件
- 支持根据 tag 浏览仓库

#### 其它变更

- 服务端和客户端的 Git 版本要求提升至 1.6.6（用于支持 Smart HTTP）
- 支持 Docker 部署（[备注](https://github.com/gogits/gogs/tree/master/dockerfiles)）

### V0.2.0(2014-4-1)

- 首个公开发布版本