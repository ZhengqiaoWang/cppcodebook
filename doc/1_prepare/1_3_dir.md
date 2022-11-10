# 1.3 目录规范

事实上目前目录规范有一些普遍做法，我们可以打开`Github`中的一些不错的开源项目就可以大致知道目前`C++`的目录规范是什么样的。在我看来，目录规范普遍遵循最小生命周期原则——如果某代码只被某模块使用，那就应该与某模块放一起。于是对于一个项目来说，我们采用的一种目录规范是这样的：

- 项目目录
  - bin：存放编译完成的结果
  - include：引入的第三方头文件
  - common：项目公共的代码文件
  - lib：引入的三方库
  - third_party：引入的子模块
    - grpc
    - libevent
    - ....
  - interface：项目接口
  - app1：进程1或库1
    - include：进程1独自引用的第三方头文件
    - interface：进程1独自的对外接口
    - etc：配置文件
    - lib：进程1引用的三方库
    - src：进程1的代码文件
  - app2：进程2或库2
    - include：进程2独自引用的第三方头文件
    - interface：进程2独自的对外接口
    - etc：配置文件
    - lib：进程2引用的三方库
    - src：进程2的代码文件
  - ut：单元测试
    - common: 公共代码单元测试
    - app1：app1单元测试
    - app2：app2单元测试
  - tools: 项目工具集合
  - README.md 项目主页
  - .gitignore git忽略规则

以上就是我常用的目录结构，使用如此结构可以有效地嵌套`makefile`以及`CMake`，特别是`third_party`的引入可以避免要求其他开发者配置环境，只需要大家有一个默认环境，就可以统一地编译运行。

当然，根据项目的不同，目录结构也有一定的调整，例如一些开源项目中，会额外包含`example`，`doc`等目录结构（可以参考[JArgsParser](https://github.com/ZhengqiaoWang/JArgsParser)），我们同样可以在上面的基础上进行增删，我只是提出了一个我们使用起来比较成熟的方案。

快去试一试吧~ 或者访问[1_prepare/1_3_dir](../../cpp/1_prepare/1_3_dir/)以及[EmptyCppDirectory](https://github.com/ZhengqiaoWang/emptycppdirectory)拿到一个完整的目录结构吧。
