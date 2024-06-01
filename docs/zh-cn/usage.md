# 使用方法

## 查看帮助命令

```bash
vmr -h


vmr <Command> <SubCommand> --flags args...

Usage:
   [command]

Command list: 
  clear-cache       Clears cached zip files for an app.
  env               Handles env manually.
  install-self      Installs version manager.
  list              Shows the supported applications.
  local             Shows installed versions for an app.
  search            Shows the available versions of an application.
  set-proxy         Sets proxy for version manager.
  set-reverse-proxy Sets reverse proxy for version manager.
  uninstall         Uninstalls a version or an app.
  use               Installs and switches to specified version.
  version           Shows version info of version-manager.

Additional Commands:
  completion        Generate the autocompletion script for the specified shell
  help              Help about any command

Flags:
  -h, --help   help for this command
```

## 设置代理

!> **反向代理和本地代理任选其一即可**。

### 设置反向代理

```bash
vmr sr "https://gvc.1710717.xyz/proxy/"
```

### 设置本地代理

```bash
vmr sp "http://localhost:xxx or socks5://localhost:xxx"
```

### 使用国内下载资源加速下载

!> **仅仅对部分SDK有效**。
```bash
vmr use -c sdk-name@version
```

## 查看支持的SDK列表

!> 按 **"j/k"** 键上下翻动列表，按 **"Enter/q"** 键退出，按 **"g/G"** 键快速跳转到列表顶部或底部。

```bash
vmr list
```
!> 退出之后，会根据选择的sdk名称自动生成**vmr search sdk-name**命令，并放入剪贴板。后续如果需要，可以直接粘贴使用。

## 搜索可以安装的版本

```bash
vmr search sdk-name
```
!> 退出之后，会根据选择的版本自动生成**vmr use sdk-name@version**命令，并放入剪贴板。后续如果需要，可以直接粘贴使用。

## 列出已经安装的版本

```bash
vmr local sdk-name
```
!> 退出之后，会根据选择的版本自动生成**vmr use sdk-name@version**命令，并放入剪贴板。后续如果需要，可以直接粘贴使用。

## 安装并切换到指定版本

- 查看子命令帮助信息。

```bash
vmr use -h


Example: vmr use go@1.22.1

Usage:
   use [flags]

Aliases:
  use, u

Flags:
  -E, --enable-locked-version   To enable the locked version for current project.
  -h, --help                    help for use
  -l, --lock                    To lock the sdk version for current project.
  -c, --mirror_in_china         To downlowd from mirror sites in China.
  -s, --session-only            To use a version only for the current terminal session.
  -t, --threads int             Number of threads for downloading. (default 1)
```

- 使用方法。

```bash
vmr use sdk-name@version
```

- 命令flag解释
  - **-E**，与**VMR**的**cd**命令的勾子函数有关，用户无需关心。
  - **-l**，对当前目录锁定SDK版本。
  - **-c**，使用国内资源下载，如果存在国内资源的话。
  - **-s**，新开一个终端会话，并在新终端中使用指定版本，退出该终端会话之后，该版本会失效。
  - **-t**，使用多少个线程进行下载。

!> 注意，当锁定SDK版本之后，使用**cd**命令切换到该目录下的任意位置，都能自动开启一个新的终端会话，然后切换到锁定版本。但是最好不要一直嵌套终端会话，使用完毕之后记得使用**exit**命令退出新开的终端会话。锁定版本的文件名为.vmr.lock。

!> 安装Python，PyPy，Scala时，会提示要先安装miniconda或者coursier，这时候只需要根据提示粘贴相关命令，然后继续按照提示操作即可。**VMR**不提供编译安装功能，因为每个用户的使用环境不一样，不能保证一定能编译成功。因此，使用Miniconda和Coursier这类稳定的二进制安装工具更为稳妥。

## 卸载指定版本

### 卸载单个版本

```bash
vmr uninstall sdk-name@version
```
!> 注意，指定指定的单个版本时，不能是当前正在使用的版本。需要卸载当前正在使用的版本时，可以先用**vmr use**切换到其他版本，然后再卸载。

### 卸载全部版本

```bash
vmr uninstall sdk-name@all
```
!> 注意，此命令会卸载sdk-name的全部版本，也包括当前正在使用的版本。


## 清理已缓存的SDK安装文件

```bash
vmr clear-cache sdk-name
```
    
!> 注意，此命令会清除sdk-name的所有本地已缓存的安装文件。

## 手动管理环境变量

- 增加环境变量

```bash
vmr env key=value
```

- 删除环境变量

```bash
vmr env -r key=value
```