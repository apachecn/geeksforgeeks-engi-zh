# 物联网中关于 Arduino Uno 或 Mega 需要记住的点

> 原文:[https://www . geeksforgeeks . org/关于 arduino-uno-or-mega-in-iot/](https://www.geeksforgeeks.org/points-to-remember-about-arduino-uno-or-mega-in-iot/) 的记忆点

**先决条件–**
**1。** [**微控制器和微处理器**](https://www.geeksforgeeks.org/whats-difference-between-microcontoller-%C2%B5c-and-microprocessor-%C2%B5p/)
**2。**[**Arduino 基础知识**](https://www.geeksforgeeks.org/what-is-arduino/)
在[物联网(IoT)](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/) 时代，我们每天都在使用任何 IoT 设备，或者偶然遇到任何支持 IoT 的设备。我们可能从朋友那里听说物联网使用微控制器和微处理器。是的，没错。不同类型的微控制器用于不同的目的。在本文中，我们将讨论 Arduino Uno 和 Mega 微控制器。这篇文章将有助于澄清关于 Uno 和 Mega 的混淆，以及它们的规范是什么。以便将来我们去使用它的时候，我们可以很容易地区分在什么条件下使用哪一个。

**1。Arduino Uno :**
Arduino Uno 是 Arduino.cc 开发的开源微控制器板，基于 Microchip ATmega328P 微控制器。它是最受欢迎的 Arduino 开发板之一，被普遍称为“股票 Arduino”。这是一块 2.7 英寸* 2.1 英寸的小型开发板。它是硬件和软件高度兼容的。该板配有多组数字和模拟输入/输出(I/O)引脚，但引脚数量少于 Arduino mega，但 Uno 适用于小型开发项目和原型制作。它的低成本和特点使它成为工程师和学生进行项目开发的好选择。

**关于 Uno 需要注意的点:**

1.  它有 *ATMega328* 微控制器。
2.  它的尺寸比兆小，因为优诺的尺寸是 2.7 英寸* 2.1 英寸。
3.  在空间受限的应用中，这是一个不错的选择，因为它的尺寸较小。
4.  从价格角度来看，它比 Mega 便宜，价格在 400 到 700 卢比左右。
5.  它提供 32 kB 的闪存。
6.  Arduino Uno 的 EEPROM 为 1 kB。
7.  Arduino Uno 的 SRAM 是 2 kB。
8.  当工程师在任何项目中需要更少的 GPIO 引脚时，他们会这样做。
9.  Arduino Uno 是高度软件兼容的。
10.  Uno 中有 14 个数字 I/O 引脚。
11.  Uno 中有 6 个带脉宽调制引脚的数字输入/输出。
12.  Uno 中有 6 个模拟引脚。
13.  Arduino Uno 只有一个 UART 接口。

**2。Arduino Mega:**
Arduino Mega 2560 是 Arduino 的一款微控制器板，基于 ATMega2560。它也是需要更多输入/输出线、更多草图内存和更多内存的项目的流行板。因为它提供了更多的输入/输出引脚，比联合国办事处更多的内存，所以在更高的要求，阿尔杜伊诺兆是首选。它提供了像 Uno 这样的所有功能。

**关于 Mega 需要注意的点:**

1.  它有 ATMega2560 微控制器。
2.  它的尺寸比 Uno 大，因为 Mega 的尺寸是 4 英寸* 2.1 英寸。
3.  在空间受限的应用中，它不是很好，因为它的尺寸稍大。
4.  从价格上看，它比 Uno 高，价格在 700 到 1000 卢比左右。
5.  提供 256 kB 的闪存。
6.  Arduino Mega 的 EEPROM 为 4 kB。
7.  Arduino Mega 的 SRAM 为 8 kB。
8.  当工程师在任何项目中需要更高的 GPIO 引脚时，他们都会这样做。
9.  Arduino Mega 不是高度软件兼容的。
10.  兆有 54 个数字输入/输出引脚。
11.  兆有 15 个带脉宽调制引脚的数字输入/输出。
12.  Uno 中有 16 个模拟引脚。
13.  Arduino Mega 有四个 UART 接口。