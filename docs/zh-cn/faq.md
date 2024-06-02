# 常见问题

### 1. 如何使用？

使用**vmr -h**查看帮助信息。
使用**vmr subcommand -h**查看子命令帮助信息。

### 2. 安装之后如何设置SDK安装目录？

编辑配置文件$HOME/.vmr/config.toml。

### 3. 为什么下载失败？

请检查是否设置了反向代理(reverse proxy)。如果添加了反向代理，获取**SDK列表**时仍然比较慢，你也可以在vmr的配置文件中设置**VersionHostUrl**为**https://gitee.com/moqsien/vsources/raw/main**。

### 4. 下载源安全吗？

安全。所有资源均来自各种SDK的官方下载链接或者github仓库的release。
你可以在 [这里](https://github.com/gvcgo/vsources) 查看所有的版本SDK信息，包括具体SDK的下载地址。

### 5. MacOS/Linux下，环境变量放在什么地方？

在$HOME/.vmr/vmr.sh或$HOME/.vmr/vmr.fish者中，然后在.bashrc或者.zshrc中进行引用。这样可以保证.bashrc或者.zshrc的整洁。

### 6. 什么是反向代理？

**https://gvc.1710717.xyz/proxy/** 是一个部署在CloudFlare上的反向转发代理，主要用于加速github的国内访问。但是限制了只能访问VMR相关的内容。完全免费。你也可以参考[这个项目](https://github.com/gaboolic/cloudflare-reverse-proxy)来部署自己的反向代理，然后给到VMR使用，这样可以大大降低公用反向代理的压力。
