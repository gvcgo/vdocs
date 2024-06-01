# Usage

## Check the help info for VMR.

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

## Set a proxy.

!> Choose either **reverse proxy** or **local proxy**.

### Set reverse proxy.

```bash
vmr sr "https://gvc.1710717.xyz/proxy/"
```

### Set local proxy.

```bash
vmr sp "http://localhost:xxx or socks5://localhost:xxx"
```

## About TUI

### Start
```bash
vmr
```
![sdk_list.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_sdk_list.png)

- 1: Enter keyword to search for an SDK name.
- 2: Key map for next step.
- 3: SDK name list.

### Search SDK name by keyword.
![sdk_search.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_sdk_search.png)

Same as above.

### Show SDK version list.
![sdk_version.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_version_list.png)

Same as above.

### Search version by keyword.
![version_search.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_version_search.png)

Same as above.

### Show installed list.
![local_list.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_local_list.png)

Same as above.

### Search installed version by keyword.
![local_search.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_local_search.png)

Same as above.
