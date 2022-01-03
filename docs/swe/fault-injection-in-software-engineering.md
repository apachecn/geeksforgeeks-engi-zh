# 软件工程中的故障注入

> 原文:[https://www . geesforgeks . org/fault-injection-in-software-engineering/](https://www.geeksforgeeks.org/fault-injection-in-software-engineering/)

**故障注入**是一种通过在软件中包含有意的故障来提高测试质量的技术。故障注入经常出现在压力测试中，它被认为是开发健壮软件的一个重要部分。

故障传播到明显的故障遵循一个明确的周期。在执行过程中，故障可能导致系统边界内的无效状态错误。相同的错误会在系统边界内导致更多的错误，因此每个新的错误都是一个错误，并且它可能会传播到系统边界并被观察到。当在系统边界观察到称为故障的错误状态时。

**故障注入的分类:**
故障注入根据软件实现可以分为两类:编译时故障注入和运行时故障注入。这些解释如下。

**1。编译时故障注入:**
编译时故障注入是一种故障注入技术，通过修改源代码将模拟故障注入系统。

两种方法用于在编译时实现故障:

*   **Code Modification:**
    Mutation testing is used to change existing lines of code so that there may exist faults. Code mutation produces faults which are similar to the faults unintentionally done by programmers.

    **示例:**

    ```
    Original Code:
    int main()
    {
      int a = 10;
      while ( a > 0 )
      {
        cout << "GFG";
        a = a - 1;
      }
      return 0;
    }

    Modified Code:
    int main()
    {
      int a = 10;
      while ( a > 0 )
      {
        cout << "GFG";
        a = a + 1; // '-' is changed to '+'
      }
      return 0;
    } 
    ```

    现在可以观察到，a 的值将增加，“while 循环”将永远不会终止，程序将进入无限循环。

*   **Code Insertion:**
    A second method of code mutation is code insertion fault injection which adds code instead of modifying existing code. This is basically done by the use of anxiety functions which are simple functions which take an existing value and change it via some logic into another value.

    **示例:**

    ```
    Original Code:
    int main()
    {
      int a = 10;
      while ( a > 0 )
      {
        cout << "GFG";
        a = a - 1;
      }
      return 0;
    }

    Modified Code:
    int main()
    {
      int a = 10;
      while ( a > 0 )
      {
        cout << "GFG";
        a = a - 1;
        a++; // Additional code
      }
      return 0;
    } 
    ```

    现在可以观察到，a 的值将是固定的，“while 循环”永远不会终止，程序将进入无限循环。

**2。运行时故障注入:**
运行时故障注入技术使用软件触发器将故障注入正在运行的软件系统。故障可以通过多种物理方法注入，触发器可以通过不同的方式实现。

**运行时故障注入中使用的软件触发器:**

```
1. Time Based Triggers
2. Interrupt Based Triggers 
```

3 种方法用于在运行时注入故障:

1.  **破坏内存空间:**
    这个方法涉及破坏主内存和处理器寄存器。
2.  **系统调用介入:**
    该方法涉及从操作系统内核接口到执行系统软件的故障模拟。这是通过拦截用户级软件进行的操作系统调用并向其中注入错误来实现的。
3.  **网络级别:**
    此方法与网络接口处网络数据包的损坏、丢失或重新排序有关。

**不同软件测试中的故障注入:**

*   (a) **健壮性测试–**在健壮性测试中，使用故障注入。
*   (b) **压力测试–**故障注入也用于压力测试。