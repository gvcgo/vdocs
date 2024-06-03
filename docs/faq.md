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
