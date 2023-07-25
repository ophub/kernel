# Kernel Description

View Chinese description  |  [查看中文说明](README.cn.md)

These kernels can be used for `Armbian` and `OpenWrt` systems, such as the [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian), [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt), [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions), and [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit) projects. They can be integrated when compiling firmware or installed in an existing system. For specific usage methods, see the [Kernel Use Instructions](https://github.com/ophub/amlogic-s9xxx-armbian/blob/main/compile-kernel/README.cn.md#内核使用说明).

Among them, [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy), [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable), and [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) are interchangeable general-purpose kernels. Flippy's feature is understanding you better, stable's feature is more considerate, and dev's feature is smoother.

- The kernel files in the [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) section of the Releases are `stable version`, which are series kernels shared by `flippy`.
- The kernel files in the [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) section of the Releases are `stable version`, which have enabled more support options according to user needs.
- The kernel files in the [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) section of the Releases are `development version`, which added third-party driver support and special modifications for some specific boxes.
- The kernel files in the [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) section of the Releases are `special version` for the `rk3588` series, and they are not compatible with other series.
- The kernel files in the [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) section of the Releases are `beta version`, which support custom addition of third-party driver patches, and allow custom configuration compilation.
- The [dev](https://github.com/ophub/kernel/releases/tag/dev) section in the Releases has the download image of the `cross-compilation toolchain` required when compiling the kernel.
- The [tools](https://github.com/ophub/kernel/releases/tag/tools) section in the Releases has download images of `Android systems` for some common TV boxes, which can be used to restore the Android system when using Armbian and OpenWrt systems.


## Kernel Compilation

- For the method of kernel compilation, please refer to [compile-kernel](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel). For the method of kernel compilation using Actions on github.com, refer to [.github/workflows](.github/workflows). You can customize the kernel by modifying the kernel configuration files in [kernel-config](kernel-config), and add custom kernel patches in the [kernel-patch](kernel-patch) directory.

- You can adjust the configuration of the kernel according to your needs, such as adding drivers and patches. You can also compile a personalized signature kernel with special meaning according to your mood, such as `5.10.95-happy-new-year`, `5.10.96-beijing-winter-olympics`, `5.10.99-valentines-day`, etc.

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.10.135_5.15.50
    kernel_auto: true
    kernel_sign: -yourname
```

## Kernel Source Code

A big thank you to unifreq and others for maintaining the kernel source code. The source code used in the kernel files in the repository is as follows:

| Kernel Tags   | Source Code Repository  |
| ------------- | ----------------------- |
| [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy)<br>[kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)<br>[kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev)<br>[kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) | [unifreq/linux-5.4.y](https://github.com/unifreq/linux-5.4.y)<br>[unifreq/linux-5.10.y](https://github.com/unifreq/linux-5.10.y)<br>[unifreq/linux-5.15.y](https://github.com/unifreq/linux-5.15.y)<br>[unifreq/linux-6.1.y](https://github.com/unifreq/linux-6.1.y) |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [unifreq/linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx) |

## Links

- [unifreq/kernel](https://github.com/unifreq)
- [chewitt/linux](https://github.com/chewitt/linux)
- [torvalds/linux](https://github.com/torvalds/linux)
- [kernel.org](https://kernel.org)

## License

The kernel © OPHUB is licensed under [GPL-2.0](https://github.com/ophub/kernel/blob/main/LICENSE)
