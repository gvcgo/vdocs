# VMR数据流

<!-- https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_install.png -->
![framwork.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/framework.png)

- [collector](https://github.com/gvcgo/collector) 收集版本信息并上传到 **resources** 仓库。
- [resources](https://github.com/gvcgo/resources) 存储版本信息。
- [vmr](https://github.com/gvcgo/version-manager) 用户界面。

**collector**部署在远程服务器上, 会定时从官网获取最新的版本列表。这部分用户无需关心。

**VMR** 从 **resources** 仓库获取版本信息(注意，不是安装文件), 然后向用户展示，或者根据用户的选择从官网进行相关下载安装。

用户可以到**resources**仓库查看版本列表，其中包含了各种SDK的下载链接，均来自官网或者Github。这样做的好处在于，即使官网改版，用户仍然能够稳定的使用**VMR**。
一般来说，SDK的发布周期都很长，用户也无需频繁地更新到最新版，**collector**的同步频率是够用的。
