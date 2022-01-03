# 使用测试在硒网络驱动程序中断言

> 原文:[https://www . geesforgeks . org/assertion-in-selenium-web driver-using-TestNG/](https://www.geeksforgeeks.org/assertion-in-selenium-webdriver-using-testng/)

先决条件–[硒](https://www.geeksforgeeks.org/software-engineering-selenium-an-automation-tool/)
实际结果与预期结果在断言的帮助下进行比较。这意味着验证是为了检查应用程序的状态是否与我们期望的相同。为了创建断言，我们将使用 TestNG 提供的 Assert 类。

断言有两种类型:-

1.  强硬的断言。
2.  温和的断言。

这些解释如下。

**1。硬断言:**
当任何断言语句失败时，这种类型的断言会立即抛出异常，并继续测试套件中的下一个测试。

硬断言可以是以下类型:-

**1。asserteqals–**
这用于比较 selenium webdriver 中的预期值和实际值。只要预期值和实际值相同，断言就会毫无例外地通过。但是，如果实际值和预期值不一样，那么 assert 就会异常失败，测试就会被标记为失败。

*语法:*

```
Assert.assertEquals(actual, expected); 
```

**2。
资产质量–这与资产质量正好相反。每当预期值和实际值不同时，断言都会毫无例外地通过。但是，如果实际值和预期值相同，那么 assert 会异常失败，测试会被标记为失败。**

*语法:*

```
Assert.assertNotEquals(actual, expected, message); 
```

**3。assertTrue–**
这种类型的断言用于检查条件是否为真。也就是说，当我们处理布尔值时，使用这个断言。只要测试用例通过，它就返回真，如果条件为假，它就跳过当前的方法，跳到下一个。

*语法:*

```
Assert.assertTrue(condition); 
```

**4。assertFalse–**
它检查返回值是否为 False。只要测试用例通过，它就会中止方法并给出一个异常。

*语法:*

```
Assert.assertFalse(condition); 
```

**5。**
该断言检查对象是否为空。如果对象为空，它将中止测试并给出一个异常。

*语法:*

```
Assert.assertNull(object);
```

**6。**
该断言检查对象是否为空。如果对象不为空，即如果对象有任何值，它将中止测试，并给出一个异常。

*语法:*

```
Assert.assertNotNull(object); 
```

**2。软断言:**
这些类型的断言是当断言失败时不抛出异常，并在断言语句后继续下一步的断言类型。