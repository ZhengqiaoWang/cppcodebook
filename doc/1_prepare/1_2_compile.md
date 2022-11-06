# 1.2 编译环境准备

在我们准备好`Linux`环境后，我们就可以准备编译环境了。

## 1.2.1 g++

`gcc`或者`g++`都是我们常用的编译工具，二者略有不同，目前版本下二者也均能编译`C++`程序，我们这里统一采用`g++`来实现编译，当然，除了这些意外，还有`msvc`,`clang`等工具可以实现类似效果。

在我们进入`Linux`环境后，如果我们不是root用户，就需要确定我们是否是`sudoer`，一般默认用户都添加在`sudoer`名单中，因此，我们只需要输入以下命令，即可完成`g++`的安装。

```shell
sudo apt-get update
sudo apt-get install build-essential gcc g++
```

然后我们就可以运行

```shell
gcc --version
g++ --version
```

如果出现版本号，那就说明安装成功了。

## 1.2.2 make

`make`工具是用于解决项目文件数目较多时的编译问题的，毕竟一行一行地敲命令编译文件听起来就不够靠谱。有了它，你可以通过编写`makefile`来快速地实现编译等个性化操作。

安装起来也很简单

```shell
sudo apt-get install make
```

然后我们就可以运行

```shell
make -v
```

查看版本号啦。

## 1.2.3 CMake

`CMake`工具可以理解成`make`工具的进阶版，他将`makefile`更进一步简化，我们可以通过`CMakeLists.txt`文件以比`makefile`更少的行数来实现同样的编译目的。特别当项目较大时，`CMake`比`make`更清晰，也更方便使用。这也因此导致其成为目前主流的一种编译工具。

```shell
sudo apt-get install cmake
```

查看版本同样简单

```shell
cmake -v
```

除了`make`，`cmake`之外，还有很多其他的编译工具，包括`ninja`，`automake`等等，各有优劣，感兴趣的话可以去学习使用。

## 1.2.4 Visual Studio Code

`Visual Studio Code`简称`VSCode`，是微软开源的一个编辑器，他通过一系列插件实现类似`IDE`的功能，并且不得不说，他的插件生态丰富并且免费，因此占据我心中极高地位。

考虑到目前的网络较为混乱，特别是听说有小白因为不知道在哪儿下载`VSCode`而被骗钱，我专门写了这一节，这样一来就可以避免小白们花冤枉钱。

`VSCode`的下载地址：[[https://code.visualstudio.com/](https://code.visualstudio.com/)](https://code.visualstudio.com/)

我们根据自己的实际开发环境下载，例如使用`Deepin`或者`Ubuntu`的就下载`.deb`安装包，使用`Windows`的就下载`.exe`安装包。下载完成后安装即可。

### 1.2.4.1 插件推荐

下面我推荐几款`VSCode`插件，这也是我用的比较多的。

在打开`VSCode`页面后点击键盘`Ctrl+Shift+X`，弹出拓展栏，搜索以下插件并安装

- Chinese(Simplified) 中文包
- C/C++
- IntelliCode：自动补全代码（仅联网有效）
- Remote-SSH/Remote-WSL：连接远程服务器开发，如果使用`Windows`+`WSL`则该项必选
