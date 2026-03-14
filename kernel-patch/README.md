# Kernel Patch Usage Guide

When performing cloud compilation using GitHub Actions, you can use the `kernel_patch` parameter to specify the directory containing kernel patches in your repository. Common kernel patches applicable to all kernel series use a fixed directory name (`common-kernel-patches`). Patches specific to a particular series, such as [linux-5.15.y](https://github.com/unifreq/linux-5.15.y), use a directory name `matching the kernel source repository name`. Directories with other custom names (such as the `deprecated-patches` directory for storing obsolete patches) will be skipped during kernel compilation and will not be applied.

```shell
~/kernel
    └── <your-kernel-patches>
        ├── common-kernel-patches  # Fixed directory name: Stores kernel patches common to all versions
        ├── linux-5.15.y           # Same as the kernel source library: stores dedicated patches
        ├── linux-6.1.y
        ├── linux-5.10.y-rk35xx
        └── more kernel directory...
```

The usage in the kernel compilation script can be found in the settings of [compile-mainline-beta-kernel.yml](../.github/workflows/compile-mainline-beta-kernel.yml):

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.1_6.1.1
    kernel_auto: true
    kernel_config: kernel-config/release/stable
    kernel_patch: kernel-patch/beta
    auto_patch: true
```

During kernel compilation, all patches with the `.patch` suffix under `common-kernel-patches` are enumerated and applied first, followed by the dedicated patches for the currently compiled kernel (e.g., linux-6.1.y). For more details, please refer to [Kernel Compilation Guide](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel) and [Kernel Patch Addition Guide](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/documents/README.md#9-compiling-armbian-kernel).

# 内核补丁使用说明

在 GitHub Actions 云编译时，可以使用 `kernel_patch` 参数指定内核补丁在仓库中的目录。其中适用于所有系列内核的通用补丁，采用固定目录名称（`common-kernel-patches`）；仅适用于指定系列的补丁，例如 [linux-5.15.y](https://github.com/unifreq/linux-5.15.y)，使用`与内核源码仓库同名`的目录名称。使用其他自定义名称的目录（例如存放已弃用补丁的 `deprecated-patches` 目录）在内核编译时将被跳过，不会被应用。

```shell
~/kernel
    └── <your-kernel-patches>
        ├── common-kernel-patches  # 固定目录名：存放各版本都通用的内核补丁
        ├── linux-5.15.y           # 与内核源码库同名：存放专用补丁
        ├── linux-6.1.y
        ├── linux-5.10.y-rk35xx
        └── more kernel directory...
```

在内核编译脚本中的使用方法可参考 [compile-mainline-beta-kernel.yml](../.github/workflows/compile-mainline-beta-kernel.yml) 中的设置：

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.1_6.1.1
    kernel_auto: true
    kernel_config: kernel-config/release/stable
    kernel_patch: kernel-patch/beta
    auto_patch: true
```

在编译内核时，会先遍历 `common-kernel-patches` 下后缀为 `.patch` 的全部补丁并应用，然后再遍历当前编译内核（如：linux-6.1.y）的专用补丁并应用。更多详情请参考[内核编译方法](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel)和[内核补丁添加方法](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/documents/README.cn.md#9-编译-armbian-内核)中的详细介绍。
