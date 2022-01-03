# 奇怪地重复出现的模板模式(CRTP)

> 原文:[https://www . geesforgeks . org/好奇地-重复-模板-模式-crtp-2/](https://www.geeksforgeeks.org/curiously-recurring-template-pattern-crtp-2/)

**背景:**
建议参考[虚函数和运行时多态](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)作为前提。下面是一个演示运行时多态性的示例程序。

## 卡片打印处理机（Card Print Processor 的缩写）

```
// A simple C++ program to demonstrate run-time
// polymorphism
#include <chrono>
#include <iostream>
using namespace std;

typedef std::chrono::high_resolution_clock Clock;

// To store dimensions of an image
class Dimension {
public:
    Dimension(int _X, int _Y)
    {
        mX = _X;
        mY = _Y;
    }

private:
    int mX, mY;
};

// Base class for all image types
class Image {
public:
    virtual void Draw() = 0;
    virtual Dimension GetDimensionInPixels() = 0;

protected:
    int dimensionX;
    int dimensionY;
};

// For Tiff Images
class TiffImage : public Image {
public:
    void Draw() {}
    Dimension GetDimensionInPixels()
    {
        return Dimension(dimensionX, dimensionY);
    }
};

// There can be more derived classes like PngImage,
// BitmapImage, etc

// Driver code that calls virtual function
int main()
{
    // An image type
    Image* pImage = new TiffImage;

    // Store time before virtual function calls
    auto then = Clock::now();

    // Call Draw 1000 times to make sure performance
    // is visible
    for (int i = 0; i < 1000; ++i)
        pImage->Draw();

    // Store time after virtual function calls
    auto now = Clock::now();

    cout << "Time taken: "
         << std::chrono::duration_cast<std::chrono::nanoseconds>(now - then).count()
         << " nanoseconds" << endl;

    return 0;
}
```

输出:

```
Time taken: 2613 nanoseconds
```

以上结果见[本](http://ideone.com/K9uGcj)。
当一个方法被声明为虚拟方法时，编译器会秘密地为我们做两件事:

1.  在类对象的前 4 个字节中定义一个 VPtr
2.  在构造函数中插入代码，初始化 VPtr 以指向 VTable

**什么是 VTable 和 VPtr？**
当一个方法在类中被声明为虚拟时，编译器会创建一个虚拟表(又称 VTable)，并将虚拟方法的地址存储在该表中。然后创建并初始化一个虚拟指针(又名 VPtr)来指向该虚拟表。一个虚拟表在类的所有实例之间共享，即编译器只创建一个虚拟表的实例在类的所有对象之间共享。该类的每个实例都有自己的 VPtr 版本。如果我们打印包含至少一个虚拟方法的类对象的大小，输出将是 size of(类数据)+ sizeof(VPtr)。
由于虚拟方法的地址存储在 VTable 中，因此可以操纵 VPtr 来调用这些虚拟方法，从而违反封装原则。见下例:

## 卡片打印处理机（Card Print Processor 的缩写）

```
// A C++ program to demonstrate that we can directly
// manipulate VPtr. Note that this program is based
// on the assumption that compiler store vPtr in a
// specific way to achieve run-time polymorphism.
#include <iostream>
using namespace std;

#pragma pack(1)

// A base class with virtual function foo()
class CBase {
public:
    virtual void foo() noexcept
    {
        cout << "CBase::Foo() called" << endl;
    }

protected:
    int mData;
};

// A derived class with its own implementation
// of foo()
class CDerived : public CBase {
public:
    void foo() noexcept
    {
        cout << "CDerived::Foo() called" << endl;
    }

private:
    char cChar;
};

// Driver code
int main()
{
    // A base type pointer pointing to derived
    CBase* pBase = new CDerived;

    // Accessing vPtr
    int* pVPtr = *(int**)pBase;

    // Calling virtual method
    ((void (*)())pVPtr[0])();

    // Changing vPtr
    delete pBase;
    pBase = new CBase;
    pVPtr = *(int**)pBase;

    // Calls method for new base object
    ((void (*)())pVPtr[0])();

    return 0;
}
```

输出:

```
CDerived::Foo() called
CBase::Foo() called 
```

我们能够访问 vPtr，并且能够通过它调用虚拟方法。物体的记忆表现在这里解释为。
**用虚法明智吗？**
可以看到，通过基类指针，对派生类方法的调用正在被调度。一切似乎都很顺利。那问题是什么？
如果一个虚拟例程被多次调用(几十万的量级)，会降低系统的性能，原因是每次调用该例程时，都需要通过使用 VPtr 查看 VTable 来解析其地址。对虚拟方法的每次调用的额外间接引用(指针取消引用)使得访问 VTable 成为一项代价高昂的操作，最好尽可能避免它。
**【奇怪重复的模板模式】(CRTP)**
通过奇怪重复的模板模式(CRTP)，可以完全避免使用 VPtr 和 VTable。CRTP 是 C++中的一种设计模式，其中类 X 使用 X 本身作为模板参数从类模板实例化中派生出来。更一般地说，它被称为 F-结合多态性。

## 卡片打印处理机（Card Print Processor 的缩写）

```
// Image program (similar to above) to demonstrate
// working of CRTP
#include <chrono>
#include <iostream>
using namespace std;

typedef std::chrono::high_resolution_clock Clock;

// To store dimensions of an image
class Dimension {
public:
    Dimension(int _X, int _Y)
    {
        mX = _X;
        mY = _Y;
    }

private:
    int mX, mY;
};

// Base class for all image types. The template
// parameter T is used to know type of derived
// class pointed by pointer.
template <class T>
class Image {
public:
    void Draw()
    {
        // Dispatch call to exact type
        static_cast<T*>(this)->Draw();
    }
    Dimension GetDimensionInPixels()
    {
        // Dispatch call to exact type
        static_cast<T*>(this)->GetDimensionInPixels();
    }

protected:
    int dimensionX, dimensionY;
};

// For Tiff Images
class TiffImage : public Image<TiffImage> {
public:
    void Draw()
    {
        // Uncomment this to check method dispatch
        // cout << "TiffImage::Draw() called" << endl;
    }
    Dimension GetDimensionInPixels()
    {
        return Dimension(dimensionX, dimensionY);
    }
};

// There can be more derived classes like PngImage,
// BitmapImage, etc

// Driver code
int main()
{
    // An Image type pointer pointing to Tiffimage
    Image<TiffImage>* pImage = new TiffImage;

    // Store time before virtual function calls
    auto then = Clock::now();

    // Call Draw 1000 times to make sure performance
    // is visible
    for (int i = 0; i < 1000; ++i)
        pImage->Draw();

    // Store time after virtual function calls
    auto now = Clock::now();

    cout << "Time taken: "
         << std::chrono::duration_cast<std::chrono::nanoseconds>(now - then).count()
         << " nanoseconds" << endl;

    return 0;
}
```

输出:

```
Time taken: 732 nanoseconds
```

以上结果见[本](http://ideone.com/IPD5Va)。
**虚法 vs CRTP 基准**
使用虚法花费的时间为 2613 纳秒。CRTP 的这一(小)性能提升是因为规避了 VTable 调度的使用。请注意，性能取决于很多因素，如使用的编译器、虚拟方法执行的操作。在不同的运行中，性能数字可能会有所不同，但预计 CRTP 会有(小)性能提升。
注意:如果我们在 CRTP 打印班级大小，可以看到 VPtr 不再保留 4 字节内存。

```

cout << sizeof(Image) << endl; 
```

CRTP 的另一个用例是，当需要访问基类成员函数中的派生类对象时，必须使用 CRTP。

## 卡片打印处理机（Card Print Processor 的缩写）

```
#include <iostream>
#include <typeinfo>
using namespace std;

template <typename DerivedT>

class Base {
public:
    int accessDerivedData() // Parsing json object
    {
        // this will call the respective derived class object.
        auto derived = static_cast<DerivedT*>(this);

        // some generic parsing logic for any json object
        // then call derived objects to set parsed values
        derived->implementation();
        derived->display();
    }
};

class Derived1 : public Base<Derived1> // jsonMessage1
{
public:
    int data1;
    Derived1() { cout << "Derived1 constr" << endl; }
    void display()
    {
        cout << " data1:" << data1 << endl;
    }
    void implementation()
    {
        this->data1 = 8900;
    }
};

class Derived2 : public Base<Derived2> // jsonMessage2
{
public:
    int data2;
    Derived2() { cout << "Derived2 constr" << endl; }
    void display()
    {
        cout << " data2:" << data2 << endl;
    }
    void implementation()
    {
        this->data2 = 898;
    }
};

int main()
{
    auto obj1 = new Derived1;
    obj1->accessDerivedData();

    auto obj2 = new Derived2;
    obj2->accessDerivedData();
}
```

有问题吗？让他们继续来。我们很乐意回答。
**参考资料**
[https://en . Wikipedia . org/wiki/好奇地 _ recursive _ template _ pattern](http://Reference(s) https://en.wikipedia.org/wiki/Curiously_recurring_template_pattern)
本文由[**aashis Barnwal**](https://about.me/aashishbarnwal)供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息