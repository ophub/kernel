# 内核说明

查看英文说明 | [View English description](README.md)

这些内核适用于 `Armbian`、`OpenWrt` 和 `FnNAS` 系统，例如 [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian)、[amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt)、[fnnas](https://github.com/ophub/fnnas)、[flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions) 和 [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit) 等项目。内核既可以在编译固件时集成，也可以安装到现有系统中使用。其中 [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)、[kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) 和 [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) 是可互换使用的主线内核。具体使用方法详见[内核使用说明](https://github.com/ophub/amlogic-s9xxx-armbian/blob/main/compile-kernel/README.cn.md#内核使用说明)。


- Releases 中的 [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) 为`稳定版`内核，根据用户需求启用了更多支持选项。
- Releases 中的 [kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy) 为`稳定版`内核，由 `flippy` 制作并分享的系列内核。
- Releases 中的 [kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) 为`测试版`内核，支持自定义添加第三方驱动补丁，并支持自定义配置编译。
- Releases 中的 [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) 为 `rk3588` 系列的`专用版本`，与其他系列不通用。
- Releases 中的 [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) 为 `rk3528/rk3566/rk3568` 系列的`专用版本`，与其他系列不通用。
- Releases 中的 [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) 为 `全志 H6（TQC-A01）` 设备的`专用版本`，与其他系列不通用。
- Releases 中的 [dev](https://github.com/ophub/kernel/releases/tag/dev) 提供了编译内核所需的`交叉编译工具链`下载镜像。
- Releases 中的 [tools](https://github.com/ophub/kernel/releases/tag/tools) 提供了部分常见电视盒子的`安卓系统`下载镜像，在使用 Armbian 或 OpenWrt 系统时可用于恢复安卓系统。

## 编译内核

- 内核编译方法详见 [compile-kernel](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel)。使用 GitHub Actions 编译内核的方法可参考 [.github/workflows](.github/workflows)。可通过修改 [kernel-config](kernel-config) 中的内核配置文件自定义内核，也可在 [kernel-patch](kernel-patch) 目录下添加自定义内核补丁。

- 你可以根据需要调整内核配置，例如添加驱动和补丁。也可以编译具有特殊意义的个性化签名内核，例如 `5.10.95-happy-new-year`、`5.10.96-beijing-winter-olympics`、`5.10.99-valentines-day` 等。


```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 6.1.y_6.12.y
    kernel_auto: true
    kernel_sign: -yourname
```

## 内核源码

特别感谢 unifreq 等贡献者维护的内核源码。目前本仓库中的内核文件所使用的源码如下：

| 内核标签        | 源码仓库               | 适用设备               |
| ------------- | --------------------- | --------------------- |
| [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)<br>[kernel_flippy](https://github.com/ophub/kernel/releases/tag/kernel_flippy)<br>[kernel_beta](https://github.com/ophub/kernel/releases/tag/kernel_beta) | [unifreq/linux-5.10.y](https://github.com/unifreq/linux-5.10.y)<br>[unifreq/linux-5.15.y](https://github.com/unifreq/linux-5.15.y)<br>[unifreq/linux-6.1.y](https://github.com/unifreq/linux-6.1.y)<br>[unifreq/linux-6.6.y](https://github.com/unifreq/linux-6.6.y)<br>[unifreq/linux-6.12.y](https://github.com/unifreq/linux-6.12.y)<br>[unifreq/linux-6.18.y](https://github.com/unifreq/linux-6.18.y) | Amlogic<br>Allwinner<br>Rockchip |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [unifreq/linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx)<br>[unifreq/linux-6.1.y-rockchip](https://github.com/unifreq/linux-6.1.y-rockchip) | Rockchip-RK3588 |
| [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [unifreq/linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx)<br>[unifreq/linux-6.1.y-rockchip](https://github.com/unifreq/linux-6.1.y-rockchip) | Rockchip-RK3528/RK3566/RK3568 |
| [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) | [13584452567/linux-6.4.y](https://github.com/13584452567/linux-6.4.y)<br>[13584452567/linux-6.5.y](https://github.com/13584452567/linux-6.5.y)<br>[13584452567/linux-6.6.y](https://github.com/13584452567/linux-6.6.y) | Allwinner-H6(TQC-A01) |
| [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable)<br>[kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6)<br>[kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588)<br>[kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [ophub/linux-5.10.y](https://github.com/ophub/linux-5.10.y)<br>[ophub/linux-5.15.y](https://github.com/ophub/linux-5.15.y)<br>[ophub/linux-6.1.y](https://github.com/ophub/linux-6.1.y)<br>[ophub/linux-6.6.y](https://github.com/ophub/linux-6.6.y)<br>[ophub/linux-6.12.y](https://github.com/ophub/linux-6.12.y)<br>[ophub/linux-6.18.y](https://github.com/ophub/linux-6.18.y)<br>[ophub/linux-h6-6.6.y](https://github.com/ophub/linux-h6-6.6.y)<br>[ophub/linux-5.10.y-rk35xx](https://github.com/ophub/linux-5.10.y-rk35xx)<br>[ophub/linux-6.1.y-rockchip](https://github.com/ophub/linux-6.1.y-rockchip) | 内核源码复制自 [unifreq](https://github.com/unifreq)、[13584452567](https://github.com/13584452567) 和 [chewitt](https://github.com/chewitt/linux) 的仓库，<br>便于学习和参考内核补丁的制作方法。 |
| [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) | [armbian/linux-rockchip](https://github.com/armbian/linux-rockchip) | Rockchip-Beta(6.1.y) |
| [kernel_rk35xx](https://github.com/ophub/kernel/releases/tag/kernel_rk35xx) | [armbian/linux-rockchip](https://github.com/armbian/linux-rockchip) | Rockchip-Beta(6.1.y) |


## 链接

- [unifreq/kernel](https://github.com/unifreq)
- [13584452567/kernel](https://github.com/13584452567/linux-6.4.y)
- [chewitt/linux](https://github.com/chewitt/linux)
- [torvalds/linux](https://github.com/torvalds/linux)
- [kernel.org](https://kernel.org)
- [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian)
- [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt)
- [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions)
- [fnnas](https://github.com/ophub/fnnas)

## License

The kernel © OPHUB is licensed under [GPL-2.0](https://github.com/ophub/kernel/blob/main/LICENSE)
