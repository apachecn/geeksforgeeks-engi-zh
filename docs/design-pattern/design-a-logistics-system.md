# 设计物流系统

> 原文:[https://www.geeksforgeeks.org/design-a-logistics-system/](https://www.geeksforgeeks.org/design-a-logistics-system/)

设计一个物流系统(面向对象设计)。讲述不同的班级以及他们之间的关系。这是**而不是**一个系统设计问题，所以这个问题的范围只是定义不同的类(有它的属性和方法)
**问在** : Adobe
**解决方案:**假设我们想设计一个物流系统，它有以下基本功能:
系统可以接受订单并将其交付到给定的目的地。
订单将是一个项目列表，每个订单都有处理成本。
用户必须自己注册才能使用该系统。
用户可以跟踪他/她的订单。
·订单将通过自行车或卡车运输，但只有一份订单将通过一辆车运输。
面试时会问这类问题，以判断候选人的面向对象设计技能。所以，首先我们应该考虑班级。
主要类别为:
1。用户
2。第
3 项。车辆
4。位置
5。付款明细
6。订单
7。物流系统
用户类是针对用户/客户/顾客的，他们将被收取送货费。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class User {

    private int userId;
    private String name;
    private Location address;
    private String mobNo;
    private String emailId;

    public int getUserId()
    {
        return userId;
    }

    public void setUserId(int userId)
    {
        this.userId = userId;
    }

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }

    public Location getAddress()
    {
        return address;
    }

    public void setAddress(Location address)
    {
        this.address = address;
    }

    public String getMobNo()
    {
        return mobNo;
    }

    public void setMobNo(String mobNo)
    {
        this.mobNo = mobNo;
    }

    public String getEmailId()
    {
        return emailId;
    }

    public void setEmailId(String emailId)
    {
        this.emailId = emailId;
    }
}
```

物料类别表示将要装运的物料。订单将包含一个项目列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Item {

    private String name;
    private int price;
    private int volume;
    private int weight;

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }

    public int getPrice()
    {
        return price;
    }

    public void setPrice(int price)
    {
        this.price = price;
    }

    public int getVolume()
    {
        return volume;
    }

    public void setVolume(int volume)
    {
        this.volume = volume;
    }

    public int getWeight()
    {
        return weight;
    }

    public void setWeight(int weight)
    {
        this.weight = weight;
    }
}
```

位置类只是代表地址。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Location {

    private Double longitude;
    private Double latitude;

    public Double getLongitude()
    {
        return longitude;
    }

    public void setLongitude(Double longitude)
    {
        this.longitude = longitude;
    }

    public Double getLatitude()
    {
        return latitude;
    }

    public void setLatitude(Double latitude)
    {
        this.latitude = latitude;
    }
}
```

车辆类别代表将用于装运/交付订单的车辆。
会有两种类型:1。自行车和 2。卡车

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Vehicle {

    private int id;
    private String vehicleNo;
    private int capacity;
    private Location currentPosition;
    private VehicleStatus currentStatus;

    public Vehicle(int id, String vehicleNo, int capacity)
    {
        this.id = id;
        this.vehicleNo = vehicleNo;
        this.capacity = capacity;
    }

    public int getId()
    {
        return id;
    }

    public void setId(int id)
    {
        this.id = id;
    }

    public String getVehicleNo()
    {
        return vehicleNo;
    }

    public void setVehicleNo(String vehicleNo)
    {
        this.vehicleNo = vehicleNo;
    }

    public int getCapacity()
    {
        return capacity;
    }

    public void setCapacity(int capacity)
    {
        this.capacity = capacity;
    }

    public Location getCurrentPosition()
    {
        return currentPosition;
    }

    public void setCurrentPosition(Location currentPosition)
    {
        this.currentPosition = currentPosition;
    }

    public VehicleStatus getCurrentStatus()
    {
        return currentStatus;
    }

    public void setCurrentStatus(VehicleStatus currentStatus)
    {
        this.currentStatus = currentStatus;
    }
}
```

这辆自行车只有 10 个单位的容量。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Bike extends Vehicle {

    private final static int capacityofBike = 10;

    public Bike(int id, String vehicleNo)
    {

        super(id, vehicleNo, capacityofBike);
    }
}
```

卡车只有 100 单位的容量(是自行车的 10 倍)。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Truck extends Vehicle {

    private final static int capacityofTruck = 100;

    public Truck(int id, String vehicleNo)
    {
        super(id, vehicleNo, capacityofTruck);
    }
}
```

车辆当前状态的枚举:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public enum VehicleStatus {
    FREE,
    BUSY,
    NOT_WORKING;
}
```

订单优先级的枚举:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public enum OrderPriority {
    LOW,
    MEDIUM,
    HIGH;
}
```

订单状态的枚举:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public enum OrderStatus {
    DELIVERED,
    PROCESSING,
    CANCELLED;
}
```

支付枚举模式:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public enum PaymentMode {

    NET_BANKING,
    CREDIT_CARD,
    DEBIT_CARD;
}
```

列举的付款状态:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public enum PaymentStatus {
    PAID,
    UNPAID;
}
```

PaymentDetails 类包含与支付相关的信息，因此无论如何订单被取消，都可以轻松退款。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class PaymentDetails {
    private PaymentMode paymentMode;
    private String transactionId;
    private int amount;
    private PaymentStatus paymentStatus;
    private String cardNumber;

    public PaymentMode getPaymentMode()
    {
        return paymentMode;
    }

    public void setPaymentMode(PaymentMode paymentMode)
    {
        this.paymentMode = paymentMode;
    }

    public String getTransactionId()
    {
        return transactionId;
    }

    public void setTransactionId(String transactionId)
    {
        this.transactionId = transactionId;
    }

    public int getAmount()
    {
        return amount;
    }

    public void setAmount(int amount)
    {
        this.amount = amount;
    }

    public PaymentStatus getPaymentStatus()
    {
        return paymentStatus;
    }

    public void setPaymentStatus(PaymentStatus paymentStatus)
    {
        this.paymentStatus = paymentStatus;
    }

    public String getCardNumber()
    {
        return cardNumber;
    }

    public void setCardNumber(String cardNumber)
    {
        this.cardNumber = cardNumber;
    }
}
```

订单类包含订单的所有信息。所有字段都是不言自明的。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Date;
import java.util.List;

public class Order {

    private int orderId;
    private OrderPriority priority_of_order;
    private User sender;
    private Location destination;
    private PaymentDetails paymentDetails;
    private List<Item> items;
    private Long totalWeight;
    private OrderStatus currentStatus;
    private Date timeOfOrderPlaced;
    private Date timeOfOrderDelivery;
    private Vehicle vehicleOfThisOrder;

    public int getOrderId()
    {
        return orderId;
    }

    public void setOrderId(int orderId)
    {
        this.orderId = orderId;
    }

    public OrderPriority getPriority_of_order()
    {
        return priority_of_order;
    }

    public void setPriority_of_order(OrderPriority priority_of_order)
    {
        this.priority_of_order = priority_of_order;
    }

    public User getSender()
    {
        return sender;
    }

    public void setSender(User sender)
    {
        this.sender = sender;
    }

    public Location getDestination()
    {
        return destination;
    }

    public void setDestination(Location destination)
    {
        this.destination = destination;
    }

    public PaymentDetails getPaymentDetails()
    {
        return paymentDetails;
    }

    public void setPaymentDetails(PaymentDetails paymentDetails)
    {
        this.paymentDetails = paymentDetails;
    }

    public List<Item> getItems()
    {
        return items;
    }

    public void setItems(List<Item> items)
    {
        this.items = items;
    }

    public Long getTotalWeight()
    {
        return totalWeight;
    }

    public void setTotalWeight(Long totalWeight)
    {
        this.totalWeight = totalWeight;
    }

    public OrderStatus getCurrentStatus()
    {
        return currentStatus;
    }

    public void setCurrentStatus(OrderStatus currentStatus)
    {
        this.currentStatus = currentStatus;
    }

    public Date getTimeOfOrderPlaced()
    {
        return timeOfOrderPlaced;
    }

    public void setTimeOfOrderPlaced(Date timeOfOrderPlaced)
    {
        this.timeOfOrderPlaced = timeOfOrderPlaced;
    }

    public Date getTimeOfOrderDelivery()
    {
        return timeOfOrderDelivery;
    }

    public void setTimeOfOrderDelivery(Date timeOfOrderDelivery)
    {
        this.timeOfOrderDelivery = timeOfOrderDelivery;
    }

    public Vehicle getVehicleOfThisOrder()
    {
        return vehicleOfThisOrder;
    }

    public void setVehicleOfThisOrder(Vehicle vehicleOfThisOrder)
    {
        this.vehicleOfThisOrder = vehicleOfThisOrder;
    }
}
```

主类(物流系统)，存储用户、订单和车辆的所有信息。它有 takeAnOrder()，processOrder()等方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.ArrayList;
import java.util.List;

public class LogisticsSystem {

    private List<Order> orders;
    private List<Vehicle> vehicles;
    private List<User> users;

    public LogisticsSystem()
    {
        this.orders = new ArrayList<Order>();
        this.vehicles = new ArrayList<Vehicle>();
        this.users = new ArrayList<User>();
    }

    public void takeAnOrder(Order order)
    {
        System.out.println("Adding an order to the system");
        orders.add(order);
    }

    public void processOrder(Order order)
    {
        System.out.println("Processing an order of the system");
    }

    public Location trackOrder(int orderId)
    {
        System.out.println("Tracking an order of the system");
        Location location = null;
        // location = findLocationOfGivenOrder();
        return location;
    }

    public void cacelOrder(Order order)
    {
        System.out.println("Going to cancell an order of the system");
    }

    public void registerNewUser(User user)
    {
        System.out.println("Registering a new user to the system");
        users.add(user);
    }

    public List<Order> getOrders()
    {
        return orders;
    }

    public void setOrders(List<Order> orders)
    {
        this.orders = orders;
    }

    public List<Vehicle> getVehicles()
    {
        return vehicles;
    }

    public void setVehicles(List<Vehicle> vehicles)
    {
        this.vehicles = vehicles;
    }

    public List<User> getUsers()
    {
        return users;
    }

    public void setUsers(List<User> users)
    {
        this.users = users;
    }
}
```

这是测试应用程序的测试类。

## Java 语言(一种计算机语言，尤用于创建网站)

```
package com.shashi.oodesign;

import java.util.ArrayList;
import java.util.Date;
import java.util.List;

public class Apptest {

    public static void main(String[] args)
    {

        User user = new User();
        user.setUserId(1);
        user.setName("Shashi");
        user.setEmailId("shashi@gmail.com");

        Item item1 = new Item();
        item1.setName("item1");
        item1.setPrice(20);

        Item item2 = new Item();
        item2.setName("item2");
        item2.setPrice(40);

        List<Item> items = new ArrayList<Item>();
        items.add(item1);
        items.add(item2);

        PaymentDetails paymentDetails = new PaymentDetails();
        paymentDetails.setAmount(100);
        paymentDetails.setPaymentMode(PaymentMode.CREDIT_CARD);
        paymentDetails.setCardNumber("12345678");

        Location destination = new Location();
        destination.setLatitude(73.23);
        destination.setLongitude(132.34);

        Order order = new Order();
        order.setOrderId(1);
        order.setItems(items);
        order.setCurrentStatus(OrderStatus.PROCESSING);
        order.setDestination(destination);
        order.setPaymentDetails(paymentDetails);
        order.setTimeOfOrderDelivery(new Date());

        LogisticsSystem logisticsSystem = new LogisticsSystem();
        logisticsSystem.registerNewUser(user);
        logisticsSystem.takeAnOrder(order);
        logisticsSystem.processOrder(order);
    }
}
```