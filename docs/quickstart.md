# QuickStart

## Installation
### For MacOS/Linux

Run the command below in terminal.

```bash
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/gvcgo/version-manager/main/scripts/install.sh | sh
```

### For Windows

Run the command below in powershell.

```bash
powershell -nop -c "iex(New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/gvcgo/version-manager/main/scripts/install.ps1')"
```

!> If you are using **VMR** on Windows11, you need to enable the **Developer Mode** as **VMR** requires to create symbolic links. If you're on Windows10, and any creating-symbolic-links-failure occurrs, you can try **VMR** with **Admin Privilege**.

!> Binaries built from go source code shows Virus Positive somehow on Windows. It's Totally False Positive. For details, Please see [here](https://go.dev/doc/faq#virus). When this happens, you need to manually add $HOME, $HOME\.vm, and the SDK-Installation-Dir you have specified, to the Trusted List.

!> **VMR** customized command **source** for refreshing **Path** env in current powershell.

### Where is VMR installed?

```bash
$HOME/.vm
```

### Can I customize the installation Dir for SDKs?

Of course. When you are installing VMR for the first time, **"Enter the SDK installation directory for vmr"** will prompt, you can just enter the path you want. If you've just input a wrong path, you can manually modify it in $HOME/.vm/config.json. 

![installation](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_install.png)

## Update VMR
### Method 1

Using the script provided by **VMR**.

```bash
vmr-update
```

### Method 2

Copy the installation command, and run it in terminal.

## Uninstallation

No scripts availble, but you can manually remove the directories listed below.
```bash
$HOME/.vm
SDK_Installation_Dir
```
