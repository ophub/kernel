# Kernel Description

View Chinese description  |  [查看中文说明](README.cn.md)

These kernels can be used for `Armbian` and `OpenWrt` systems, such as the [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian), [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt), [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions), and [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit) projects. They can be integrated when compiling firmware or installed in an existing system. Among them, [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable), [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) and [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) is an interchangeable mainline kernel. For specific usage methods, see the [Kernel Use Instructions](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel).

- The kernel files in the [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) section of the Releases are `stable version`, which have enabled more support options according to user needs.
- The kernel files in the [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) section of the Releases are `stable version`, which are series kernels shared by `flippy`.
- The kernel files in the [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) section of the Releases are `beta version`, which support custom addition of third-party driver patches, and allow custom configuration compilation.
- The kernel files in the [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) section of the Releases are `special version` for the `rk3588` series, and they are not compatible with other series.
- The kernel files in the [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) section of the Releases are `special version` for the `rk3528/rk3566/rk3568` series, and they are not compatible with other series.
- The kernel files in the [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) section of the Releases are `special version` for the `Allwinner H6 (TQC-A01)` device, and they are not compatible with other series.
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
    kernel_version: 6.1.y_6.12.y
    kernel_auto: true
    kernel_sign: -yourname
```

## Kernel Source Code

A big thank you to unifreq and others for maintaining the kernel source code. The source code used in the kernel files in the repository is as follows:

| Kernel Tags   | Source Code Repository  | Applicable devices      |
| ------------- | ----------------------- | ----------------------- |
| [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)<br>[kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy)<br>[kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) | [unifreq/linux-5.10.y](https://github.com/unifreq/linux-5.10.y)<br>[unifreq/linux-5.15.y](https://github.com/unifreq/linux-5.15.y)<br>[unifreq/linux-6.1.y](https://github.com/unifreq/linux-6.1.y)<br>[unifreq/linux-6.6.y](https://github.com/unifreq/linux-6.6.y)<br>[unifreq/linux-6.12.y](https://github.com/unifreq/linux-6.12.y) | Amlogic<br>Allwinner<br>Rockchip |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [unifreq/linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx)<br>[unifreq/linux-6.1.y-rockchip](https://github.com/unifreq/linux-6.1.y-rockchip) | Rockchip-RK3588 |
| [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [unifreq/linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx)<br>[unifreq/linux-6.1.y-rockchip](https://github.com/unifreq/linux-6.1.y-rockchip) | Rockchip-RK3528/RK3566/RK3568 |
| [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) | [13584452567/linux-6.4.y](https://github.com/13584452567/linux-6.4.y)<br>[13584452567/linux-6.5.y](https://github.com/13584452567/linux-6.5.y)<br>[13584452567/linux-6.6.y](https://github.com/13584452567/linux-6.6.y) | Allwinner-H6(TQC-A01) |
| [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)<br>[kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6)<br>[kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588)<br>[kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [ophub/linux-5.10.y](https://github.com/ophub/linux-5.10.y)<br>[ophub/linux-5.15.y](https://github.com/ophub/linux-5.15.y)<br>[ophub/linux-6.1.y](https://github.com/ophub/linux-6.1.y)<br>[ophub/linux-6.6.y](https://github.com/ophub/linux-6.6.y)<br>[ophub/linux-6.12.y](https://github.com/ophub/linux-6.12.y)<br>[ophub/linux-h6-6.6.y](https://github.com/ophub/linux-h6-6.6.y)<br>[ophub/linux-6.1.y-rockchip](https://github.com/ophub/linux-6.1.y-rockchip) | The kernel source code was cloned from the repositories <br>of [unifreq](https://github.com/unifreq), [13584452567](https://github.com/13584452567) and [chewitt](https://github.com/chewitt/linux), facilitating learning <br>how to patch the kernel by following these experts. |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [armbian/linux-rockchip](https://github.com/armbian/linux-rockchip) | Rockchip-Beta(6.1.y) |
| [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [armbian/linux-rockchip](https://github.com/armbian/linux-rockchip) | Rockchip-Beta(6.1.y) |

## Links

- [unifreq/kernel](https://github.com/unifreq)
- [13584452567/kernel](https://github.com/13584452567/linux-6.4.y)
- [chewitt/linux](https://github.com/chewitt/linux)
- [torvalds/linux](https://github.com/torvalds/linux)
- [kernel.org](https://kernel.org)

## License

The kernel © OPHUB is licensed under [GPL-2.0](https://github.com/ophub/kernel/blob/main/LICENSE)
