# Kernel Custom Configuration Guide

When performing cloud compilation using GitHub Actions, you can use the `kernel_config` parameter to specify a custom kernel configuration. Configuration files for each kernel version are named using the major version number (e.g., config-6.1). Refer to the settings in [compile-mainline-stable-kernel.yml](../.github/workflows/compile-mainline-stable-kernel.yml):

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.y_6.1.y
    kernel_auto: true
    kernel_config: kernel-config/release/stable
```

If no custom configuration is required, this parameter can be omitted. The default kernel configuration file [compile-kernel/tools/config](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel/tools/config) will be used for compilation. For more details, please refer to the [Kernel Compilation Guide](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel).

# 内核自定义配置说明

在 GitHub Actions 云编译时，可以使用 `kernel_config` 参数指定自定义内核配置。各内核版本的配置文件（config-k.x）以主版本号命名（例如：config-6.1），使用方法可参考 [compile-mainline-stable-kernel.yml](../.github/workflows/compile-mainline-stable-kernel.yml) 中的设置：

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.y_6.1.y
    kernel_auto: true
    kernel_config: kernel-config/release/stable
```

如果没有特殊需求，可以不指定自定义配置，编译时将采用默认内核配置文件 [compile-kernel/tools/config](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel/tools/config) 进行编译。更多详情请参考[内核编译说明](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel)文档。
