# 实现单个链表的迭代器模式

> 原文:[https://www . geeksforgeeks . org/implementing-iterator-pattern-of-a-single-link-list/](https://www.geeksforgeeks.org/implementing-iterator-pattern-of-a-single-linked-list/)

STL 是 C++的支柱之一。它让生活变得容易得多，尤其是当你专注于解决问题，而你不想花时间去实现已经存在的东西，这保证了一个健壮的解决方案。软件工程的一个关键方面是避免重新发明轮子。可重用性始终是**的首选。**

**虽然依赖库函数直接影响我们的效率，但如果没有正确理解库函数是如何工作的，有时就会失去我们一直谈论的工程效率的意义。错误选择的数据结构可能会在未来某个时候再次困扰我们。解决方法很简单。使用库方法，但知道它如何处理幕后操作。**

**说够了！今天我们将看看如何实现我们自己的单个链表的**迭代器模式。下面是链表的 STL 实现的样子:****

## **C++**

```
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // creating  a list
    vector<int> list;

    // elements to be added at the end.
    // in the above created list.
    list.push_back(1);
    list.push_back(2);
    list.push_back(3);

    // elements of list are retrieved through iterator.
    for (vector<int>::iterator it = list.begin();
                                it != list.end(); ++it)
        cout << *it << " ";

    return 0;
}
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import java.util.*;
class GFG
{

    public static void main(String[] args)
    {

        // creating  a list
        ArrayList<Integer> list = new ArrayList<>();

        // elements to be added at the end.
        // in the above created list.
        list.add(1);
        list.add(2);
        list.add(3);

        // elements of list are retrieved through iterator.
        Iterator<Integer> it = list.iterator();
        while (it.hasNext())
        {
            System.out.print(it.next() + " ");
        }
    }
}

// This code is contributed by pratham76
```

## **蟒蛇 3**

```
if __name__=='__main__':

    # Creating  a list
    list = []

    # Elements to be added at the end.
    # in the above created list.
    list.append(1)
    list.append(2)
    list.append(3)

    # Elements of list are retrieved
    # through iterator.
    for it in list:
        print(it, end = ' ')

# This code is contributed by rutvik_56
```

## **C#**

```
using System;
using System.Collections.Generic;

public class GFG {

    public static void Main(String[] args) {

        // creating a list
        List<int> list = new List<int>();

        // elements to be added at the end.
        // in the above created list.
        list.Add(1);
        list.Add(2);
        list.Add(3);

        // elements of list are retrieved through iterator.

        foreach (int it in list) {
            Console.Write(it + " ");
        }
    }
}

// This code contributed by umadevi9616
```

## **java 描述语言**

```

<script>

        // creating a list
        var list =  [];

        // elements to be added at the end.
        // in the above created list.
        list.push(1);
        list.push(2);
        list.push(3);

        // elements of list are retrieved through iterator.

        for (var i = 0; i<list.length;i++) {
            document.write(list[i] + " ");
        }

// This code contributed by umadevi9616

</script>
```

****输出****

```
1 2 3
```

****cin** 和 **cout** 的优点之一是它们不需要格式说明符来处理数据类型。这与模板相结合，使得代码更加清晰易读。虽然我更喜欢 C++中的命名方法以大写字母开头，但是这个实现遵循 STL 规则来模仿确切的方法调用集，即 push_back、begin、end。**

**下面是我们自己的 LinkedList 及其迭代器模式的实现:**

## **C++**

```
// C++ program to implement Custom Linked List and
// iterator pattern.
#include <bits/stdc++.h>
using namespace std;

// Custom class to handle Linked List operations
// Operations like push_back, push_front, pop_back,
// pop_front, erase, size can be added here
template <typename T>
class LinkedList
{
    // Forward declaration
    class Node;

public:
    LinkedList<T>() noexcept
    {
        // caution: static members can't be
        // initialized by initializer list
        m_spRoot = nullptr;
    }

    // Forward declaration must be done
    // in the same access scope
    class Iterator;

    // Root of LinkedList wrapped in Iterator type
    Iterator begin()
    {
        return Iterator(m_spRoot);
    }

    // End of LInkedList wrapped in Iterator type
    Iterator end()
    {
        return Iterator(nullptr);
    }

    // Adds data to the end of list
    void push_back(T data);

    void Traverse();

    // Iterator class can be used to
    // sequentially access nodes of linked list
    class Iterator
    {
    public:
    Iterator() noexcept :
        m_pCurrentNode (m_spRoot) { }

    Iterator(const Node* pNode) noexcept :
        m_pCurrentNode (pNode) { }

        Iterator& operator=(Node* pNode)
        {
            this->m_pCurrentNode = pNode;
            return *this;
        }

        // Prefix ++ overload
        Iterator& operator++()
        {
            if (m_pCurrentNode)
                m_pCurrentNode = m_pCurrentNode->pNext;
            return *this;
        }

        // Postfix ++ overload
        Iterator operator++(int)
        {
            Iterator iterator = *this;
            ++*this;
            return iterator;
        }

        bool operator!=(const Iterator& iterator)
        {
            return m_pCurrentNode != iterator.m_pCurrentNode;
        }

        int operator*()
        {
            return m_pCurrentNode->data;
        }

    private:
        const Node* m_pCurrentNode;
    };

private:

    class Node
    {
        T data;
        Node* pNext;

        // LinkedList class methods need
        // to access Node information
        friend class LinkedList;
    };

    // Create a new Node
    Node* GetNode(T data)
    {
        Node* pNewNode = new Node;
        pNewNode->data = data;
        pNewNode->pNext = nullptr;

        return pNewNode;
    }

    // Return by reference so that it can be used in
    // left hand side of the assignment expression
    Node*& GetRootNode()
    {
        return m_spRoot;
    }

    static Node* m_spRoot;
};

template <typename T>
/*static*/ typename LinkedList<T>::Node* LinkedList<T>::m_spRoot = nullptr;

template <typename T>
void LinkedList<T>::push_back(T data)
{
    Node* pTemp = GetNode(data);
    if (!GetRootNode())
    {
        GetRootNode() = pTemp;
    }
    else
    {
        Node* pCrawler = GetRootNode();
        while (pCrawler->pNext)
        {
            pCrawler = pCrawler->pNext;
        }

        pCrawler->pNext = pTemp;
    }
}

template <typename T>
void LinkedList<T>::Traverse()
{
    Node* pCrawler = GetRootNode();

    while (pCrawler)
    {
        cout << pCrawler->data << " ";
        pCrawler = pCrawler->pNext;
    }

    cout << endl;
}

//Driver program
int main()
{
    LinkedList<int> list;

    // Add few items to the end of LinkedList
    list.push_back(1);
    list.push_back(2);
    list.push_back(3);

    cout << "Traversing LinkedList through method" << endl;
    list.Traverse();

    cout << "Traversing LinkedList through Iterator" << endl;
    for ( LinkedList<int>::Iterator iterator = list.begin();
            iterator != list.end(); iterator++)
    {
        cout << *iterator << " ";
    }

    cout << endl;

    return 0;
}
```

****输出:****

```
Traversing LinkedList through method
1 2 3 
Traversing LinkedList through Iterator
1 2 3
```

****练习:**
当我们有一个数据时，上面的实现效果很好。扩展这段代码，使其适用于包装在类中的一组数据。**

**本文由 [**阿施·巴恩瓦尔**](https://about.me/aashishbarnwal) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。**