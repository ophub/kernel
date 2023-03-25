# 内核说明

查看英文说明 | [View English description](README.md)

这些内核可用于 `Armbian` 和 `OpenWrt` 系统。例如 [amlogic-s9xxx-armbian](https://github.com/ophub/amlogic-s9xxx-armbian), [amlogic-s9xxx-openwrt](https://github.com/ophub/amlogic-s9xxx-openwrt), [flippy-openwrt-actions](https://github.com/ophub/flippy-openwrt-actions) 和 [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit) 等项目。可以在编译固件时集成，也可以安装到已有的系统中使用。具体使用方法详见[内核使用说明](https://github.com/ophub/amlogic-s9xxx-armbian/blob/main/compile-kernel/README.cn.md#内核使用说明)。

- 在 Releases 的 [kernel_stable](https://github.com/ophub/kernel/releases/tag/kernel_stable) 里的内核文件是`稳定版`，适合在正式生产环境中使用。
- 在 Releases 的 [kernel_rk3588](https://github.com/ophub/kernel/releases/tag/kernel_rk3588) 里的内核文件是 `rk3588` 系列的`专用版本`，适合 Rock-5B 和 HinLink-H88K 等设备，和其他系列不通用。
- 在 Releases 的 [kernel_h6](https://github.com/ophub/kernel/releases/tag/kernel_h6) 里的内核文件是 `H6` 系列的`专用版本`，适合 TQC-A01 等设备，和其他系列不通用。
- 在 Releases 的 [kernel_dev](https://github.com/ophub/kernel/releases/tag/kernel_dev) 里的内核文件是`开发版`，为一些特定盒子添加了第三方的驱动支持和特殊修改，供开发和测试使用。
- 在 Releases 的 [dev](https://github.com/ophub/kernel/releases/tag/dev) 里有编译内核时需要的`交叉编译工具链`下载镜像。
- 在 Releases 的 [tools](https://github.com/ophub/kernel/releases/tag/tools) 里有一些常见的电视盒子的`安卓系统`下载镜像，在使用 Armbian 和 OpenWrt 系统时，可以用于恢复安卓系统使用。

## 编译内核

- 内核的编译方法详见 [compile-kernel](https://github.com/ophub/amlogic-s9xxx-armbian/tree/main/compile-kernel), 使用 github.com 的 Actions 进行内核编译的模板可参考 [.github/workflows](.github/workflows)，可以通过修改 [tool/config](tool/config) 里的内核配置文件进行自定义。

- 你可以根据需要对内核的配置进行调整，如添加驱动和补丁。也可以根据心情编译具有特殊意义的个性化签名内核，如 `5.10.95-happy-new-year`, `5.10.96-beijing-winter-olympics`, `5.10.99-valentines-day` 等等。


```yaml
- name: Compile the kernel
  uses: ophub/amlogic-s9xxx-armbian@main
  with:
    build_target: kernel
    kernel_version: 5.10.135_5.15.50
    kernel_auto: true
    kernel_sign: -yourname
```

## 内核源码

非常感谢 unifreq 和 13584452567 等大佬们维护的内核源码，目前仓库中的内核文件使用的源码如下：

| 内核分类       | 源码作者      | 源码仓库               |
| ------------- | ----------- | --------------------- |
| kernel_stable | [unifreq](https://github.com/unifreq) | [linux-5.4.y](https://github.com/unifreq/linux-5.4.y), [linux-5.10.y](https://github.com/unifreq/linux-5.10.y), [linux-5.15.y](https://github.com/unifreq/linux-5.15.y), [linux-6.1.y](https://github.com/unifreq/linux-6.1.y) |
| kernel_rk3588 | [unifreq](https://github.com/unifreq) | [linux-5.10.y-rk35xx](https://github.com/unifreq/linux-5.10.y-rk35xx) |
| kernel_h6     | [13584452567](https://github.com/13584452567) | [linux-6.1.y](https://github.com/13584452567/linux-6.1.y) |

## 链接

- [unifreq/kernel](https://github.com/unifreq)
- [13584452567/kernel](https://github.com/13584452567/linux-6.1.y)
- [chewitt/linux](https://github.com/chewitt/linux)
- [torvalds/linux](https://github.com/torvalds/linux)
- [kernel.org](https://kernel.org)

## License

The kernel © OPHUB is licensed under [GPL-2.0](https://github.com/ophub/kernel/blob/main/LICENSE)
