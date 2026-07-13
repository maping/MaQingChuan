# [Python](https://www.python.org/)
Life is Short, You Need Python.

## 1. 安装 Python (macOS‌)

### 1.1 检查已经安装了哪些 Python 版本
macOS 13.x/14.x/15.x 预装的 Python 3 版本是 Python 3.9.6。
```shell
/usr/bin/python3 --version
Python 3.9.6
```
>重要：不要动系统自带的 Python：macOS 系统本身依赖的 Python（如 /usr/bin/python3 指向的 3.9.6 版本）不要删除或修改，以免造成系统不稳定。

检查之前是否从 Python 官网安装包 或 Homebrew 安装过 Python
```shell
which python3
```
输出 /Library/Frameworks/Python.framework/Versions/3.13/bin/python3 说明从官网安装。

输出 /opt/homebrew/bin/python3 说明从 Homebrew 安装。

### 1.2 从官网安装最新 Release 版 Python 3.14.6
Python 新旧版本可以共存：升级并不是“覆盖”，而是“安装新版本，并让系统默认使用它”。你之前安装的 Python 3.13 依然留在电脑里，可以通过 python3.13 命令来精确调用。

```shell
which python3
/Library/Frameworks/Python.framework/Versions/3.14/bin/python3
```
>发现：系统已经把 python3 指向新安装的版本了。

在 ～/.zprofile 文件中，定义了新安装的 Python 版本路径
```shell
grep -r "3.14" ~/.zshrc ~/.bashrc ~/.bash_profile ~/.zprofile ~/.profile /etc/profile /etc/zshrc 2>/dev/null
/Users/vmaping/.zprofile:# Setting PATH for Python 3.14
/Users/vmaping/.zprofile:PATH="/Library/Frameworks/Python.framework/Versions/3.14/bin:${PATH}"
```
macOS 默认的 Shell 是 Zsh，因此 .zprofile 在登录时加载且比 .zshrc 更早，所以系统级的环境变量放在这里，生效范围最广、最稳定。

Python 官方安装包有一个非常贴心的设计：/Library/Frameworks/Python.framework/Versions/ 目录下，除了具体的版本号文件夹（如 3.13、3.14），还会有一个 Current 符号链接，它永远指向你安装的最新版本。

## 2. 在 Visual Studiio Code 中配置 Python 环境
安装常用 Python 插件
- 安装 Microsoft 出品的 Python 系列插件
- 安装 Cstrap 出品的 python-snippets 插件

## 3. 创建第一个 Python 程序：helloworld.py
在 Visual Studiio Code 中，新建一个文件 helloworld.py，内容如下：
```python
print("Hello, World!")
```
右键 helloworld.py 文件，选择 Run Python -> Run Python File in Terminal ｜ 也可以直接点击 右上角 ▶️ 运行程序。

## 3. [if 练习（1）](https://www.bilibili.com/video/BV1hW41197sB?p=44)

## 4. [if 练习（2）](https://www.bilibili.com/video/BV1hW41197sB?p=45)

## 作业
看视频 [学了Python能干什么?](https://www.bilibili.com/video/BV1WY411n7Zu)

## 参考文档
- [Visual Studiio Code 中配置 Python 环境](https://www.bilibili.com/video/BV1TN411K7sn/)
- [Visual Studiio Code 中配置 Python 虚拟环境](https://www.bilibili.com/video/BV17P7DzeEmm/)
