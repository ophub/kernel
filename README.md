# Kernel Description

View Chinese description  |  [查看中文说明](README.cn.md)

These kernels can be used on `Armbian` and `OpenWrt` systems, such as [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian), [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt), [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions), and [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit). They can be integrated when compiling firmware or installed in existing systems for use. For specific usage methods, please refer to [kernel usage instructions](https://github.com/ophub/amlogic-s9xxx-armbian/blob/main/compile-kernel/README.md#instructions-for-using-the-kernel).

The [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy), [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable), and [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) are universal kernels that can be interchanged. Flippy's feature is being more user-friendly, Stable is more intimate, and Dev is smoother.

- The kernel files in [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) of Releases are the `stable version`, which are a series of kernels shared by `flippy`.
- The kernel files in [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) of Releases are the `stable version` with more support options enabled according to user needs.
- The kernel files in [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) of Releases are the `development version`, which adds third-party driver support and special modifications for some specific boxes.
- The kernel files in [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) of Releases are `dedicated versions` for the `rk3588` series, and it is not compatible with other series.
- The kernel files in [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) of Releases are the `beta versions`, Supports custom addition of third-party drivers and other patches, as well as custom configuration for compilation.
- In the [dev](https://github.com/ophub/kernel/releases/tag/dev) section of releases, there is a `cross-compilation toolchain` download image required for compiling the kernel.
- In the [tools](https://github.com/ophub/kernel/releases/tag/tools) section of releases, there are `Android system` download images for some common TV boxes, which can be used to restore the Android system when using Armbian and OpenWrt systems.

## Compiling the Kernel

- For detailed instructions on how to compile the kernel, please refer to [compile-kernel](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel). The method of using github.com's Actions to compile the kernel can be found in [.github/workflows](.github/workflows). You can customize the kernel by modifying the kernel configuration file in [kernel-config](kernel-config). You can add custom kernel patches in the [kernel-patch](kernel-patch) directory.

- You can adjust the kernel configuration as needed, such as adding drivers and patches. You can also compile a personalized signature kernel with special significance based on your mood, such as `5.10.95-happy-new-year`, `5.10.96-beijing-winter-olympics`, `5.10.99-valentines-day`, and so on.

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

We would like to express our sincere thanks to unifreq and others for maintaining the kernel source code. The current kernel files in the repository use the following source code:

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
