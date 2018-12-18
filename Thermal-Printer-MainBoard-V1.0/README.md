# Thermal-Printer-MainBoard-V1.0

## 项目简介

Thermal-Printer-MainBoard-V1.0项目由基于硬件Thermal-Printer-MainBoard-V1.0下的各种例程组成


硬件平台开源地址：[Thermal-Printer-MainBoard-V1.0](https://github.com/LGG001/LCEDA_Hardware)  


## Thermal-Printer-MainBoard-V1.0硬件介绍  

Thermal Printer MainBoard V1.0是一块以STM32F103RCT6为核心的开发板，原本的设计目的是作为一块热敏打印机控制板学习使用  
![](http://phd9ide4y.bkt.clouddn.com/Snipaste_2018-11-21_23-24-55_gaitubao_com_423x263_gaitubao_com_381x237.png)


Thermal Printer MainBoard V1.0的资源非常丰富  
* 带有1.3寸的IPS（240*240）高清显示屏  
* 4个KEY按键+1个复位按键、2个用户LED、2个电源指示灯  
* 板上设计有热敏打印头接口以及相关电路，可直接驱动  
* 工作使用12V/2A DC适配器输入，如果不使用打印机可使用MINI_USB供电
* 带有外部FLASH，容量8MByte
* 下载接口采用SWD接口，引出两路UART引脚

## 例程列表及功能

### 00_LED_Blink

功能：使用位带和位与（^）操作进行IO口取反实现LED1&LED闪烁  

### 01_KEY_Detection

功能：实现按键的长短按检测  
效果：
```
LEFT按键短按-LED1亮  		RIGHT按键短按-LED1亮  
ENTER按键短按-LED1灭		EXIT按键短按-LED1灭
LEFT按键长按-LED2亮  		RIGHT按键长按-LED2亮  
ENTER按键长按-LED2灭		EXIT按键长按-LED2灭
```

### 02_USART_Printf

功能：实现串口printf打印  
效果：
```
LED1&LED2闪烁，串口打印：USART_Test! 
串口配置：1停止位、8数据位、波特率115200、无奇偶校验
```

### 03_uGUI_Display

功能：移植uGUI来控制IPS显示屏显示
效果：  
```
显示屏显示，	LEFT按键短按-LED1亮		RIGHT按键短按-LED2亮
		  	ENTER按键短按-LED1灭		EXIT按键短按-LED2灭
```

### 04_SPI_Flash

功能：对板子上的FLASH(W25Q64)进行读写操作  
效果：  
```
上电读取FLASH的ID：  
-成功打印-W25Q64 Init Succeed !!  
-失败打印-W25Q64 Init Faile !!  
按下LEFT键：  
-LED1亮，LED2灭，对FLASH写入"ADCDEF"后打印：Weite Succeed !!  
按下RIGHT键：  
-LED2亮，LED1灭，对FLASH读取写入的"ABCDEF"并打印  
```

### 05_WWDG_Reset  

功能：实现窗口看门狗，用于监视MCU正常运行 
效果：  
```
WWDG配置：窗口值0x7f,最大喂狗时间约为57ms
按下LEFT键：  
-延迟200ms，导致WWDG复位，系统重新运行，检测WWDG复位标志，LED2亮，串口打印"WWDG RESET!!!"  
按下RIGHT键： 
-LED2灭 
```



