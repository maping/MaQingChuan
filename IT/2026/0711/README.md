# 分布式版本控制系统：Git

## 1. [Git](https://git-scm.com/)

### 1.1 安装 Git (macOS‌)

#### 1.1.1 安装 [Homebrew](https://brew.sh/)
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### 1.1.2 升级 Homebrew
```shell
brew upgrade
```

#### 1.1.3 使用 Homebrew 安装 Git 
```shell
brew install git
```
#### 1.1.2 使用 Homebrew 更新 Git
```shell
git --version
brew update
‌brew upgrade git
‌git --version
```

### 1.2 配置 Git
因为 Git 是分布式版本控制系统，所以，每个机器都必须自报家门：user.name 和 user.email。
>问题：如果有人故意冒充别人怎么办？
```shell
git config --global user.name "maping"
git config --global user.email "maping930883@hotmail.com"
```
>说明：--global 参数，表示你这台机器上所有的 Git 仓库都会使用这个配置，当然也可以对某个仓库指定不同的 user.name 和 user.email。

上述命令会生成 .gitconfig 文件，内容如下：
```txt
[user]
	name = maping
	email = maping930883@hotmail.com
```

### 1.3 拉取 Public Repository
```shell
mkdir git
cd git
git clone https://github.com/maping/Language.git
```
>说明：建立 git 目录，表明该目录都是 git 命令行拉取的 Repository

## 2. [GitHub](https://github.com/)

### 2.1 注册并登录 GitHub

### 2.2 创建第一个 Repository

### 2.3 编写第一个 README.md

### 2.4 Markdown 语法介绍

## 3. [GitHub Desktop](https://desktop.github.com) 

### 3.1 安装 GitHub Desktop (macOS‌)

### 3.2 GitHub Desktop 基本使用
clone 一个远程 repository 到本机
>注意：GitHub Desktop 默认克隆到的本机目录是 /Users/<USER_NAME>/Documents/GitHub/<YOUR_RESPOSITORY>

- 修改代码前，先 Fetch origin 确保把最新的版本拉到本地
- 用 VS Code 打开 repository，修改内容并保存
- 填写 Summary (required)
- 提交代码前，再 Fetch origin 一次，看看有没有人在此期间更新代码
- Commit
- Push origin

## 3. [Visual Studio Code](https://code.visualstudio.com/) 

### 3.1 安装 Visual Studio Code

### 3.2 配置 Visual Studio Code 源代码管理（GitHub）
Clone Git Repository...

Clone Repository -> Clone from GitHub ｜ 也可以是其它 Git Repository，比如 GitLab
- 登录 GitHub 账号
- Authorize Visual Studio Code
- Select a Repository Destination

### 3.3 修改代码，并推送到远程 Repository
- 修改代码并保存
- Commit -> Commit All Changes
- Sync Changes

### 3.4 升级 VS Code
Code -> Check for Updates...

## 参考文档
- [Git 教程【廖雪峰】](https://liaoxuefeng.com/books/git/introduction/index.html) ✅ 
  - 非常系统和全面的介绍 Git
- [GitHub 新手指南：星球最强资源库](https://www.bilibili.com/video/BV14qh8ztEhv/) ✅
  - 很好的 GitHub 入门级介绍
- [如何发布你的第一个 GitHub 项目？](https://www.bilibili.com/video/BV1H5xeeQELn) ✅
  - 点击 Add file -> Upload files，可以直接拖拽本地目录上传到 Repository，酷！
- [Visual Studio Code 中配置使用 Git](https://www.bilibili.com/video/BV1ti73zuEVF/) ✅

