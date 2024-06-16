# 使用方法

## 显示帮助信息

```bash
linux:~/$ vmr -h
vmr <Command> <SubCommand> --flags args...

Usage:
  vmr [flags]
  vmr [command]

Command list: 
  install-self      Installs version manager.
  set-proxy         Sets proxy for version manager.
  set-reverse-proxy Sets reverse proxy for version manager.
  uninstall-self    Uninstalls version manager, Only for script.
  use               This is the hook for command cd.
  version           Shows version info of version-manager.

Additional Commands:
  completion        Generate the autocompletion script for the specified shell
  help              Help about any command

Flags:
  -h, --help   help for vmr

Use "vmr [command] --help" for more information about a command.
```

## 设置代理

!> 在 **反向代理** 和 **本地代理**中任选其一即可。

### 设置反向代理

```bash
vmr sr "https://proxy.vmr.us.kg/proxy/"
```

### 设置本地代理

```bash
vmr sp "http://localhost:xxx or socks5://localhost:xxx"
```

## TUI使用方法

### 打开TUI
输入**vmr**命令，不带任何参数。
```bash
vmr
```
![sdk_list.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_sdk_list.png)

- 区域1: 输入关键字进行搜索。
- 区域2: 关于下一步的快捷键提示。
- 区域3: 显示SDK名称列表(如果仅显示区域1和区域2，可能是因为你的终端窗口太小，请尝试调整窗口大小)。

### 使用关键字搜索SDK
**注意**：只支持从头开始匹配。
![sdk_search.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_sdk_search.png)

同上。

### 展示版本列表
![sdk_version.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_version_list.png)

同上。

### 通过关键字搜索版本号
![version_search.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_version_search.png)

同上。

### 展示已安装的版本
![local_list.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_local_list.png)

同上。

### 搜索已安装的版本
![local_search.png](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_local_search.png)

同上。
