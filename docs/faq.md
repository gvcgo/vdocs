# FAQs

### 1. How to use?

See help inof with **vmr -h**.
See help info for subcommand with **vmr subcommand -h**.

### 2. How to change installation path for SDKs after installation?

You can edit the config file **$HOME/.vmr/config.toml**.

### 3. Why download SDK fails?

Try to set the **reverse proxy**.

### 4. Is it safe to use **VMR**?

Of course. All the SDKs are downloaded from the official websites or github releases. You can check the version info [here](https://github.com/gvcgo/vsources).

### 5. Where does **VMR** store the envs for SDKs?

In **$HOME/.vm/vmr.sh** or **$HOME/.vmr/vmr.fish**.

### 6. What is reverse proxy？

**https://gvc.1710717.xyz/proxy/** is deployed on CloudFlare for github accelerations. It's totally free.

### 7. How to lock the SDK version for a project? And how is it implemented?

In the **TUI** of VMR, there is a region for showing key bindings, you'll find somthing like **lock version** there.
Press the key that binds to version-locking, and you'll find a file named **.vmr.lock** is generated for current project.
**VMR** hooks the **cd** command for bash/zsh/fish/powershell. When using **cd** in terminal, the hook will be executed, and the command **vmr use -E** is called.

### 8. After the installation of an SDK，how should I found the related command？

**VMR** do not open new terminal session by default, so, you need to use **source** command to refresh the envs for current terminal. On windows, **VMR** also customized the **source** command for users. It is integrated to the powershell config file during the installation process of **VMR**. And you can use **source** to refresh **PATH** env in any powershell session.

### 9. Why some of the SDKs on Windows can not run properly？

For example, agg, php, etc. It may be caused by lacking of **Microsoft Visual C++ Redistributable**. You can download it from [here](https://learn.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170).

### 10. What are Session Mode or Global Mode?

![session_mode](https://cdn.jsdelivr.net/gh/moqsien/conf_backup@main/session_mode.png
)
1. Global Mode: Add envs to **$HOME/.vmr/vmr.sh** or  **$HOME/.vmr/vmr.fish**.
2. Session Mode: Add envs only to current new session, **no persistent storage**.
