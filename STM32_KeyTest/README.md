# STM32_KeyTest

## 项目简介

这是一个检测按键长短按的程序，实现的硬件平台是以STM32F103C8T6为核心的STM32 Display Board V1.0开发板。

工程使用的软件平台是KEIL-MDK5，建议使用5以上的版本打开工程编译。代码使用C语言编写，使用ST官方提供的库函数实现

硬件平台开源地址：[STM32 Display Board V1.0](https://github.com/LGG001/LCEDA_Hardware)  

源码分析文章地址：[MCU程序设计-按键长短按检测](https://lgg001.github.io/2018/10/30/MCU%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1-%E6%8C%89%E9%94%AE%E9%95%BF%E7%9F%AD%E6%8C%89%E6%A3%80%E6%B5%8B/#more)

## 实现效果

短按KEY1、KEY3，然后长按KEY2、KEY4：

![](http://phd9o0dsm.bkt.clouddn.com/test8.gif)
