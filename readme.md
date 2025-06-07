# STM32F103的UF2引导程序开发

[原版README](./README_en.md)

本项目最初是从[DAPBoot](https://github.com/devanlai/dapboot)分支而来，但移除了DFU功能，并替换为[支持UF2](https://github.com/Microsoft/uf2)的USB大容量存储设备。

安装此引导程序的开发板可以通过[MakeCode](https://maker.makecode.com)的网页界面进行编程，支持图形化编程语言或TypeScript。

## 通过二进制文件烧录引导程序

你需要一个 STLink/v2（或其他调试器）来烧录引导程序。

- 访问[uf2-stm32f103](https://github.com/mmoskal/uf2-stm32f103/releases)
- 下载最新的 ZIP 文件（`uf2-stm32f103-vX.Y.Z.zip`）
- 运行：`openocd -f interface/stlink-v2.cfg -f target/stm32f1x.cfg -c "program uf2boot-BLUEPILL.bin verify reset exit 0x8000000"`
- 查看是否出现`BLUEPILL`盘符；如果没有，请复位开发板；LED 应会以大约每秒一次的频率渐亮渐灭。

## 构建说明

默认目标是为通用 STM32F103 开发板（LED 连接在 PC13 上，通常称为“bluepill”的开发板）构建的。

要为其他目标构建，可以在调用 `make` 时覆盖 `TARGET` 变量。

```shell
make clean
make TARGET=LJTURING_STM32F103X8_8M
```

### 项目

| 项目名称 | 描述 | 链接 |
| :-: | :-: | :-: |
| `BLUEPILL` | 性价比开发板 | http://wiki.stm32duino.com/index.php?title=Blue_Pill |
| `MAPLEMINI` | LeafLabs Maple Mini板 | http://wiki.stm32duino.com/index.php?title=Maple_Mini |
| `STLINK` | STLink/v2复刻版 | https://wiki.paparazziuav.org/wiki/STLink#Clones |
| `PXT32` | MakeCode游戏机版 | https://arcade.makecode.com |

