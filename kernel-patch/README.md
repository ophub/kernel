# Kernel Patches Description

During GitHub Actions cloud compilation, you can use the `kernel_patch` parameter to specify the directory in your repository where the kernel patches are located. The common kernel patches are stored in a fixed directory name (`common-kernel-patches`), while patches specific to a designated kernel version (e.g., `linux-5.15.y`) should be placed in a directory with the same name as `the kernel source repository`. Any other custom-named directories (such as the one for storing deprecated patches, `deprecated-patches`) will be ignored during kernel compilation.

```shell
~/kernel
    └── <your-kernel-patches>
        ├── common-kernel-patches  # Fixed directory name: Storing common kernel patches
        ├── linux-5.15.y           # Same as kernel source repository: storing dedicated kernel patches
        ├── linux-6.1.y
        ├── linux-5.10.y-rk35xx
        └── more kernel directory...
```

You can refer to the settings in [compile-beta-kernel.yml](../.github/workflows/compile-beta-kernel.yml) for usage examples in kernel compilation scripts.

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.1_6.1.1
    kernel_auto: true
    kernel_config: kernel-config/beta
    kernel_patch: kernel-patch/beta
    auto_patch: true
```

When compiling the kernel, all patches with the suffix `.patch` under `common-kernel-patches` are first traversed and applied, followed by the private patches for the current compiled kernel (such as: linux-6.1.y). For more information, please refer to the detailed introduction in [Kernel Compilation Method](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel) and [Kernel Patch Addition Method](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/build-armbian/documents#9-compile-armbian-kernel).

# 内核补丁使用说明

在 GitHub Actions 云编译时，可以使用 `kernel_patch` 参数指定内核补丁在你仓库中的目录。其中通用内核补丁采用固定目录名称（`common-kernel-patches`），仅适用于指定内核版本（例如 `linux-5.15.y`）的补丁使用 `与内核源码库同名` 的目录名称。使用其他自定义命名的目录（例如存放已弃用补丁的目录`deprecated-patches`）在内核编译时将忽略。

```shell
~/kernel
    └── <your-kernel-patches>
        ├── common-kernel-patches  # 固定目录名：存放各版本都通用的内核补丁
        ├── linux-5.15.y           # 与内核源码库同名：存放专用补丁
        ├── linux-6.1.y
        ├── linux-5.10.y-rk35xx
        └── more kernel directory...
```

在内核编译脚本中使用方法可以参考 [compile-beta-kernel.yml](../.github/workflows/compile-beta-kernel.yml) 的设置：

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.15.1_6.1.1
    kernel_auto: true
    kernel_config: kernel-config/beta
    kernel_patch: kernel-patch/beta
    auto_patch: true
```

在编译内核时，会先遍列 `common-kernel-patches` 下后缀是 `.patch` 的全部补丁并应用，然后再遍列当前编译内核（如：linux-6.1.y）的专用补丁并应用。更多说明请参考 [内核编译方法](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel) 和 [内核补丁添加方法](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/build-armbian/documents/README.cn.md#9-编译-armbian-内核) 中的详细介绍。
