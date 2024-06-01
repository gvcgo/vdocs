# Data flow

<!-- https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/vmr_install.png -->
![framwork.png](https://cdn.jsdelivr.net/gh/moqsien/img_repo@main/framework.png)

- [collector](https://github.com/gvcgo/collector) collects version list for SDKs and uploads the results to repo **resources**.
- [resources](https://github.com/gvcgo/resources) holds the version list for SDKs.
- [vmr](https://github.com/gvcgo/version-manager) is the user interface of the whole project.

The collector is deployed on a remote server, which users do never need to care about.
**VMR** fetches the prepared version list from repo **resources**, and shows/downloads the versions of an SDK.