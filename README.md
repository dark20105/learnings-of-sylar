# learnings-of-sylar
sylar 框架学习记录

# 当前进度
| 日期    |  进度   | 收获 |
|----     | --- | --- |
| 2021.12.06 | 项目创建 | 真正开始使用 github |

# 项目描述
这个项目是我学习国人大佬 sylar-yin 写的高性能服务器框架 sylar 的一个记录，敦促自己学习的同时也把自己的收获分享给大家。

项目原地址：https://github.com/sylar-yin/sylar

另一个大佬的 sylar 重写项目：https://github.com/zhongluqiang/sylar-from-scratch

这个项目的学习文档会放到 csdn 上面，这里只是存放代码。

# 环境搭建
具体环境可以参照 上面两位大佬的：

1. sylar 本人的环境配置：http://www.sylar.top/blog/?p=94
2. luqiang大佬的环境配置：https://www.midlane.top/wiki/pages/viewpage.action?pageId=16416843
3. 我的配置（一下的命令只适用于 ArchLinux 系的系统）：
   1. 开发平台：ArchLinux ：5.14.16-arch1-1 #1 SMP PREEMPT Tue, 02 Nov 2021 22:22:59 +0000 x86_64 GNU/Linux
   2. GCC：gcc (GCC) 11.1.0
   3. boost 库安装： `sudo pacman -S boost`
   4. 其他工具：`sudo pacman -S cmake make`
   5. 目前我还没有看到 sylar 框架的其他部分，所以还需要什么配置暂时还不知道，如果之后看到了也会更新本文

# 项目结构

```shell
$ tree -L 1
.
├── cmake
├── CMakeLists.txt
├── component
├── inc
├── plugin
├── src
├── tests
└── tools

7 directories, 2 files
```
总共有 11(这里删掉了 `build` 、 `bin`、`lib`、`lib`) 个目录和 1 个文本。

| 名称 | 类型                         | 作用 |
| ---- | ---------------------------- | ---- |
| src | 目录 |  存储框架中的主要进程相关源文件  |
| inc | 目录 |   存储框架中的主要进程相关头文件   |
| doc | 目录 | 存放文档 |
| plugin | 目录 | 存放第三方库文件、或是项目中独立的模块文件 |
| component | 目录 | 存放项目中可以独立出来供其他项目使用的依赖项 |
| tests | 目录 | 存放测试各个模块用的源文件 |
| build | 目录 | 存放编译的中间文件 |
| bin | 目录 | 存放生成的可执行文件|
| lib | 目录 | 存放生成的库文件 |
| log | 目录 | 存放程序运行期间生成的日志文件|
| cmake | 目录 | 存放 cmake 配置相关文件 |
| CMakeLists.txt | 文本文件 | 用于 cmake 编译 |


# 联系方式
我的联系方式如下：

QQ：1097844647
邮箱：1097844647@qq.com
