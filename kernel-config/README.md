# Kernel Personalized Configuration Guide

During cloud compilation using GitHub Actions, you can use the `kernel_config` parameter to specify personalized kernel configuration. The naming of the configuration files (config-k.x) of each kernel version uses the major version number (for example: config-6.1). You can refer to the settings in [compile-mainline-stable-kernel.yml](../.github/workflows/compile-mainline-stable-kernel.yml):

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.y_6.1.y
    kernel_auto: true
    kernel_config: kernel-config/release/stable
```

If there is no special requirement, you can proceed without specifying personalized configuration. The kernel default configuration file [compile-kernel/tools/config](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel/tools/config) will be used for kernel compilation. For more settings, please refer to the [Kernel Compilation Guide](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel) document.

# 内核个性化配置说明

在 GitHub Actions 云编译时，可以使用 `kernel_config` 参数指定个性化内核配置，各内核版本的配置文件（config-k.x）的命名使用主版本号（例如：config-6.1），使用方法可以参考 [compile-mainline-stable-kernel.yml](../.github/workflows/compile-mainline-stable-kernel.yml) 的设置：

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.y_6.1.y
    kernel_auto: true
    kernel_config: kernel-config/release/stable
```

如果没有特殊需求，可以不指定个性化配置，编译时将采用内核默认配置文件 [compile-kernel/tools/config](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel/tools/config) 进行内核编译。更多设置请查看[内核编译说明](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel)文档。
