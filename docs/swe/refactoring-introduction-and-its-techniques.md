# 重构–介绍及其技巧

> 原文:[https://www . geeksforgeeks . org/重构-介绍-及其技术/](https://www.geeksforgeeks.org/refactoring-introduction-and-its-techniques/)

**重构**或**代码重构**被定义为在不增加新功能或改变代码外部行为的情况下，改进现有计算机代码的系统化过程。它旨在改变代码的实现、定义和结构，而不改变软件的功能。它提高了软件的可扩展性、可维护性和可读性，而不改变软件的实际功能。

**为什么我们要在代码运行良好的时候重构代码？**
重构的目标不是添加新的功能或删除现有的功能。重构的主要目标是使代码在将来更容易维护，并与技术债务作斗争。我们之所以进行重构，是因为我们知道在第一时间获得正确的设计是很难的，而且重构还会给你带来以下好处:

*   代码大小通常会减少
*   混乱的代码被重组为更简单的代码

以上两个好处都大大提高了可维护性，这是必需的，因为需求总是在不断变化。

**我们什么时候重构？**

*   在添加新功能之前，确保您的设计和当前代码是“好的”，这将有助于新代码更容易编写。
*   当你需要修复一个错误时
*   当你做同行评审时
*   在代码审查期间

**如何识别代码进行重构？**
马丁·福勒建议使用“代码气味”来识别何时何地重构。代码气味是在代码中做的坏事，就像代码中的坏模式一样。重构和代码气味是帮助我们识别设计和实现中的问题的一些技术。它还帮助我们将已知的解决方案应用到这些问题中。

**重构技术:**
现有 70 多种重构技术。但我们将只讨论几个更常见的。

1.  **Extract Method –**
    When we have a code that can be grouped together.

    **示例:**

    ```
    def student():
        getgrades()
        # details
        name = input()
        class = input() 
    ```

    这可以重构为:

    ```
    def student():
        getgrades()
        getdetails()

    def getdetails():
        name = input()
        class = input() 
    ```

2.  **Replace Temp with Query –**
    When we are using a temporary variable to hold the result of an expression.

    **示例:**

    ```
    SI = P * R * T / 100
    if(SI > 100):
        return SI
    else:
        return SI * 1.5 
    ```

    这可以重构为:

    ```
    def SI():
    return P * R * T / 100

    if(SI() > 100):
        return SI()
    else:
        return SI()*1.5 
    ```

3.  **Encapsulate Field –**
    It involves providing methods that is used to read/write data rather than accessing it directly.

    **示例:**

    ```
    class A:
        variable 
    This could be refactored as:

    ```
    class A:
         self.variable
         getvariable()
         setvariable() 
    ```

    ```

4.  **Inline Method -**
    When we have a method body which is more obvious than the method itself.

    **示例:**

    ```
    class PizzaDelivery:
        def getgrades(self):
            return 'A' if self.moretheneight() else B
        def ismorethaneight(self):
            return self.number > 8 
    ```

    这可以重构为:

    ```
    class PizzaDelivery:
        def getgrades(self):
            return self.number > 8 ? A : B 
    ```

5.  **Move Method -**
    When a function a class is used by other class more than the class in which it exists.

    ```
    Class A:
        #...
        abc()

    Class B:
        #... 
    ```

    这可以重构为:

    ```
    Class A:
        #...

    Class B:
        #...
        abc()
    ```

6.  **Replace Conditional with Polymorphism -**
    When we have a conditional that performs various actions depending on object type or properties.

    **示例:**

    ```
    =class Bird:
        # ...
        def getSpeed(self):
            if self.type == EUROPEAN:
                return self.getBaseSpeed()
            elif self.type == AFRICAN:
                return self.getBaseSpeed() - self.getLoadFactor() * self.numberOfCoconuts
            elif self.type == NORWEGIAN_BLUE:
                return 0 if self.isNailed else self.getBaseSpeed(self.voltage)
            else:
                raise Exception("Should be unreachable") 
    ```

    这可以重构为

    ```
    class Bird:
        # ...
        def getSpeed(self):
            pass

    class European(Bird):
        def getSpeed(self):
            return self.getBaseSpeed()

    class African(Bird):
        def getSpeed(self):
            return self.getBaseSpeed() - self.getLoadFactor() * self.numberOfCoconuts

    class NorwegianBlue(Bird):
        def getSpeed(self):
            return 0 if self.isNailed else self.getBaseSpeed(self.voltage)

    # Somewhere in client code
    speed = bird.getSpeed() 
    ```

**注:**

*   重构改进了软件的设计。
*   重构使软件更容易理解。
*   重构帮助我们发现程序中的错误。
*   重构帮助我们更快地编程。