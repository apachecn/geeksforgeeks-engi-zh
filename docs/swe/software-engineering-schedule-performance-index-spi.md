# 软件工程|进度性能指数(SPI)

> 原文:[https://www . geesforgeks . org/software-engineering-schedule-performance-index-SPI/](https://www.geeksforgeeks.org/software-engineering-schedule-performance-index-spi/)

进度绩效指数(SPI)描述了与计划的项目进度相比，我们实际进展的效率。进度绩效指数(SPI)可以定义为进度效率的度量，表示为挣值与计划值的比率。

进度绩效指数提供了有关项目进度绩效的信息。这是项目所用时间的效率。

**进度绩效指数(CPI)的计算:**
进度绩效指数可以通过挣值除以计划值来计算。

```
SPI = EV / PV 
```

哪里，

```
Earned Value (EV): Earned Value is the amount 
                        of the task that is actually completed.  

Planned Value (PV) = Planned Completion * Task Budget 
```

**SPI 解释:**

1.  **SPI > 1** :
    如果 SPI 大于 1，那么已经完成的工作比计划的工作多。换句话说，我们可以说项目提前了。
2.  **SPI < 1** :
    如果 SPI 小于 1，则完成的工作少于计划的工作。换句话说，我们可以说项目进度落后了。
3.  **SPI = 1** :
    如果 SPI 等于 1，则工作正在以与计划大致相同的速度完成。换句话说，我们可以说项目是准时的。

**例:**
给定一个 12 个月完成的项目，项目预算为 100，000 印度卢比。六个月过去了，已经花费了 60，000 印度卢比，但仔细审查后发现，到目前为止，只有 40%的工作已经完成。
找到进度绩效指标，得出项目是落后还是超前。

**解决方案:**

实际成本= 60，000 印度卢比

计划值= 1，00000 印度卢比的 50% = 50000 印度卢比

挣值= 1，00，000 印度卢比的 40% = 40，000 印度卢比

SPI =挣值/计划值= 40，000 / 50，000 = 0.8

因此，计划绩效指数为 0.8。

结论是项目落后于计划，因为计划绩效指数小于 1。