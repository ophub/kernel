# Kernel Description

View Chinese description  |  [查看中文说明](README.cn.md)

This kernel can be used in `Armbian` and `OpenWrt` systems. For example [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian), [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt), [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions) and [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit). It can be integrated when compiling firmware, or it can be installed into an existing system for use. For specific usage, please refer to [Kernel usage Instructions](https://github.com/ophub/amlogic-s9xxx-armbian/blob/main/compile-kernel/README.md#kernel-usage-instructions).

- The kernel files in [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) in Releases are `stable version`, suitable for use in a formal production environment.
- The kernel files in [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) in Releases are `special versions` of the `rk3588` series, which is suitable for devices such as Rock-5B and HinLink-H88K, and is not common to other series.
- The kernel files in [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) in Releases are `special version` of the `H6` series, which is suitable for devices such as TQC-A01, and is not common to other series.
- The kernel files in [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) in Releases are `development version`, and third-party driver support and special modifications have been added for some specific devices, for development and testing use.
- In the [dev](https://github.com/ophub/kernel/releases/tag/dev) of Releases, there are download image of the `cross-compilation toolchain` required for compiling the kernel.
- In the [tools](https://github.com/ophub/kernel/releases/tag/tools) of Releases, there are some `Android system` download images of common TV boxes. When using Armbian and OpenWrt systems, you can use It is used to restore the Android system.

## Compile the kernel

- For the compilation method of the kernel, see [compile-kernel](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel), The template for kernel compilation using github.com's Actions can be found in [.github/workflows](.github/workflows), It can be customized by modifying the kernel config-x.y file in [tool/config](tool/config).

- You can adjust the configuration of the kernel as needed, such as adding drivers and patches. It is also possible to compile personalized signature kernels with special meanings according to mood, such as `5.10.95-happy-new-year`, `5.10.96-beijing-winter-olympics`, `5.10.99-valentines-day` and so on.

```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.10.135_5.15.50
    kernel_auto: true
    kernel_sign: -yourname
```

## kernel source code

Thank you very much for the kernel source code maintained by unifreq and 13584452567. The source code used by the kernel files in the repository is as follows:

| Kernel Tag    | Source Author  | Source Code Repository  |
| ------------- | -------------- | ----------------------- |
| [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) | [unifreq](https://github.com/unifreq) | [linux-5.4.y](https://github.com/unifreq/linux-5.4.y), [linux-5.10.y](https://github.com/unifreq/linux-5.10.y), [linux-5.15.y](https://github.com/unifreq/linux-5.15.y), [linux-6.1.y](https://github.com/unifreq/linux-6.1.y) |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [unifreq](https://github.com/unifreq) | [linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx) |
| [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6)     | [13584452567](https://github.com/13584452567) | [linux-6.1.y](https://github.com/13584452567/linux-6.1.y) |

## Links

- [unifreq/kernel](https://github.com/unifreq)
- [13584452567/kernel](https://github.com/13584452567/linux-6.1.y)
- [chewitt/linux](https://github.com/chewitt/linux)
- [torvalds/linux](https://github.com/torvalds/linux)
- [kernel.org](https://kernel.org)

## License

The kernel © OPHUB is licensed under [GPL-2.0](https://github.com/ophub/kernel/blob/main/LICENSE)
