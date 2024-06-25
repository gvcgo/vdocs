# 快速开始

## 安装
### MacOS或Linux下的安装

复制以下命令，并在终端中执行。

```bash
curl --proto '=https' --tlsv1.2 -sSf https://scripts.vmr.us.kg | sh
```

### Windows下的安装

复制以下命令，并在Powershell中执行。

```powershell
powershell -c "irm https://scripts.vmr.us.kg/windows | iex"
```

!> 使用go源码编译得到的Windows可执行文件，经常被windows的defender**误报**为病毒，详见[go语言官方的解释](https://go.dev/doc/faq#virus)。 为了解决这个问题，**VMR**使用**osslsigncode**对windows可执行文件进行了签名，但无法保证一定没有误报。如果仍然出现误报，请手动添加和**VMR**有关的文件夹到信任列表，或者尝试下载**VMR**的[签名证书](https://github.com/gvcgo/version-manager/blob/main/scripts/vmr.pfx)进行安装。

!> **VMR**定制了**source**命令，可以用于在当前Powershell中刷新Path环境变量。

!> Windows下安装**VMR**之后，如果在powershell中遇到类似**ps1 cannot be loaded because running scripts is disabled on this system**的报错，可以使用以下命令解决。具体[参考](https://stackoverflow.com/questions/41117421/ps1-cannot-be-loaded-because-running-scripts-is-disabled-on-this-system)。

```bash
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope CurrentUser
```

### 国内用户安装太慢怎么办？

这与GFW有关，你可以使用代理。

- MacOS或Linux下终端使用代理。
```bash
export ALL_PROXY="http://127.0.0.1:xxxx"
# export ALL_PROXY="socks5://127.0.0.1:xxxx"
```

- Windows的Powershell中使用代理。
```powershell
$env:all_proxy="http://127.0.0.1:xxxx"
# $env:all_proxy="socks5://127.0.0.1:xxxx"
```

### VMR安装在哪里？

```bash
$HOME/.vmr/
```

### Unix-like系统下，环境变量放在哪里?

```bash
$HOME/.vmr/vmr.sh 或 $HOME/.vmr/vmr.fish
```

### 可以指定SDK的安装目录吗？

可以。在首次安装**VMR**的时候，会提示你设置**SDK Installation Dir**，这时候在输入框中输入你想要定制的SDK安装路径即可。
如果你不小心输入错误了，你也可以在 **$HOME/.vmr/config.toml** 配置文件中手动修改。

![installation](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_install_dir.png)

### 如何打开TUI?

```bash
vmr
```

### 无法显示SDK列表?

你需要设置代理(http或者socks5)；或者你也可以设置由VMR提供的免费反向代理，详见[这里](https://docs.vmr.us.kg/#/zh-cn/usage?id=%e8%ae%be%e7%bd%ae%e4%bb%a3%e7%90%86)。 **强烈建议使用自己的代理，因为反向代理不一定稳定，容易被墙** 。

## 更新
### 方法一

使用VMR自带的更新脚本命令。(不要切换到.vmr/中执行，否则会更新失败)
```bash
vmr-update
```

### 方法二 

复制上面的安装命令到终端中执行。

## 卸载

使用**VMR**提供的卸载脚本命令。(不要切换到.vmr/中执行)
```bash
vmr-uninstall
```
