# Usage

## Check the help info for VMR.

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

### Download files using resources in China.

!> Only for part of SDKs。
```bash
vmr use -c sdk-name@version
```

## List the supported SDKs.

!> Press **"j/k"** to move up/down，**"Enter/q"** to quit the table exhibition，**"g/G"** to skip to top/bottom.

```bash
vmr list
```
!> After exit, command **vmr search sdk-name** is generated and added to clipboard for furter use.

## Search the available versions of an SDK.

```bash
vmr search sdk-name
```
!> After exit, command **vmr use sdk-name@version** is generated and added to clipboard for furter use.

## List the installed versions of an SDK.

```bash
vmr local sdk-name
```
!> After exit, command **vmr use sdk-name@version** is generated and added to clipboard for furter use.

## Installs and swithes to a specified version.

- See help info.

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

- How to use.

```bash
vmr use sdk-name@version
```

- flags
  - **-E**，related to **cd hook**, users should never use.
  - **-l**，locks SDK version for current dir.
  - **-c**，downloads files from mirror sites in China.
  - **-s**，Opens a new termianl session and swithes to the specified version.
  - **-t**，How many threads to use for downloading.

!> If a version is locked for a project, a file named **.vmr.lock** is generated in the project. When you are changing dir to some where in this project using command **cd**, a new terminal session will be opened with the locked version enabled. After you exit the new terminal session, the locked version will be diabled.

!> **VMR** does not support compilation for SDKs from source code. So, when you are installing Python, PyPy, or Scala, a requirement for Miniconda or Coursier will pop-up. Just follow the hints, install Miniconda or Coursier, and continue to install the SDKs.

## Uninstalls versions.

### Unistalls a specific version.

```bash
vmr uninstall sdk-name@version
```
!> You can't uninstalled the version that is currently in use with this command.

### Uninstalls all versions for an SDK.

```bash
vmr uninstall sdk-name@all
```
!> This command will uninstall all version of sdk-name, including the one that is currently in use.

## Clear the cached files.

```bash
vmr clear-cache sdk-name
```
    
!> This command will delete all the cached files for sdk-name.

## Manually handles env.

- Add an env.

```bash
vmr env key=value
```

- Removes an env.

```bash
vmr env -r key=value
```
