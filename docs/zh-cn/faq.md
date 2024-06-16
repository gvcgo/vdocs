# 常见问题

### 1. 如何使用？

- 使用**vmr**命令打开TUI，TUI界面有丰富的按键提示(key map)，很简单的英文，注意查看。
- 使用**vmr -h**命令查看帮助信息。
- 使用**vmr subcommand -h**命令查看子命令帮助信息。

### 2. 安装之后如何设置SDK安装目录？

编辑配置文件$HOME/.vmr/config.toml。


### 3. Unix-like操作系统下，环境变量存放在什么地方？

```bash
$HOME/.vmr/vmr.sh 或者 $HOME/.vmr/vmr.fish
```

### 4. 为什么下载失败？为什么不显示SDK列表？

VMR的很多资源，包括版本信息仓库和VMR安装包，都来自github，而国内github访问受限，导致下载速度慢。解决方法如下：

- 使用**vmr sp "http://localhost:xxx or socks5://localhost:xxx"** 设置你自己的代理。
- 使用**vmr sr "https://proxy.vmr.us.kg/proxy/"** 设置VMR提供的反向代理，加速github相关的下载。
- 对于依赖于conda的SDK，为了加速安装，可以配置国内的conda源，例如[清华源](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/?eqid=b45767b90013072c00000005649051db)。

如果添加了代理，获取**SDK列表**时仍然比较慢，你也可以在vmr的配置文件中设置**VersionHostUrl**为**https://gitee.com/moqsien/vsources/raw/main**。

### 5. 什么是反向代理？

**https://proxy.vmr.us.kg/proxy/** 是一个部署在CloudFlare上的反向转发代理，主要用于加速github的国内访问。但是限制了只能访问VMR相关的内容。完全免费。

你也可以参考[这个项目](https://github.com/gaboolic/cloudflare-reverse-proxy)来部署自己的反向代理，然后给到VMR使用，这样可以大大降低公用反向代理的压力。


### 6. 什么是Session模式和Global模式？

指的是安装或者使用某个SDK的方式。
- Session模式下，VMR不会自动持久化相关环境变量到文件中，而是打开一个新的终端Session，将相关SDK的环境变量临时添加到这个Session中，当Session关闭之后，环境变量会自动失效。
- Global模式下，VMR会自动持久化环境变量到文件中，这样的环境变量才是永久有效的。

**在安装、切换SDK版本时，注意key map中的提示，根据自己的需要，选择Session或者Global模式**。
![key_map](https://cdn.jsdelivr.net/gh/moqsien/conf_backup@main/key_map.png)


### 7. 如何针对项目锁定SDK版本？实现原理是什么？

在VMR的**TUI**中，key map按键功能提示区，留意看一下，会发现有提示lock version的按键，即可针对当前项目锁定选择的SDK版本，锁定版本之后，会在当前项目下生成一个叫做 **.vmr.lock** 的文件。该文件支持对同一个项目，锁定多个SDK的版本。比如，你可以同时锁定python和node的版本等等。

锁定版本的原理是，在bash/zsh/fish/powershell中，VMR分别配置了cd命令的hook，当在终端使用cd命令切换目录时，就会执行到该hook，该hook又会调用**vmr use -E**命令，从而检查当前目录是否在某个锁定版本的项目之中，然后打开新的终端session，临时切换版本。至于**vmr use -E**命令，用户无需关心。

### 8. 安装一个SDK之后，当前终端没有找到相关命令？

**VMR**默认不打开新的终端session，所以你需要使用source命令刷新一下环境变量。

另外，**VMR**也为Windows用户贴心地提供了**source**命令，在**VMR**安装过程中就已经集成到系统powershell配置文件中，所以Windows用户也能愉快地使用source命令刷新PATH环境变量了。

### 9. 为什么Windows下的一部分SDK无法运行？

例如，Windows下的agg, php等等。可能是缺少**Microsoft Visual C++ Redistributable**，可以到官网[下载](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170)安装。

### 10. 下载源安全吗？

安全。所有资源均来自各种SDK的官方下载链接或者github仓库的release。
你可以在 [这里](https://github.com/gvcgo/vsources) 查看所有的版本SDK信息，包括具体SDK的下载地址。
