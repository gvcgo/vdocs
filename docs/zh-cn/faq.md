# 常见问题

### 1. 如何使用？

使用**vmr -h**查看帮助信息。
使用**vmr subcommand -h**查看子命令帮助信息。

### 2. 安装之后如何设置SDK安装目录？

编辑配置文件$HOME/.vmr/config.toml。

### 3. 为什么下载失败？

- 请检查是否设置了反向代理(reverse proxy)。如果添加了反向代理，获取**SDK列表**时仍然比较慢，你也可以在vmr的配置文件中设置**VersionHostUrl**为**https://gitee.com/moqsien/vsources/raw/main**。
- 对于依赖于conda的SDK，为了加速安装，可以配置国内的conda源，例如[清华源](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/?eqid=b45767b90013072c00000005649051db)。

### 4. 下载源安全吗？

安全。所有资源均来自各种SDK的官方下载链接或者github仓库的release。
你可以在 [这里](https://github.com/gvcgo/vsources) 查看所有的版本SDK信息，包括具体SDK的下载地址。

### 5. MacOS/Linux下，环境变量放在什么地方？

在$HOME/.vmr/vmr.sh或$HOME/.vmr/vmr.fish者中，然后在.bashrc或者.zshrc中进行引用。这样可以保证.bashrc或者.zshrc的整洁。

### 6. 什么是反向代理？

**https://gvc.1710717.xyz/proxy/** 是一个部署在CloudFlare上的反向转发代理，主要用于加速github的国内访问。但是限制了只能访问VMR相关的内容。完全免费。你也可以参考[这个项目](https://github.com/gaboolic/cloudflare-reverse-proxy)来部署自己的反向代理，然后给到VMR使用，这样可以大大降低公用反向代理的压力。

### 7. 如何针对项目锁定SDK版本？实现原理是什么？

在VMR的**TUI**中，区域2是按键功能提示区，留意看一下，会发现有提示lock version的按键，即可针对当前项目锁定选择的SDK版本，锁定版本之后，会在当前项目下生成一个叫做 **.vmr.lock** 的文件。该文件支持对同一个项目，锁定多个SDK的版本。比如，你可以同时锁定python和node的版本等等。

锁定版本的原理是，在bash/zsh/fish/powershell中，VMR分别配置了cd命令的hook，当在终端使用cd命令切换目录时，就会执行到该hook，该hook又会调用**vmr use -E**命令，从而检查当前目录是否在某个锁定版本的项目之中，然后打开新的终端session，临时切换版本。至于**vmr use -E**命令，用户无需关心。
