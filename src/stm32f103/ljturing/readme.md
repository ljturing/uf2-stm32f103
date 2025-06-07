# [UF2-STM32F103](https://github.com/mmoskal/uf2-stm32f103)开发指导文档

针对STM32F103使用`.uf2`固件的定制Bootloader开发

## 依赖

```shell
# 安装编译依赖
sudo apt install -y make python3 gcc-arm-none-eabi
```

## 编译

```shell
cd src/
# 分别编译各项目
make TARGET=LJTURING_APM32F103X8_16M
make TARGET=LJTURING_APM32F103XB_16M
make TARGET=LJTURING_STM32F103X8_8M
make TARGET=LJTURING_STM32F103X8_16M
make TARGET=LJTURING_STM32F103XB_8M
make TARGET=LJTURING_STM32F103XB_16M
make clean
```
