# 编程范例介绍

> 原文:[https://www . geesforgeks . org/编程范例介绍/](https://www.geeksforgeeks.org/introduction-of-programming-paradigms/)

**范式**也可以称为解决某个问题或完成某项任务的方法。编程范式是一种使用某种编程语言解决问题的方法，或者我们也可以说它是一种使用工具和技术来解决问题的方法，这些工具和技术可用于我们遵循某种方法。有许多已知的编程语言，但是它们在实现时都需要遵循某种策略，这种方法/策略就是范例。除了各种编程语言之外，还有许多范例来满足每一个需求。下面讨论它们:

![](img/f38ca1725dc3a924d88dfbc32b5e3d2d.png)

**1。命令式编程范式:**
它是最古老的编程范式之一。它的特点是与机器架构密切相关。它基于冯·诺依曼架构。它通过赋值语句来改变程序状态。它通过改变状态来逐步执行任务。主要的重点是如何实现目标。范例由几个语句组成，在执行之后，所有的结果都被存储。

**优势:**

1.  实现起来非常简单
2.  它包含循环、变量等。

**劣势:**

1.  复杂的问题无法解决
2.  效率更低，生产率更低
3.  并行编程是不可能的

```
Examples of Imperative programming paradigm:

C : developed by Dennis Ritchie and Ken Thompson
Fortan : developed by John Backus for IBM
Basic : developed by John G Kemeny and Thomas E Kurtz 
```

## C

```
// average of five number in C

int marks[5] = { 12, 32, 45, 13, 19 } int sum = 0;
float average = 0.0;
for (int i = 0; i < 5; i++) {
    sum = sum + marks[i];
}
average = sum / 5;
```

命令式编程分为三大类:过程式、面向对象和并行处理。这些范例如下:

*   **过程编程范式–**
    这种范式从底层机器模型的角度强调过程。程序性方法和强制性方法没有区别。它具有重用代码的能力，并且由于它的可重用性，它在当时的使用中非常有用。

```
Examples of Procedural programming paradigm:

C : developed by Dennis Ritchie and Ken Thompson
C++ : developed by Bjarne Stroustrup
Java : developed by James Gosling at Sun Microsystems
ColdFusion : developed by J J Allaire
Pascal : developed by Niklaus Wirth 
```

## C++

```
#include <iostream>
using namespace std;
int main()
{
    int i, fact = 1, num;
    cout << "Enter any Number: ";
    cin >> number;
    for (i = 1; i <= num; i++) {
        fact = fact * i;
    }
    cout << "Factorial of " << num << " is: " << fact << endl;
    return 0;
}
```

然后是 OOP，

*   **面向对象编程–**
    程序是作为一个类和对象的集合来编写的，这些类和对象是用来通信的。最小和基本的实体是对象，所有类型的计算都只在对象上执行。更强调的是数据而不是程序。它可以处理几乎所有的现实生活中的问题，这是今天的场景。

**优势:**

*   数据安全
*   遗产
*   代码可重用性
*   灵活和抽象也是存在的

```
Examples of Object Oriented programming paradigm:

Simula : first OOP language
Java : developed by James Gosling at Sun Microsystems
C++ : developed by Bjarne Stroustrup
Objective-C : designed by Brad Cox
Visual Basic .NET : developed by Microsoft
Python : developed by Guido van Rossum
Ruby : developed by Yukihiro Matsumoto 
Smalltalk : developed by Alan Kay, Dan Ingalls, Adele Goldberg 

```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        System.out.println("GfG!");
        Signup s1 = new Signup();
        s1.create(22, "riya", "riya2@gmail.com", 'F', 89002);
    }
}

class Signup {
    int userid;
    String name;
    String emailid;
    char sex;
    long mob;

    public void create(int userid, String name, 
                        String emailid, char sex, long mob)
    {
        System.out.println("Welcome to 
                 GeeksforGeeks\nLets create your account\n");
        this.userid = 132;
        this.name = "Radha";
        this.emailid = "radha.89@gmail.com";
        this.sex = 'F';
        this.mob = 900558981;
        System.out.println("your account has been created");
    }
}
```

*   **并行处理方法–**
    并行处理是通过在多个处理器之间划分程序指令来处理程序指令。一个并行处理系统拥有许多处理器，其目标是通过划分处理器来减少运行一个程序的时间。这种做法似乎像是各个击破。例如 NESL(最老的一个)和 C/C++也支持，因为一些库函数。

**2。声明式编程范式:**
它分为逻辑、函数、数据库。在计算机科学中，*声明式编程*是一种构建程序的风格，它表达计算逻辑，而不谈论其控制流。它通常认为程序是某种逻辑的理论。它可以简化并行程序的编写。重点是需要做什么，而不是应该如何做，基本上强调代码实际上在做什么。它只是宣布了我们想要的结果，而不是它是如何产生的。这是命令式(如何做)和声明式(做什么)编程范例之间的唯一区别。深入研究我们会看到逻辑、功能和数据库。

*   **逻辑编程范式–**
    它可以被称为计算的抽象模型。它可以解决逻辑问题，如谜题、数列等。在逻辑程序设计中，我们有一个我们以前知道的知识库，连同给机器的问题和知识库，它产生结果。在正常的编程语言中，这种知识库的概念是不可用的，但是在使用人工智能、机器学习的概念时，我们有一些模型，例如使用相同机制的感知模型。
    在逻辑编程中，主要强调的是知识库和问题。程序的执行很像数学陈述的证明，例如 Prolog

```
sum of two number in prolog:

  predicates
  sumoftwonumber(integer, integer)
clauses

  sum(0, 0).
   sum(n, r):-
        n1=n-1,
        sum(n1, r1),
        r=r1+n 
```

*   **函数式编程范式–**
    函数式编程范式源于数学，与语言无关。这种范式的主要原则是执行一系列数学函数。抽象的中心模型是用于某些特定计算的函数，而不是数据结构。数据松散地耦合到函数。函数隐藏了它们实现。函数可以用它们的值替换，而不改变程序的含义。像 perl、javascript 这样的语言大多使用这种范式。

```
Examples of Functional programming paradigm:

JavaScript : developed by Brendan Eich
Haskwell : developed by Lennart Augustsson, Dave Barton
Scala : developed by Martin Odersky
Erlang : developed by Joe Armstrong, Robert Virding
Lisp : developed by John Mccarthy
ML : developed by Robin Milner
Clojure : developed by Rich Hickey 
```

下一种方法是数据库。

*   **数据库/数据驱动编程方法–**
    这种编程方法基于数据及其移动。程序语句是由数据定义的，而不是对一系列步骤进行硬编码。数据库程序是业务信息系统的核心，提供文件创建、数据输入、更新、查询和报告功能。有几种主要为数据库应用开发的编程语言。例如 SQL。它应用于结构化数据流，用于过滤、转换、聚合(如计算统计数据)或调用其他程序。所以它有自己广泛的应用。

```
CREATE DATABASE databaseAddress;
CREATE TABLE Addr (
    PersonID int,
    LastName varchar(200),
    FirstName varchar(200),
    Address varchar(200),
    City varchar(200),
    State varchar(200)
); 
```