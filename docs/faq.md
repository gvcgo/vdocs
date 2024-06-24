# FAQs

### 1. How to use?

- Open TUI for VMR with **vmr**.
- See help inof with **vmr -h**.
- See help info for subcommand with **vmr subcommand -h**.

### 2. How to change installation path for SDKs after installation?

You can edit the config file **$HOME/.vmr/config.toml**.

### 3. Where are the envs restored for Unix-like systems?

```bash
$HOME/.vmr/vmr.sh or $HOME/.vmr/vmr.fish
```

### 4. Why download SDK fails? Why No SDK Found?

Lots of resources required by VMR are from github, which seems to be blocked in China. Solutions are:

- Set your own proxy with command **vmr sp "http://localhost:xxx or socks5://localhost:xxx"**.
- Set reverse proxy provided by VMR with command **vmr sr "https://proxy.vmr.us.kg/proxy/"**.
- For SDKs using conda, you can set other mirrors instead of the official one, such as [tsinghua](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/?eqid=b45767b90013072c00000005649051db).

if a proxy or reverse proxy is added, and VMR still respond slowly, you can try to modify the **VersionHostUrl** as **https://gitee.com/moqsien/vsources/raw/main** in config file of VMR.


### 5. What is reverse proxy？

**https://proxy.vmr.us.kg/proxy/** is deployed on CloudFlare for github accelerations. It's totally free.

You can also deploy your own reverse proxy according to this [repo](https://github.com/gaboolic/cloudflare-reverse-proxy).

### 6. What are Session Mode and Global Mode?

They are the ways how an SDK is installed or used.

- For Session Mode, a new terminal session is opened, and envs are added to this session without saving to any files. When the session is closed, these envs become invalid.
- For Global Mode, envs are added to related files and will take effect for all new terminal sessions.

You need to pay attention to the **key map** hints in TUI of VMR for these modes.

![key_map](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/conf_backup@main/key_map.png)

### 7. How to lock the SDK version for a project? And how is it implemented?

In the **TUI** of VMR, there is a region for showing key bindings, you'll find somthing like **lock version** there.

Press the key that binds to version-locking, and you'll find a file named **.vmr.lock** is generated for current project.
**VMR** hooks the **cd** command for bash/zsh/fish/powershell. When using **cd** in terminal, the hook will be executed, and the command **vmr use -E** is called.

### 8. After the installation of an SDK，how should I found the related command？

**VMR** do not open new terminal session by default, so, you need to use **source** command to refresh the envs for current terminal. 

On windows, **VMR** also customized the **source** command for users. It is integrated to the powershell config file during the installation process of **VMR**. And you can use **source** to refresh **PATH** env in any powershell session.

### 9. Why some of the SDKs on Windows can not run properly？

For example, agg, php, etc. It may be caused by lacking of **Microsoft Visual C++ Redistributable**. You can download it from [here](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170).


### 10. Is it safe to use **VMR**?

Of course. All the SDKs are downloaded from the **official websites**, or **github releases**, or **Anaconda Forge**. 
VMR at now is not planning to provide anything like compilation from source code since stability issues cannot be avoided.
You can also check the version info [here](https://github.com/gvcgo/vsources).

### 11. "Extract file failed" error occurs over and over again?

This may occur on windows. Try to **clear the cached files** in the **cache dir** for the SDK, and try to install the SDK again.

![clear_cache](https://proxy.vmr.us.kg/proxy/https://cdn.jsdelivr.net/gh/moqsien/moqsien/img_repo@main/vmr_clear_cache.png)
