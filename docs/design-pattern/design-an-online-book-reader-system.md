# 设计一个在线读书系统

> 原文:[https://www . geesforgeks . org/design-an-online-book-reader-system/](https://www.geeksforgeeks.org/design-an-online-book-reader-system/)

设计一个在线图书阅读器系统(面向对象设计)。

**在**问:亚马逊，微软，以及更多的采访

**解决方案**:假设我们要设计一个基本的在线阅读系统，提供以下功能:

搜索图书数据库并阅读一本书。
·用户成员资格的创建和扩展。
·一次只有一个活动用户，并且该用户只有一个活动图书

OnlineReaderSystem 类代表了我们程序的主体。我们可以实现
类，这样它就可以存储所有涉及用户管理的书籍的信息，并刷新显示，但这将使这个类相当庞大。相反，我们选择将这些组件分离成库、用户管理器和显示类。

这些课程:

1.用户
2。书
3。图书馆
4。用户管理器
5。显示
6。OnlineReaderSystem

完整代码如下:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.HashMap;

/*
* This class represents the system
*/

class OnlineReaderSystem {
    private Library library;
    private UserManager userManager;
    private Display display;
    private Book activeBook;
    private User activeUser;

    public OnlineReaderSystem()
    {
        userManager = new UserManager();
        library = new Library();
        display = new Display();
    }

    public Library getLibrary()
    {
        return library;
    }

    public UserManager getUserManager()
    {
        return userManager;
    }

    public Display getDisplay()
    {
        return display;
    }

    public Book getActiveBook()
    {
        return activeBook;
    }

    public void setActiveBook(Book book)
    {
        activeBook = book;
        display.displayBook(book);
    }

    public User getActiveUser()
    {
        return activeUser;
    }

    public void setActiveUser(User user)
    {
        activeUser = user;
        display.displayUser(user);
    }
}

/*
* We then implement separate classes to handle the user
* manager, the library, and the display components 
*/

/*
* This class represents the Library which is responsible
* for storing and searching the books.
*/
class Library {
    private HashMap<Integer, Book> books;

    public Library()
    {
        books = new HashMap<Integer, Book>();
    }

    public Boolean addBook(int id, String details, String title)
    {
        if (books.containsKey(id)) {
            return false;
        }
        Book book = new Book(id, details, title);
        books.put(id, book);
        return true;
    }

    public Boolean addBook(Book book)
    {
        if (books.containsKey(book.getId())) {
            return false;
        }

        books.put(book.getId(), book);
        return true;
    }

    public boolean remove(Book b)
    {
        return remove(b.getId());
    }

    public boolean remove(int id)
    {
        if (!books.containsKey(id)) {
            return false;
        }
        books.remove(id);
        return true;
    }

    public Book find(int id)
    {
        return books.get(id);
    }
}

/*
* This class represents the UserManager which is responsible 
* for managing the users, their membership etc.
*/

class UserManager {
    private HashMap<Integer, User> users;

    public UserManager()
    {
        users = new HashMap<Integer, User>();
    }
    public Boolean addUser(int id, String details, String name)
    {
        if (users.containsKey(id)) {
            return false;
        }
        User user = new User(id, details, name);
        users.put(id, user);
        return true;
    }

    public Boolean addUser(User user)
    {
        if (users.containsKey(user.getId())) {
            return false;
        }

        users.put(user.getId(), user);
        return true;
    }

    public boolean remove(User u)
    {
        return remove(u.getId());
    }

    public boolean remove(int id)
    {
        if (users.containsKey(id)) {
            return false;
        }
        users.remove(id);
        return true;
    }

    public User find(int id)
    {
        return users.get(id);
    }
}

/*
* This class represents the Display, which is responsible 
* for displaying the book, it's pages and contents. It also 
* shows the current user. * It provides the method
* turnPageForward, turnPageBackward, refreshPage etc.
*/

class Display {
    private Book activeBook;
    private User activeUser;
    private int pageNumber = 0;

    public void displayUser(User user)
    {
        activeUser = user;
        refreshUsername();
    }

    public void displayBook(Book book)
    {
        pageNumber = 0;
        activeBook = book;

        refreshTitle();
        refreshDetails();
        refreshPage();
    }

    public void turnPageForward()
    {
        pageNumber++;
        System.out.println("Turning forward to page no " +
                   pageNumber + " of book having title " +
                                     activeBook.getTitle());
        refreshPage();
    }

    public void turnPageBackward()
    {
        pageNumber--;
        System.out.println("Turning backward to page no " +
                    pageNumber + " of book having title " + 
                                    activeBook.getTitle());
        refreshPage();
    }

    public void refreshUsername()
    {
        /* updates username display */
        System.out.println("User name " + activeUser.getName() + 
                                             " is refreshed");
    }

    public void refreshTitle()
    {
        /* updates title display */
        System.out.println("Title of the book " +
                        activeBook.getTitle() + " refreshed");
    }

    public void refreshDetails()
    {
        /* updates details display */
        System.out.println("Details of the book " +
                        activeBook.getTitle() + " refreshed");
    }

    public void refreshPage()
    {
        /* updated page display */
        System.out.println("Page no " + pageNumber + " refreshed");
    }
}

/* 
* The classes for User and Book simply hold data and 
* provide little functionality.
* This class represents the Book which is a simple POJO
*/

class Book {
    private int bookId;
    private String details;
    private String title;

    public Book(int id, String details, String title)
    {
        bookId = id;
        this.details = details;
        this.title = title;
    }

    public int getId()
    {
        return bookId;
    }

    public void setId(int id)
    {
        bookId = id;
    }

    public String getDetails()
    {
        return details;
    }

    public void setDetails(String details)
    {
        this.details = details;
    }

    public String getTitle()
    {
        return title;
    }

    public void setTitle(String title)
    {
        this.title = title;
    }
}

/*
* This class represents the User which is a simple POJO
*/

class User {
    private int userId;
    private String name;
    private String details;

    public void renewMembership()
    {
    }

    public User(int id, String details, String name)
    {
        this.userId = id;
        this.details = details;
        this.name = name;
    }

    public int getId()
    {
        return userId;
    }

    public void setId(int id)
    {
        userId = id;
    }

    public String getDetails()
    {
        return details;
    }

    public void setDetails(String details)
    {
        this.details = details;
    }

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }
}

// This class is used to test the Application

public class AppTest {

    public static void main(String[] args)
    {

        OnlineReaderSystem onlineReaderSystem = new OnlineReaderSystem();

        Book dsBook = new Book(1, "It contains Data Structures", "Ds");
        Book algoBook = new Book(2, "It contains Algorithms", "Algo");

        onlineReaderSystem.getLibrary().addBook(dsBook);
        onlineReaderSystem.getLibrary().addBook(algoBook);

        User user1 = new User(1, " ", "Ram");
        User user2 = new User(2, " ", "Gopal");

        onlineReaderSystem.getUserManager().addUser(user1);
        onlineReaderSystem.getUserManager().addUser(user2);

        onlineReaderSystem.setActiveBook(algoBook);
        onlineReaderSystem.setActiveUser(user1);

        onlineReaderSystem.getDisplay().turnPageForward();
        onlineReaderSystem.getDisplay().turnPageForward();
        onlineReaderSystem.getDisplay().turnPageBackward();
    }
}
```

## C#

```
using System;
using System.Collections.Generic;

/*
* This class represents the system
*/

class OnlineReaderSystem
{
    private Library library;
    private UserManager userManager;
    private Display display;
    private Book activeBook;
    private User activeUser;

    public OnlineReaderSystem()
    {
        userManager = new UserManager();
        library = new Library();
        display = new Display();
    }

    public Library getLibrary()
    {
        return library;
    }

    public UserManager getUserManager()
    {
        return userManager;
    }

    public Display getDisplay()
    {
        return display;
    }

    public Book getActiveBook()
    {
        return activeBook;
    }

    public void setActiveBook(Book book)
    {
        activeBook = book;
        display.displayBook(book);
    }

    public User getActiveUser()
    {
        return activeUser;
    }

    public void setActiveUser(User user)
    {
        activeUser = user;
        display.displayUser(user);
    }
}

/*
* We then implement separate classes to handle the user
* manager, the library, and the display components 
*/

/*
* This class represents the Library which is responsible
* for storing and searching the books.
*/
class Library 
{
    private Dictionary<int, Book> books;

    public Library()
    {
        books = new Dictionary<int, Book>();
    }

    public Boolean addBook(int id, String details, 
                                   String title)
    {
        if (books.ContainsKey(id))
        {
            return false;
        }
        Book book = new Book(id, details, title);
        books.Add(id, book);
        return true;
    }

    public Boolean addBook(Book book)
    {
        if (books.ContainsKey(book.getId()))
        {
            return false;
        }

        books.Add(book.getId(), book);
        return true;
    }

    public bool remove(Book b)
    {
        return remove(b.getId());
    }

    public bool remove(int id)
    {
        if (!books.ContainsKey(id)) 
        {
            return false;
        }
        books.Remove(id);
        return true;
    }

    public Book find(int id)
    {
        return books[id];
    }
}

/*
* This class represents the UserManager  
* which is responsible for managing the users, 
* their membership etc.
*/
class UserManager
{
    private Dictionary<int, User> users;

    public UserManager()
    {
        users = new Dictionary<int, User>();
    }
    public Boolean addUser(int id, String details, 
                                   String name)
    {
        if (users.ContainsKey(id)) 
        {
            return false;
        }
        User user = new User(id, details, name);
        users.Add(id, user);
        return true;
    }

    public Boolean addUser(User user)
    {
        if (users.ContainsKey(user.getId()))
        {
            return false;
        }

        users.Add(user.getId(), user);
        return true;
    }

    public bool remove(User u)
    {
        return remove(u.getId());
    }

    public bool remove(int id)
    {
        if (users.ContainsKey(id)) 
        {
            return false;
        }
        users.Remove(id);
        return true;
    }

    public User find(int id)
    {
        return users[id];
    }
}

/*
* This class represents the Display, which is responsible 
* for displaying the book, it's pages and contents.  
* It also shows the current user. * It provides the method
* turnPageForward, turnPageBackward, refreshPage etc.
*/
class Display
{
    private Book activeBook;
    private User activeUser;
    private int pageNumber = 0;

    public void displayUser(User user)
    {
        activeUser = user;
        refreshUsername();
    }

    public void displayBook(Book book)
    {
        pageNumber = 0;
        activeBook = book;

        refreshTitle();
        refreshDetails();
        refreshPage();
    }

    public void turnPageForward()
    {
        pageNumber++;
        Console.WriteLine("Turning forward to page no " +
                  pageNumber + " of book having title " +
                                  activeBook.getTitle());
        refreshPage();
    }

    public void turnPageBackward()
    {
        pageNumber--;
        Console.WriteLine("Turning backward to page no " +
                   pageNumber + " of book having title " + 
                                   activeBook.getTitle());
        refreshPage();
    }

    public void refreshUsername()
    {
        /* updates username display */
        Console.WriteLine("User name " + 
                  activeUser.getName() + 
                       " is refreshed");
    }

    public void refreshTitle()
    {
        /* updates title display */
        Console.WriteLine("Title of the book " +
                         activeBook.getTitle() + 
                                  " refreshed");
    }

    public void refreshDetails()
    {
        /* updates details display */
        Console.WriteLine("Details of the book " +
                           activeBook.getTitle() + 
                                    " refreshed");
    }

    public void refreshPage()
    {
        /* updated page display */
        Console.WriteLine("Page no " + pageNumber + 
                                     " refreshed");
    }
}

/* 
* The classes for User and Book simply hold data  
* and provide little functionality.
* This class represents the Book which is 
* a simple POJO
*/
class Book
{
    private int bookId;
    private String details;
    private String title;

    public Book(int id, String details, 
                        String title)
    {
        bookId = id;
        this.details = details;
        this.title = title;
    }

    public int getId()
    {
        return bookId;
    }

    public void setId(int id)
    {
        bookId = id;
    }

    public String getDetails()
    {
        return details;
    }

    public void setDetails(String details)
    {
        this.details = details;
    }

    public String getTitle()
    {
        return title;
    }

    public void setTitle(String title)
    {
        this.title = title;
    }
}

/*
* This class represents the User 
* which is a simple POJO
*/
class User
{
    private int userId;
    private String name;
    private String details;

    public void renewMembership()
    {
    }

    public User(int id, String details,
                        String name)
    {
        this.userId = id;
        this.details = details;
        this.name = name;
    }

    public int getId()
    {
        return userId;
    }

    public void setId(int id)
    {
        userId = id;
    }

    public String getDetails()
    {
        return details;
    }

    public void setDetails(String details)
    {
        this.details = details;
    }

    public String getName()
    {
        return name;
    }

    public void setName(String name)
    {
        this.name = name;
    }
}

// This class is used to test the Application
public class AppTest
{
    public static void Main(String[] args)
    {

        OnlineReaderSystem 
              onlineReaderSystem = new OnlineReaderSystem();

        Book dsBook = new Book(1, "It contains Data Structures", "Ds");
        Book algoBook = new Book(2, "It contains Algorithms", "Algo");

        onlineReaderSystem.getLibrary().addBook(dsBook);
        onlineReaderSystem.getLibrary().addBook(algoBook);

        User user1 = new User(1, " ", "Ram");
        User user2 = new User(2, " ", "Gopal");

        onlineReaderSystem.getUserManager().addUser(user1);
        onlineReaderSystem.getUserManager().addUser(user2);

        onlineReaderSystem.setActiveBook(algoBook);
        onlineReaderSystem.setActiveUser(user1);

        onlineReaderSystem.getDisplay().turnPageForward();
        onlineReaderSystem.getDisplay().turnPageForward();
        onlineReaderSystem.getDisplay().turnPageBackward();
    }
}

// This code is contributed by 29AjayKumar
```

[](https://practice.geeksforgeeks.org/courses/system-design-live)

### [极客 forges 系统设计课程](https://practice.geeksforgeeks.org/courses/system-design-live)

[](https://practice.geeksforgeeks.org/courses/system-design-live)

*想在领先的科技公司获得软件开发/工程师的工作吗？还是想从 SDE 一号顺利过渡到 SDE 二号或者高级开发者档案？*如果是，那么你需要**深入系统设计世界！**对系统设计概念的熟练掌握是非常必要的，尤其是对于工作的专业人员来说，这样才能在技术面试中获得比其他人急需的优势。

[![System-Design-Course-By-GeeksforGeeks](img/7bf50615801134182e8d824e7270a1b6.png)](https://practice.geeksforgeeks.org/courses/system-design-live)

*这就是为什么 GeeksforGeeks 为您提供以深度访谈为中心的* [***系统设计–现场课程***](https://practice.geeksforgeeks.org/courses/system-design-live) *将帮助您为谷歌、亚马逊、Adobe、优步和其他产品型公司准备与系统设计相关的问题。*