# 命令模式

> 原文:[https://www.geeksforgeeks.org/command-pattern/](https://www.geeksforgeeks.org/command-pattern/)

像[之前的](https://www.geeksforgeeks.org/category/design/)文章一样，让我们拿起一个设计问题来理解命令模式。假设您正在构建一个家庭自动化系统。有一个可编程遥控器，可以用来打开和关闭你家里的各种物品，如灯、立体声、交流电等。看起来像这样。

你可以用简单的 if-else 语句来完成，比如

```
if (buttonPressed == button1)
     lights.on()

```

但是我们需要记住，打开一些设备，如立体声，包括许多步骤，如设置 cd，音量等。我们还可以重新分配一个按钮来做其他事情。通过使用简单的 if-else，我们是在为实现而不是接口编码。还有紧耦合。

因此，我们想要实现的是一种提供松散耦合的设计，并且远程控制不应该有关于特定设备的太多信息。命令模式帮助我们做到这一点。

**定义:****命令模式**将一个请求封装为一个对象，从而让我们用不同的请求参数化其他对象，对请求进行排队或记录，并支持可撤销的操作。

这个定义一开始有点混乱，但是让我们一步一步来。与我们上面的问题类似，遥控器是客户端和立体声、灯光等。是接收者。在命令模式中，有一个命令对象*通过将特定接收器上的一组动作绑定在一起来封装一个请求*。它通过只公开一个方法 execute()来实现这一点，该方法会导致在接收器上调用一些操作。

*用不同的请求参数化其他对象*在我们的类比中，这意味着用来开灯的按钮以后可以用来打开立体声或者可能打开车库门。

*对请求进行排队或记录，并支持可撤销操作*意味着命令的执行操作可以在命令本身中存储用于反转其效果的状态。该命令可能添加了一个“未执行”操作，该操作可以逆转前一个要执行的调用的效果。它还支持记录更改，以便在系统崩溃时可以重新应用。

下面是上面提到的远程控制示例的 Java 实现:

```
// A simple Java program to demonstrate
// implementation of Command Pattern using
// a remote control example.

// An interface for command
interface Command
{
    public void execute();
}

// Light class and its corresponding command
// classes
class Light
{
    public void on()
    {
        System.out.println("Light is on");
    }
    public void off()
    {
        System.out.println("Light is off");
    }
}
class LightOnCommand implements Command
{
    Light light;

    // The constructor is passed the light it
    // is going to control.
    public LightOnCommand(Light light)
    {
       this.light = light;
    }
    public void execute()
    {
       light.on();
    }
}
class LightOffCommand implements Command
{
    Light light;
    public LightOffCommand(Light light)
    {
        this.light = light;
    }
    public void execute()
    {
         light.off();
    }
}

// Stereo and its command classes
class Stereo
{
    public void on()
    {
        System.out.println("Stereo is on");
    }
    public void off()
    {
        System.out.println("Stereo is off");
    }
    public void setCD()
    {
        System.out.println("Stereo is set " +
                           "for CD input");
    }
    public void setDVD()
    {
        System.out.println("Stereo is set"+
                         " for DVD input");
    }
    public void setRadio()
    {
        System.out.println("Stereo is set" +
                           " for Radio");
    }
    public void setVolume(int volume)
    {
       // code to set the volume
       System.out.println("Stereo volume set"
                          + " to " + volume);
    }
}
class StereoOffCommand implements Command
{
    Stereo stereo;
    public StereoOffCommand(Stereo stereo)
    {
        this.stereo = stereo;
    }
    public void execute()
    {
       stereo.off();
    }
}
class StereoOnWithCDCommand implements Command
{
     Stereo stereo;
     public StereoOnWithCDCommand(Stereo stereo)
     {
         this.stereo = stereo;
     }
     public void execute()
     {
         stereo.on();
         stereo.setCD();
         stereo.setVolume(11);
     }
}

// A Simple remote control with one button
class SimpleRemoteControl
{
    Command slot;  // only one button

    public SimpleRemoteControl()
    {
    }

    public void setCommand(Command command)
    {
        // set the command the remote will
        // execute
        slot = command;
    }

    public void buttonWasPressed()
    {
        slot.execute();
    }
}

// Driver class
class RemoteControlTest
{
    public static void main(String[] args)
    {
        SimpleRemoteControl remote =
                  new SimpleRemoteControl();
        Light light = new Light();
        Stereo stereo = new Stereo();

        // we can change command dynamically
        remote.setCommand(new
                    LightOnCommand(light));
        remote.buttonWasPressed();
        remote.setCommand(new
                StereoOnWithCDCommand(stereo));
        remote.buttonWasPressed();
        remote.setCommand(new
                   StereoOffCommand(stereo));
        remote.buttonWasPressed();
     }
  }
```

**输出:**

```
Light is on
Stereo is on
Stereo is set for CD input
Stereo volume set to 11
Stereo is off
```

请注意，遥控器对打开立体声一无所知。该信息包含在单独的命令对象中。这减少了它们之间的耦合。

**优点:**

*   Make our code extensible because we can add new commands without changing the existing code.
*   Reduce the coupling between the caller and the receiver of the command.

**劣势:**

*   Increase the number of classes per individual command.

**进一步阅读–**[Python 中的命令方法](https://www.geeksforgeeks.org/command-method-python-design-patterns/)

***参考文献:***

*   First design pattern (book)
*   [https://github。com/Beth Robson/Head-First-Design-Patterns/tree/master/src/Head First/Design Patterns/command](https://github.com/bethrobson/Head-First-Design-Patterns/tree/master/src/headfirst/designpatterns/command)

如果本文由**苏拉布·库马尔**投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，然后把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论