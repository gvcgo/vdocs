# QuickStart

## Installation
### For MacOS/Linux

Run the command below in terminal.

```bash
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/gvcgo/version-manager/main/scripts/install.preview.sh | sh
```

Use Following command when **github.com** happens to be slow.
```bash
curl --proto '=https' --tlsv1.2 -sSf https://scripts.vmr.us.kg | sh
```

### For Windows

Run the command below in powershell.

```bash
powershell -c "irm https://scripts.vmr.us.kg/windows | iex"
```
    

!> Binaries built from go source code shows Virus **False Positive** somehow on Windows. You can learn that from go official website, see [here](https://go.dev/doc/faq#virus). **VMR** is signed by **osslsigncode** to avoid this annoying situation. However, we cannot ensure that **False Positive** will never happen. In case of **False Positive**, you can manually add the **VMR** directory to your **Trusted** directory, or try to install the certificate [here](https://github.com/gvcgo/version-manager/blob/main/scripts/vmr.pfx).

!> **VMR** customized command **source** for refreshing **Path** env in current powershell.

!> If an error like **ps1 cannot be loaded because running scripts is disabled on this system** occurrs in powershell, try the following command. See [here](https://stackoverflow.com/questions/41117421/ps1-cannot-be-loaded-because-running-scripts-is-disabled-on-this-system) for details.

```bash
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope CurrentUser
```

### Where is VMR installed?

```bash
$HOME/.vmr/
```

### Where are envs restored on Unix-like systems?

```bash
$HOME/.vmr/vmr.sh 或 $HOME/.vmr/vmr.fish
```

### Can I customize the installation Dir for SDKs?

Of course. When you are installing VMR for the first time, a hint will prompt asking for customizing your **SDK Installation Dir**, you can just enter the path you want. If you've just input a wrong path, you can manually modify it in **$HOME/.vmr/config.toml**. 

![installation](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_install_dir.png)

### How to use TUI?

```bash
vmr
```

### Why "No SDK Found"?

You need to set a proxy or reverse proxy, see [here](https://docs.vmr.us.kg/#/usage?id=set-a-proxy).

## Update VMR
### Method 1

Use the script provided by **VMR**.

```bash
vmr-update
```

### Method 2

Copy the installation command, and run it in terminal.

## Uninstallation

Use the script provided by **VMR**.

```bash
vmr-uninstall
```
