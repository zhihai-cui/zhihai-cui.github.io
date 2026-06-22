# Hugo 快速开始指南


这篇文章可以让你在几分钟内快速入门Hugo.

<!--more-->

本文参考了[Hugo 快速入门官方文档](https://hugo.opendocs.io/getting-started/quick-start/)。

首先，Hugo 是一个快速、简单、高效的静态网站生成器，如果你想了解更多关于Hugo的信息，请访问[hugo 官方网站](https://gohugo.io/)。

### 1. 为网站添加新页面

在命令行中输入以下命令，为网站添加一个新的页面：

```bash
hugo new content/posts/my-first-post/index.zh-cn.md
```

运行该命令，Hugo 将在 `content/posts/my-first-post/` 路径下创建一个新的页面 `index.zh-cn.md`，使用编辑器打开该文件并编辑内容。  

注意，文件中的draft字段默认为true，Hugo 在构建网站时不会发布草稿内容。

但是，可以通过以下命令来发布草稿内容，并且可以保持 public/ 目录始终纯净，只用于正式构建。

```bash
hugo server -D --destination ./preview
```
访问 `http://127.0.0.1:1313/` 即可通过本地服务器查看网站。

想要正式构建网站，请将draft字段设置为false，然后运行以下命令：

```bash
hugo
```
注意，`hugo server`默认在开发环境下构建网站，而`hugo`默认在生产环境下构建网站。

**所以，对于一些暂时不能公开发表的内容，可以保持draft字段为true，然后运行上述`hugo server -D --destination ./preview`来查看草稿内容。**

**而对于可以正式发表的内容，可以将draft字段设置为false，然后运行`hugo`来正式构建网站**。

### 2. 发布到github pages

#### 2.1 首次提交（新建仓库）

```bash
# 1. 初始化本地 Git 仓库（如果还没有 .git 文件夹）
git init

# 2. 添加所有文件到暂存区（. 代表当前目录所有文件）
git add .

# 3. 提交到本地仓库，并写上说明
git commit -m "first commit"

# 将当前分支（master）重命名为 main
git branch -M main

# 4. 添加远程仓库地址（将下面的 URL 换成你自己的）
git remote add origin https://github.com/你的用户名/仓库名.git

# 5. 将本地 main 分支推送到远程，并建立关联
git push -u origin main
```
#### 2.2 日常更新提交（仓库已存在）

```bash
# 1. 拉取远程最新代码（避免冲突，养成好习惯）
git pull

# 2. 添加所有修改的文件到暂存区
git add .

# 3. 提交到本地仓库
git commit -m "更新说明"

# 4. 推送到 GitHub 远程仓库
git push
```

