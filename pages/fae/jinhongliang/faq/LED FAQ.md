---
title: 18MB8X系列 LED FAQ
keywords: documentation theme, jekyll, technical writers, help authoring tools, hat replacements
last_updated: July 3, 2016
tags: [getting_started]
summary: "客户在应用我司LED DRIVER的时候经常遇见的一些问题，为帮助客户能更容易使用我们的产品，将一些常见问题进行总结和解答"
sidebar: mydoc_sidebar
permalink: led_faq.html
folder: mydoc
---


## `18MB8X`系列 `LED` `FAQ`

#### 1. 常见问题

- 问题1. _为什么打不开`charge pump`？_
- 问题2. _打开`charge pump`且LED点亮时，为什么`Low power`电压升高了？_
- 问题3. _怎么调整`LED`整体电流？_
- 问题4. _为什么打开了`charge pump`之后还是很暗？_


#### 2. 问题与解答

* 问题1. _为什么打不开`charge pump`？_

    - 答：在配置好LED之后，请检查是否将`CHPCON[CHPEN]`、`LEDCON1[LED_PMODE]`打开, `CHPCON[CHPVS]`置0。

* 问题2. _打开`charge pump`且`LED`点亮时，为什么`Low power`电压升高了？_

    - 答：原因是`LED`点亮时将电源电压拉低了。这时候就应该提高`LDO`的驱动能力才能确保电源电压保持稳定。

* 问题3. _怎么调整`LED`整体电流？_

    - 答：可修改`l_led_drv.asm`文件中函数```INTERRUPT_LED_END```以及```INTERRUPT_LED_END1```中驱动电流以及定时器溢出时间。

* 问题4. _为什么打开了`charge pump`之后跟不打开亮度一样_

    - 答：这有多种可能性，以下为可能性总结及建议：

#### 3. 其他


- `LED`已达到最大亮度。建议更换`LED`。
- `CAP0/CAP1`外接电容耐压值不够。建议使用封装`0805`以上、耐压值`10V`以上电容。
- `CHPV/VLED`引脚外接电容容值不足或耐压值不够。建议使用封装`0805`以上、耐压值`10V`以上电容。
- `LDO`驱动电压不够。建议更换驱动电流大的`LDO`。



{% include links.html %}