# 设计图案|第二套(工厂法)

> 原文:[https://www . geesforgeks . org/design-patterns-set-2-factory-method/](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/)

工厂方法是一种[创造设计模式](https://www.geeksforgeeks.org/design-patterns-set-1-introduction/)，即与对象创造相关。在工厂模式中，我们创建对象，而不向客户端公开创建逻辑，客户端使用相同的公共接口来创建新类型的对象。

其思想是使用静态成员函数(静态工厂方法)来创建和返回实例，对用户隐藏类模块的细节。
工厂模式是创建对象的核心设计原则之一，允许客户端以不与库的类层次结构紧密耦合的方式创建库的对象(如下所述)。

***当我们谈论*** **【图书馆】** ***和客户时，是什么意思？***
库是由某个第三方提供的东西，它公开了一些公共 API，客户端调用这些公共 API 来完成自己的任务。一个非常简单的例子是安卓操作系统提供的不同类型的视图。

***为什么是工厂模式？***
我们举个例子来理解一下:

## C

```
// A design without factory pattern
#include <iostream>
using namespace std;

// Library classes
class Vehicle {
public:
    virtual void printVehicle() = 0;
};
class TwoWheeler : public Vehicle {
public:
    void printVehicle()  {
        cout << "I am two wheeler" << endl;
    }
};
class FourWheeler : public Vehicle {
    public:
    void printVehicle()  {
        cout << "I am four wheeler" << endl;
    }
};

// Client (or user) class
class Client {
public:
    Client(int type)  {

        // Client explicitly creates classes according to type
        if (type == 1)
            pVehicle = new TwoWheeler();
        else if (type == 2)
            pVehicle = new FourWheeler();
        else
            pVehicle = NULL;
    }

    ~Client()   {
        if (pVehicle)
        {
            delete[] pVehicle;
            pVehicle = NULL;
        }
    }

    Vehicle* getVehicle() {
        return pVehicle;
    }
private:
    Vehicle *pVehicle;
};

// Driver program
int main() {
    Client *pClient = new Client(1);
    Vehicle * pVehicle = pClient->getVehicle();
    pVehicle->printVehicle();
    return 0;
}
```

**输出:**

```
I am two wheeler
```

***什么*** **都是***T7*T10***上面设计的问题？***
正如您在上面的示例中所观察到的，客户端在构建其对象的过程中，基于一些输入创建了两轮车或四轮车的对象。
比如说，图书馆推出了一种新的三轮汽车，也包括三轮汽车。会发生什么？如果在条件阶梯中，客户端将最终链接一个新的 else 来创建三轮车的对象。这又需要重新编译客户端。因此，每次在库端进行新的更改时，客户机都需要在其末端进行一些相应的更改，并重新编译代码。听起来很糟糕？这是非常糟糕的设计实践。

**如何避免问题？**
答案是，创建一个静态(或工厂)方法。让我们看看下面的代码。

## C

```
// C++ program to demonstrate factory method design pattern
#include <iostream>
using namespace std;

enum VehicleType {
    VT_TwoWheeler,    VT_ThreeWheeler,    VT_FourWheeler
};

// Library classes
class Vehicle {
public:
    virtual void printVehicle() = 0;
    static Vehicle* Create(VehicleType type);
};
class TwoWheeler : public Vehicle {
public:
    void printVehicle() {
        cout << "I am two wheeler" << endl;
    }
};
class ThreeWheeler : public Vehicle {
public:
    void printVehicle() {
        cout << "I am three wheeler" << endl;
    }
};
class FourWheeler : public Vehicle {
    public:
    void printVehicle() {
        cout << "I am four wheeler" << endl;
    }
};

// Factory method to create objects of different types.
// Change is required only in this function to create a new object type
Vehicle* Vehicle::Create(VehicleType type) {
    if (type == VT_TwoWheeler)
        return new TwoWheeler();
    else if (type == VT_ThreeWheeler)
        return new ThreeWheeler();
    else if (type == VT_FourWheeler)
        return new FourWheeler();
    else return NULL;
}

// Client class
class Client {
public:

    // Client doesn't explicitly create objects
    // but passes type to factory method "Create()"
    Client()
    {
        VehicleType type = VT_ThreeWheeler;
        pVehicle = Vehicle::Create(type);
    }
    ~Client() {
        if (pVehicle) {
            delete[] pVehicle;
            pVehicle = NULL;
        }
    }
    Vehicle* getVehicle()  {
        return pVehicle;
    }

private:
    Vehicle *pVehicle;
};

// Driver program
int main() {
    Client *pClient = new Client();
    Vehicle * pVehicle = pClient->getVehicle();
    pVehicle->printVehicle();
    return 0;
}
```

**输出:**

```
I am three wheeler
```

在上面的例子中，我们已经将对象创建的类型选择与客户端完全分离。该库现在负责根据输入决定创建哪个对象类型。客户端只需要调用库的工厂 Create 方法并传递它想要的类型，而不用担心对象创建的实际实现。

**工厂方法的其他例子:**

1.  比方说，在一个“绘图”系统中，根据用户的输入，不同的图片像正方形、长方形、圆形都可以画出来。在这里，我们可以根据用户的输入使用 factory 方法创建实例。对于添加新类型的形状，不需要更改客户端的代码。
2.  另一个例子:在旅游网站上，我们可以预订火车票以及公共汽车票和机票。在这种情况下，用户可以给出他的旅行类型为“公共汽车”、“火车”或“航班”。
    这里我们有一个抽象类‘any travel’，带有一个静态成员函数‘GetObject’，根据用户的出行类型，它将创建&返回一个‘BusTravel’或‘trainetravel’的对象。“旅行”或“列车旅行”有共同的功能，如乘客姓名、出发地、目的地参数。

**进一步阅读:**[Python 中的工厂方法](https://www.geeksforgeeks.org/factory-method-python-design-patterns/)
如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。