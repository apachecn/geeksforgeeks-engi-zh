# 软件开发中的可靠性属性

> 原文:[https://www . geesforgeks . org/reliability-attributes-in-software-development/](https://www.geeksforgeeks.org/reliability-attributes-in-software-development/)

**可靠性属性**是软件可靠性的度量。不同的软件有许多可靠性要求，但是所有的软件都有一些通用的可靠性度量。不同类别软件产品的可靠性属性可能不同。因此，有必要在软件需求规格文件中规定软件产品所需的可靠性水平。
有一些属性是显著表达软件产品可靠性所必需的。一个好的可靠性度量应该依赖于观察者，这样不同的人就可以对一个系统的可靠性程度达成一致。

例如，有各种各样的技术用于测量性能，这些技术可能导致获得相同的性能值，而不管是谁在执行性能测量。但是实际上很难制定精确的可靠性测量技术。下一个基本情况是要有与可靠性相关的措施。

有六个可靠性属性可以用来表示软件产品的可靠性。

**故障发生率(ROCOF) :**
ROCOF 衡量软件出现意外行为的频率。它基本上衡量软件产品失败的次数。软件产品的 ROCOF 度量可以通过记录软件产品的行为来获得。ROCOF 基本上是在指定时间间隔内发生的故障总数。

**平均故障时间(MTTF) :**
两次连续故障之间的平均时间称为 MTTF。它是通过观察软件产品中的大量故障而获得的。为了测量 MTTF，记录 n 次故障的故障数据。
如果故障发生在时刻 T1、T2、…、Tn，则 MTTF 可计算为:

```
MTTF = ( (T2 - T1) + (T3 - T2) + ... + (Tn+1 - Tn) ) / (n-1) 
```

值得注意的是，在时间测量中只考虑运行时间。系统关闭以修复错误的时间、引导时间和任何其他可忽略的时间都被忽略，并且不包括在时间测量中。

**平均修复时间(MTTR) :**
当软件出现故障时，需要一段时间来修复错误。MTTR 是系统发现导致故障的错误并修复它们所花费的平均时间的量度。

**平均故障间隔时间(MTBR) :**
MTBR 属性可以结合 MTTF 和 MTTR 属性得到。

```
MTBF = MTTF + MTTR 
```

因此，MTBF 表示一旦发生故障，在同一时间后预计会发生下一次故障。在这种情况下，时间测量是实时的，而不是像 MTTF 那样的执行时间。

**按需故障概率:**
该属性不像其他属性那样涉及时间测量。POFOD 测量当发出服务请求时系统失败的行为。

例如，如果 POFOD 测量值为 0.001，则意味着每 1000 个服务请求中就有一个会导致失败。

**可用性:**
系统的可用性是系统在给定时间段内使用的可能性的度量。它考虑在一个时间间隔内发生的故障数量。当故障发生时，它还会测量系统的停机时间。这个属性对于那些应该永不停机的系统来说很重要。这在电信系统和操作系统中起着至关重要的作用。即使在维修期间，这些系统也需要运行。