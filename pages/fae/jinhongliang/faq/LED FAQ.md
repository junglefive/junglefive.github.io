---
title: 18MB8X系列 LED FAQ
keywords: documentation theme, jekyll, technical writers, help authoring tools, hat replacements
last_updated: Sep 20, 2017
tags: [FAQ]
summary: "客户在应用我司LED DRIVER的时候经常遇见的一些问题，为帮助客户能更容易使用我们的产品，将一些常见问题进行总结和解答"
sidebar: mydoc_sidebar
permalink: led_faq.html
folder: mydoc
---


## 18MB8X系列 LED FAQ

#### 1. 常见问题

- 问题1. 为什么打不开charge pump？
- 问题2. 打开charge pump且LED点亮时，为什么Low power电压升高了？
- 问题3. 怎么调整LED整体电流？
- 问题4. 为什么打开了charge pump之后还是很暗？

#### 2. 问题与解答

- 问题1. 为什么打不开charge pump？
- 解答：在配置好LED之后，请检查是否将CHPCON[CHPEN]、LEDCON1[LED_PMODE]打开,CHPCON[CHPVS]置0。
- 问题2. 打开charge pump且LED点亮时，为什么Low power电压升高了？
- 解答：原因是LED点亮时将电源电压拉低了。这时候就应该提高LDO的驱动能力才能确保电源电压保持稳定。
- 问题3. 怎么调整LED整体电流？
- 解答：可修改l_led_drv.asm文件中函数INTERRUPT_LED_END以及INTERRUPT_LED_END1中驱动电流以及定时器溢出时间。
- 问题4. 为什么打开了charge pump之后跟不打开亮度一样？
- 解答：这有多种可能性，以下为可能性总结及建议：
- LED已达到最大亮度。建议更换LED。
- CAP0/CAP1外接电容耐压值不够。建议使用封装0805以上、耐压值10V以上电容。
- CHPV/VLED引脚外接电容容值不足或耐压值不够。建议使用封装0805以上、耐压值10V以上电容。
- LDO驱动电压不够。建议更换驱动电流大的LDO。



{% include links.html %}