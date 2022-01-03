# 如何利用面向对象原理设计停车场？

> 原文:[https://www . geesforgeks . org/design-park-look-use-object-oriented-principles/](https://www.geeksforgeeks.org/design-parking-lot-using-object-oriented-principles/)

使用面向对象的原则设计停车场。

**问于:**亚马逊、苹果、谷歌等更多采访

**解决方案:**出于我们现在的目的，我们将做出以下假设。我们做了这些具体的假设，以便在不增加太多复杂性的情况下给问题增加一点复杂性。如果你做了不同的假设，那完全没问题。
1)停车场有多层。每一层都有多行斑点。
2)停车场可以停放摩托车、汽车和公共汽车。
3)停车场有摩托车点、小型点和大型点。
4)摩托车可以停在任何地点。
5)一辆车既可以停在单个紧凑点，也可以停在单个大点。
6)一辆公交车可以停在连续的同一排的五个大点上。它不能停在小地方。

在下面的实现中，我们创建了一个抽象类 Vehicle，汽车、公共汽车和摩托车继承自该类。为了处理不同的停车位大小，我们只有一个类停车位，它有一个指示大小的成员变量。

**下面给出的 Java 主逻辑**

```
// Vehicle and its inherited classes.
public enum VehicleSize { Motorcycle, Compact,Large }

public abstract class Vehicle
{
      protected ArrayList<ParkingSpot> parkingSpots =
                           new ArrayList<ParkingSpot>();
      protected String licensePlate;
      protected int spotsNeeded;
      protected VehicleSize size;

      public int getSpotsNeeded()
      {
          return spotsNeeded;
      }
      public VehicleSize getSize()
      {
          return size;
      }

      /* Park vehicle in this spot (among others,
         potentially) */
      public void parkinSpot(ParkingSpot s)
      {
          parkingSpots.add(s);
      }

      /* Remove vehicle from spot, and notify spot
         that it's gone */
      public void clearSpots() { ... }

      /* Checks if the spot is big enough for the
         vehicle (and is available).
         This * compares the SIZE only.It does not
        check if it has enough spots. */
      public abstract boolean canFitinSpot(ParkingSpot spot);
}

public class Bus extends Vehicle
{
    public Bus()
    {
        spotsNeeded = 5;
        size = VehicleSize.Large;
    }

    /* Checks if the spot is a Large. Doesn't check
     num of spots */
    public boolean canFitinSpot(ParkingSpot spot) 
    {... }
}

public class Car extends Vehicle
{
    public Car()
    {
        spotsNeeded = 1;
        size = VehicleSize.Compact;
    }

    /* Checks if the spot is a Compact or a Large. */
    public boolean canFitinSpot(ParkingSpot spot) 
    { ... }
}

public class Motorcycle extends Vehicle
{
    public Motorcycle()
    {
        spotsNeeded = 1;
        size = VehicleSize.Motorcycle;
    }
    public boolean canFitinSpot(ParkingSpot spot) 
    { ... }
}

```

**停车点**是通过仅具有一个表示光点大小的变量来实现的。我们可以通过为继承自 ParkingSpot 的 LargeSpot、CompactSpot 和 MotorcycleSpot 创建类来实现这一点，但这可能被过度扼杀了。这些斑点可能没有不同的行为，除了它们的大小。

```
public class ParkingSpot
{
    private Vehicle vehicle;
    private VehicleSize spotSize;
    private int row;
    private int spotNumber;
    private Level level;

    public ParkingSpot(Level lvl, int r, int n,
                         VehicleSize s)
    { ... }

    public boolean isAvailable()
    {
        return vehicle == null;
    }

    /* Check if the spot is big enough and is available */
    public boolean canFitVehicle(Vehicle vehicle) { ... }

    /* Park vehicle in this spot. */
    public boolean park(Vehicle v) {..}

    public int getRow()
    {
        return row;
    }
    public int getSpotNumber()
    {
        return spotNumber;
    }

    /* Remove vehicle from spot, and notify
      level that a new spot is available */
    public void removeVehicle() { ... }
}
```

**来源:**T2[www.andiamogo.com/S-OOD.pdf](http://www.andiamogo.com/S-OOD.pdf)

**更多参考资料:**
[https://www . quora . com/How-I-answer-design-related-questions-like-design-a-a-a-Amazon-停车场-面试](https://www.quora.com/How-do-I-answer-design-related-questions-like-design-a-parking-lot-in-an-Amazon-interview)
[http://stackoverflow . com/questions/764933/Amazon-面试-question-design-a-oo-停车场](http://stackoverflow.com/questions/764933/amazon-interview-question-design-an-oo-parking-lot)

本文由 Somesh Awasthi 先生供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。