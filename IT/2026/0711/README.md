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

### 3.3 升级 VS Code
Code -> Check for Updates...

## 参考文档
- [Git 教程【廖雪峰】](https://liaoxuefeng.com/books/git/introduction/index.html) ✅ 
  - 非常系统和全面的介绍 Git
- [GitHub 新手指南：星球最强资源库](https://www.bilibili.com/video/BV14qh8ztEhv/) ✅
  - 很好的 GitHub 入门级介绍
- [如何发布你的第一个 GitHub 项目？](https://www.bilibili.com/video/BV1H5xeeQELn) ✅
  - 点击 Add file -> Upload files，可以直接拖拽本地目录上传到 Repository，酷！
